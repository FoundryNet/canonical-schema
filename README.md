# FoundryNet Canonical Schema for Industrial Telemetry

An open vocabulary for normalizing industrial equipment telemetry across
manufacturers, protocols, and platforms.

**694 canonical fields. 16,908 vendor tag mappings. 18 OEM families. MIT licensed.**

> **v2.0.0 publishes the full vocabulary.** 366 of these fields are
> corpus-attributed: real vendor tags were observed mapping onto them, and all
> 16,908 mappings belong to those 366. The other 328 are names the kernel can
> emit but that have no vendor tags yet. Every field says which it is in its
> `provenance` column, so nothing here implies evidence it does not have.

## The problem

Industrial equipment from N manufacturers produces telemetry in N incompatible
formats. A spindle speed is `S1_ActualVelocity` on one controller,
`SP_SPEED [RPM]` on another, and `Rotational_Speed_1/min` on a third. All three
are the same physical quantity, and nothing in the data says so.

Every integration solves this again from scratch. The mapping table gets rebuilt
per vendor, per site, per project, then thrown away when the project ends.

## The schema

This repository is the dictionary: the agreed target vocabulary that
vendor-specific tags get translated into.

| Vertical | Fields | Covers |
|---|---:|---|
| `cnc` | 82 | CNC machine tools |
| `robotics` | 53 | Robotics |
| `additive` | 6 | Additive manufacturing |
| `vehicle` | 64 | Vehicles and off-highway |
| `amr` | 10 | Autonomous mobile robots |
| `universal` | 151 | Universal (cross-vertical) |

Every field has a name and a vertical. Where the source data supports it, a
field also has a type, a unit, and an example value. Each field lists the real
vendor tags observed to map onto it, and which OEM families those tags came from.

As of v1.1.0 a field also carries a **unit contract** and a **physics range**.
The field name tells you what the value means; the contract tells you what unit
it is in and which source units may be converted into it. 386 fields carry a
unit contract, 219 carry physics bounds.

Three fields are published **without** a contract, carrying a
`contract_withheld` reason instead: `ac_voltage_phase_a`, `ac_current_phase_c`
and `ac_voltage_phase_c`. The contract generator read the three-phase suffix as
a unit (`_a` as Amps, `_c` as Celsius) when it actually means phase A and phase
C, so it typed two electrical fields as temperatures that accept Fahrenheit. A
contract you would corrupt data by following is worse than no contract, so
those three ship without one until the source metadata is fixed.

```json
{
  "field": "spindle_speed_rpm",
  "type": "integer",
  "unit": "rpm",
  "description": "Speed of the spindle, in rpm.",
  "vertical": "cnc",
  "example_value": 3400,
  "mapped_from": ["Act Sp Speed (RPM)", "SP_SPEED [RPM]", "SPRPM (1/min)",
                  "Rotational_Speed_1/min", "spindle_velocity[rpm]", "S1_ActualVelocity"],
  "oem_coverage": ["brother", "dmg_mori", "fanuc", "haas", "heidenhain",
                   "hurco", "mazak", "mitsubishi", "siemens", "tornos"],
  "mapping_count": 307,

  "si": true,
  "quantity": "rotational",
  "accepted_input_units": ["rpm"],
  "conversion_required": [],
  "measurement_type": "instantaneous",
  "physics_bounds": {"min": -50000, "max": 50000},
  "bounds_note": "signed: an M04 reverse spindle legitimately reports negative rpm"
}
```

### The unit contract

`unit` is what the field holds. `accepted_input_units` are the source units a
normalizer may convert FROM, and `conversion_required` is the subset that needs
converting. A temperature field holding Celsius accepts C, F, K and R:

```json
"sensor_readings.coolant_temp": {
  "unit": "C",
  "accepted_input_units": ["C", "F", "K", "R"],
  "conversion_required": ["F", "K", "R"],
  "physics_bounds": {"min": -40, "max": 215},
  "measurement_type": "instantaneous"
}
```

Note that the unit lives in the contract, not in the field name. There is no
`coolant_temp_c` and no `coolant_temp_f` — one field, one unit, declared.

### Physics bounds

`physics_bounds` is the physically defensible range for the field. A value
outside it is an equipment error code, not a reading. Industrial controllers
routinely emit `9999`, `65535` or `-32768` to mean "sensor unavailable", and a
`9999` landing in a Celsius field reads as a catastrophic overheat. Bounds are
deliberately generous: they catch the impossible, not the merely unusual.

Where a range is signed, it says so. Spindle speed runs negative because M04
reverse rotation is a real operation, not an error.

### Measurement type

`measurement_type` is one of `instantaneous`, `cumulative` or `setpoint`. It
distinguishes a snapshot reading from a lifetime counter from a commanded
target — without it, `operating_hours: 14203` (lifetime) and
`operating_hours: 8.5` (since last service) are indistinguishable.

## What is in here

```
schema/
  fields.json              all 694 canonical fields, full metadata
  fields.csv               same data, one row per field
  oem-mappings/            {raw_tag: canonical_field} per OEM family
  verticals/               field lists per machine class
docs/
  FIELD_REFERENCE.md       every field, documented
  INTEGRATION_GUIDE.md     how to use this in your project
  CONTRIBUTING.md          how to submit mappings and fields
  WHY_CANONICAL.md         why two decades of standards did not close this
```

## Usage

Use these field names in your agents, dashboards, automations, and integrations.
When every system uses the same names, interoperability stops being a project.

```python
import json, urllib.request

URL = ("https://raw.githubusercontent.com/FoundryNet/canonical-schema"
       "/main/schema/fields.json")
schema = json.load(urllib.request.urlopen(URL))
by_name = {f["field"]: f for f in schema["fields"]}

# Reverse index: any known vendor tag to its canonical field
lookup = {tag: f["field"] for f in schema["fields"] for tag in f["mapped_from"]}
print(lookup.get("S1_ActualVelocity"))   # spindle_speed_rpm
```

See [docs/INTEGRATION_GUIDE.md](docs/INTEGRATION_GUIDE.md) for adapter patterns,
validation, and unit handling.

## OEM coverage

1,865 of the 16,908 mappings are attributed to a named OEM family. The rest
are generic, cross-vendor, and multilingual tag variants that belong to no single
manufacturer.

| OEM family | Vendor tags | Canonical fields touched |
|---|---:|---:|
| `abb` | 17 | 4 |
| `brother` | 27 | 23 |
| `caterpillar` | 21 | 19 |
| `dmg_mori` | 43 | 20 |
| `doosan` | 25 | 23 |
| `fanuc` | 759 | 66 |
| `haas` | 240 | 34 |
| `heidenhain` | 44 | 33 |
| `hurco` | 17 | 15 |
| `komatsu` | 8 | 8 |
| `kuka` | 44 | 6 |
| `mazak` | 46 | 19 |
| `mitsubishi` | 30 | 29 |
| `octoprint` | 17 | 17 |
| `okuma` | 34 | 18 |
| `siemens` | 440 | 56 |
| `tornos` | 29 | 25 |
| `universal_robots` | 24 | 3 |

## Coverage and limits

This comes out of a production mapping corpus. That corpus was built to answer
one question, "what canonical field does this tag mean?", so its descriptive
metadata is uneven. The files record which values were measured and which were
inferred, rather than presenting a uniform guess:

- **Provenance.** 366 fields are `corpus`, 328 are `vocabulary`. Filter on the
  `provenance` column before you use mapping counts for anything: every one of
  the 16,908 mappings sits on a `corpus` field, and every `vocabulary` field
  has a `mapping_count` of 0.
- **Types.** 174 of 694 fields have a type, and 172 of those are on `corpus`
  fields. The `vocabulary` tier is almost entirely untyped: it came from
  deterministic packs that declare a unit, not a type.
- **Units.** 386 of 694 fields carry a unit. `declared` means a vertical pack
  states it. `derived` means the field-name suffix implies it. A missing unit
  means unknown, not dimensionless.
- **Descriptions.** These are generated from the field name and unit. They are
  editorial rather than extracted, and they are the easiest thing to improve.
- **Process manufacturing.** `schema/verticals/process.json` lists
  74 process fields for pharma, food and beverage, and chemical
  equipment. None of them have vendor tag mappings yet. As of v2.0.0 they are
  counted in the 694 and marked `provenance: vocabulary`, rather than being
  left out entirely as they were in the 366.

Every field carries `type_source` and `unit_source` so you can filter down to
only what was measured. Closing these gaps is what
[CONTRIBUTING.md](docs/CONTRIBUTING.md) is for.

## The kernel

The schema is the dictionary. Translating arbitrary vendor telemetry into it,
including tags that have never been seen before, is a separate problem. That is
what the Forge kernel does, and it is a commercial product that is not part of
this repository.

The schema is free. The translation is the product.

## License

MIT. See [LICENSE](LICENSE). Use it in commercial products, fork it, vendor it,
embed it. Attribution is appreciated and not required.

Built by [Foundry Labs](https://foundrynet.io).
