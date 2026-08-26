# Contributing

This schema is only as good as the real vendor tags in it. Mappings from real
equipment are the most valuable thing you can send.

## What is most useful

1. **Vendor tags for existing fields.** If your Mazak emits `SpindleRPM_Act` and
   it is not in `mazak.json`, that is a one-line pull request.
2. **A new OEM family.** Any manufacturer not already in `schema/oem-mappings/`.
3. **Process manufacturing tags.** `schema/verticals/process.json` lists
   74 declared fields with no vendor mappings at all. This is the
   largest gap in the schema.
4. **Better descriptions.** The current ones are generated from field names. A
   domain-accurate sentence is better than a generated gloss.
5. **Units and types.** 308 fields have no recorded unit and
   194 have no type. If you know one from a vendor manual, cite it.

## Adding a mapping

Edit the relevant `schema/oem-mappings/<oem>.json` and add an entry to
`mappings`:

```json
"SpindleRPM_Act": "spindle_speed_rpm"
```

Rules:

- The canonical field must already exist in `schema/fields.json`. If it does not,
  propose the field first.
- Use the tag exactly as the equipment emits it, including case, spaces, and
  brackets. `Act Sp Speed (RPM)` is a real tag and should not be tidied up.
- One manufacturer per file.

## Proposing a new field

Open an issue with:

- The proposed name, following the existing conventions: lowercase, underscores,
  and a unit suffix where there is a unit, such as `_c`, `_pct`, `_rpm`, `_bar`,
  or `_mm_s`.
- The physical quantity and unit.
- The vertical: `cnc`, `robotics`, `additive`, `vehicle`, `amr`, `universal`, or
  `process`.
- At least one real vendor tag that maps to it, and the equipment it came from.

Fields with no real tag behind them will not be added. That rule is why the
existing 694 can be trusted.

## Correcting a mapping

A wrong mapping matters more than a missing one, because it silently corrupts
downstream analytics. Open an issue titled `wrong mapping: <tag>` with the tag,
the current canonical field, what it should be, and how you know: a manual,
controller documentation, or observed values.

## Ground rules

- Real equipment only. No speculative or generated tags.
- Cite the source where you can: controller manual, protocol spec, integration doc.
- Keep JSON sorted with 2-space indentation.
- Contributions are MIT licensed, the same as the rest of the repository.

## Out of scope

The resolution engine that translates unseen tags automatically is a commercial
product and is not part of this repository. Issues asking for it will be closed
with a pointer rather than a patch. This repository is the dictionary, not the
translator.
