# Contributing

This schema is only as good as the real vendor tags in it. Contributions of
actual mappings from real equipment are the most valuable thing you can send.

## What we most want

1. **Vendor tags for existing fields** — you have a Mazak that emits
   `SpindleRPM_Act` and it is not in `mazak.json`. That is a one-line PR.
2. **A new OEM family** — any manufacturer not in `schema/oem-mappings/`.
3. **Process manufacturing tags** — `schema/verticals/process.json` lists
   74 declared fields with **zero** vendor mappings. Tags for these are
   the single biggest gap.
4. **Better descriptions** — the current ones are generated from field names.
   A domain-accurate sentence beats a generated gloss every time.
5. **Units and types** — 308 fields have no recorded unit and
   194 have no type. If you know one from a vendor manual, cite it.

## Adding a mapping

Edit the relevant `schema/oem-mappings/<oem>.json` and add to `mappings`:

```json
"SpindleRPM_Act": "spindle_speed_rpm"
```

Rules:

- The canonical field **must already exist** in `schema/fields.json`. If it does
  not, propose the field first (below).
- Use the tag **exactly as the equipment emits it** — original case, spaces,
  brackets, units. `Act Sp Speed (RPM)` is a real tag; do not tidy it.
- One manufacturer per file.

## Proposing a new field

Open an issue with:

- Proposed name, following the existing conventions (lowercase, underscores,
  unit suffix where there is a unit: `_c`, `_pct`, `_rpm`, `_bar`, `_mm_s`).
- Physical quantity and unit.
- Vertical (`cnc`, `robotics`, `additive`, `vehicle`, `amr`, `universal`, `process`).
- At least one real vendor tag that maps to it, and the equipment it came from.

A field with no real tag behind it will not be added. That rule is why the
existing 366 are trustworthy.

## Correcting a mapping

Wrong mappings matter more than missing ones — a wrong one silently corrupts
downstream analytics. Open an issue titled `wrong mapping: <tag>` with the tag,
the current canonical, what it should be, and how you know (manual, controller
docs, observed values).

## Ground rules

- Real equipment only. No speculative or generated tags.
- Cite the source when you can: controller manual, protocol spec, integration doc.
- Keep JSON sorted and 2-space indented.
- MIT — by contributing you agree your contribution is licensed the same way.

## What is out of scope

The resolution engine that translates unseen tags automatically is a commercial
product and is not part of this repository. Issues asking for it will be closed
with a pointer, not a patch. This repo is the dictionary, not the translator.
