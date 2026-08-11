# Why a canonical schema exists

## The problem is old, well understood, and still unsolved

Cross-vendor interoperability in industrial equipment is not a new observation.
It has been the explicit goal of a long line of standards:

| Year | Standard | What it addressed |
|---|---|---|
| 1994 | SAE J1939 | CAN bus messaging for heavy-duty vehicles |
| 2000 | ISA-95 / IEC 62264 | Enterprise–control system integration models |
| 2006– | OPC UA (IEC 62541) | Transport, security, and information modelling |
| 2008 | MTConnect | Read-only semantic vocabulary for machine tools |
| 2016 | ISO 15143-3 (AEMP) | Telematics data for off-highway equipment |
| 2016 | MQTT Sparkplug B | Payload/state conventions for MQTT namespaces |
| 2019– | OPC UA companion specs | Per-domain models (umati, Robotics, and others) |

That is more than two decades of serious, well-funded work by people who
understood the problem. Each standard is good. The problem persists anyway.

## Why standards did not close it

**Adoption is partial and optional.** A standard defines what a compliant
device *may* emit. It does not make a 2009 controller emit it. Roughly the
installed base of industrial equipment predates the standard meant to describe
it, and that equipment does not get replaced on a software timetable.

**Standards are vocabularies, not translations.** MTConnect says a rotary
velocity should be called `RotaryVelocity`. It does not tell you that the
Heidenhain tag `SP_SPEED [RPM]` is one. The gap between "here is the correct
name" and "here is what this specific machine actually calls it" is the entire
integration cost, and no standard has ever eliminated it.

**Vendors extend.** Even compliant implementations add proprietary items,
because real machines have features the standard did not anticipate. The
extensions are where the useful signals usually live.

**Multiple standards overlap.** A modern cell might carry OPC UA, MTConnect,
J1939, Modbus, and a vendor REST API simultaneously — describing overlapping
physical quantities under different names, units, and conventions.

The result is that N manufacturers still produce N schemas, and the mapping
table gets rebuilt per vendor, per site, per project — then discarded.

## What this repository is

The mapping table, published, so it stops being rebuilt.

366 canonical fields and 16,908 vendor tag mappings extracted from a
production normalization corpus, covering 18 OEM families across CNC,
robotics, additive, vehicle, and AMR equipment. It is not a new standard and
does not compete with the ones above — where MTConnect has a name for something,
this vocabulary generally follows it.

It is descriptive rather than aspirational. Every field is here because real
equipment emitted a tag that meant it.

## Why publish it

A dictionary is only valuable if everyone has the same one. A proprietary
canonical vocabulary is a contradiction: the whole point is shared meaning, and
meaning is not shared if it is licensed.

So the vocabulary is MIT and free to embed, fork, or vendor.

Translating *unseen* tags — the ones no corpus has yet, from a controller nobody
has integrated before — is a genuinely hard and separate problem. That is the
commercial product.

**The schema is free. The translation is the product.**

## Honest scope

This vocabulary describes what the corpus has seen. It is not exhaustive, it is
CNC-weighted by history, and its descriptive metadata (units, types,
descriptions) is incomplete in ways the files record explicitly rather than
paper over. See the honest-limits section of the [README](../README.md), and
[CONTRIBUTING.md](CONTRIBUTING.md) for the gaps most worth closing.
