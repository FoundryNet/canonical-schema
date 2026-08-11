# Integration Guide

How to use the canonical schema in your own project. These are static data
files, so nothing here depends on a FoundryNet service.

## 1. Load the schema

```python
import json, urllib.request

RAW = ("https://raw.githubusercontent.com/FoundryNet/canonical-schema"
       "/main/schema/fields.json")
schema = json.load(urllib.request.urlopen(RAW))
fields = {f["field"]: f for f in schema["fields"]}
```

You can also vendor the files directly. They are small and MIT licensed. Pin a
release tag if you need reproducibility.

## 2. Build a reverse index

The most useful first step is mapping known vendor tags onto canonical names.

```python
lookup = {}
for f in schema["fields"]:
    for tag in f["mapped_from"]:
        lookup[tag] = f["field"]
        lookup[tag.lower()] = f["field"]

def to_canonical(tag):
    return lookup.get(tag) or lookup.get(tag.lower())

to_canonical("S1_ActualVelocity")   # 'spindle_speed_rpm'
to_canonical("SPRPM (1/min)")       # 'spindle_speed_rpm'
```

This resolves tags that are already in the corpus. It will not resolve a tag
nobody has seen before. See [Limits](#5-limits).

## 3. Per-OEM mappings

If you already know the manufacturer, load only that file:

```python
haas = json.load(open("schema/oem-mappings/haas.json"))
haas["mappings"]["AXIS_A_LOAD"]     # 'axes.a_load_pct'
```

Each OEM file is a flat `{raw_tag: canonical_field}` object plus the list of
canonical fields it touches.

## 4. Validate your output

Use the schema as a contract in tests so a refactor cannot silently rename a
field:

```python
CANON = {f["field"] for f in schema["fields"]}

def validate(reading: dict):
    unknown = set(reading) - CANON
    if unknown:
        raise ValueError(f"non-canonical fields: {sorted(unknown)}")
```

For unit safety, check the declared unit before doing arithmetic:

```python
f = fields["spindle_speed_rpm"]
assert f["unit"] == "rpm"
```

Only 58 of 366 fields carry a unit. Treat a missing unit as unknown rather
than dimensionless. See the coverage section of the README.

## 5. Limits

- **Unknown tags.** The reverse index is an exact match over observed tags. A tag
  from a vendor or firmware revision that is not in the corpus returns `None`.
  Fuzzy, embedding, and model-assisted resolution of new tags are out of scope
  for this repository.
- **Field naming is not uniform.** The corpus grew around real vendor data, so
  both flat names such as `spindle_speed_rpm` and dotted names such as
  `axes.0.position_actual` and `sensor_readings.coolant_temp` exist. Match on the
  exact string.
- **One quantity can have several spellings.** `spindle_temperature` and
  `spindle_temperature_c` both appear. Normalize on your side if you need a
  single spelling.
- **`mapping_count` is corpus frequency.** It is not a confidence score and not a
  measure of how common the field is in the field.

## 6. Suggested conventions

If you emit telemetry, these conventions make your data readable by anything
that speaks this schema:

- Use the canonical name verbatim as the key.
- Keep the raw vendor tag alongside it. Normalization should be lossless.
- Match units to the field suffix: `_c` for Celsius, `_bar` for bar, `_mm_s` for
  mm/s, `_pct` for 0 to 100.
- Timestamp every reading in UTC using ISO 8601.
