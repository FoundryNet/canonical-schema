# Integration Guide

How to use the canonical schema in your own project. No dependency on any
FoundryNet service — these are static data files.

## 1. Load the schema

```python
import json, urllib.request

RAW = ("https://raw.githubusercontent.com/FoundryNet/canonical-schema"
       "/main/schema/fields.json")
schema = json.load(urllib.request.urlopen(RAW))
fields = {f["field"]: f for f in schema["fields"]}
```

Or vendor it — the files are small and MIT licensed. Pin a release tag if you
need reproducibility.

## 2. Build a reverse index

The fastest useful thing: map known vendor tags onto canonical names.

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

This resolves tags **already in the corpus**. It will not resolve a tag no one
has seen before — see [Limits](#5-limits).

## 3. Per-OEM mappings

If you know the manufacturer, load only that file:

```python
haas = json.load(open("schema/oem-mappings/haas.json"))
haas["mappings"]["AXIS_A_LOAD"]     # 'axes.a_load_pct'
```

Each OEM file is a flat `{raw_tag: canonical_field}` object plus the list of
canonical fields it touches.

## 4. Validate your output

Use the schema as a contract in tests, so a refactor cannot silently rename a
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

Only 58 of 366 fields carry a unit. Treat a missing `unit` as
*unknown*, never as *unitless* — see the honest-limits section of the README.

## 5. Limits

- **Unknown tags.** The reverse index is exact-match over observed tags. A tag
  from a vendor or firmware revision not in the corpus returns `None`. Fuzzy,
  embedding, or LLM-assisted resolution of novel tags is deliberately out of
  scope here.
- **Field naming is not uniform.** The corpus grew around real vendor data, so
  both flat (`spindle_speed_rpm`) and dotted (`axes.0.position_actual`,
  `sensor_readings.coolant_temp`) forms exist. Match on the exact string.
- **Same quantity, several spellings.** `spindle_temperature` and
  `spindle_temperature_c` can both appear. Normalize on your side if you need
  one spelling.
- **`mapping_count` is corpus frequency**, not a confidence score, and not a
  measure of how common the field is in the field.

## 6. Suggested conventions

If you emit telemetry, adopting these makes your data readable by anything that
speaks this schema:

- Use the canonical name verbatim as the key.
- Keep the raw vendor tag alongside it — normalization should be lossless.
- Emit SI-ish units matching the field suffix (`_c` Celsius, `_bar` bar,
  `_mm_s` mm/s, `_pct` 0–100).
- Timestamp every reading in UTC, ISO 8601.
