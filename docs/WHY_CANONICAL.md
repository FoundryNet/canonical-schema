# Why a canonical schema exists

## The problem is old and well understood

Cross-vendor interoperability in industrial equipment is not a new observation.
It has been the explicit goal of a long line of standards:

| Year | Standard | What it addressed |
|---|---|---|
| 1994 | SAE J1939 | CAN bus messaging for heavy-duty vehicles |
| 2000 | ISA-95 and IEC 62264 | Enterprise to control system integration models |
| 2006 onward | OPC UA (IEC 62541) | Transport, security, and information modelling |
| 2008 | MTConnect | Read-only semantic vocabulary for machine tools |
| 2016 | ISO 15143-3 (AEMP) | Telematics data for off-highway equipment |
| 2016 | MQTT Sparkplug B | Payload and state conventions for MQTT namespaces |
| 2019 onward | OPC UA companion specs | Per-domain models including umati and Robotics |

That is more than two decades of serious, well-funded work by people who
understood the problem. Each of these standards is good. The problem persists
anyway.

## Why the standards did not close it

**Adoption is partial and optional.** A standard defines what a compliant device
may emit. It does not make a 2009 controller emit it. Much of the installed base
predates the standard meant to describe it, and that equipment does not get
replaced on a software schedule.

**Standards are vocabularies, not translations.** MTConnect says a rotary
velocity should be called `RotaryVelocity`. It does not tell you that the
Heidenhain tag `SP_SPEED [RPM]` is one. The distance between "here is the correct
name" and "here is what this specific machine calls it" is the integration cost,
and no standard has removed it.

**Vendors extend.** Even compliant implementations add proprietary items, because
real machines have features the standard did not anticipate. Those extensions are
usually where the useful signals live.

**Standards overlap.** A modern work cell can carry OPC UA, MTConnect, J1939,
Modbus, and a vendor REST API at the same time, describing overlapping physical
quantities under different names, units, and conventions.

So N manufacturers still produce N schemas, and the mapping table gets rebuilt
per vendor, per site, per project, then discarded.

## What this repository is

The mapping table, published, so that it stops being rebuilt.

It contains 366 canonical fields and 16,908 vendor tag mappings taken from a
production normalization corpus, covering 18 OEM families across CNC,
robotics, additive, vehicle, and AMR equipment. It is not a new standard and does
not compete with the ones above. Where MTConnect already has a name for
something, this vocabulary generally follows it.

It is descriptive rather than aspirational. Every field is here because real
equipment emitted a tag that meant it.

## Why publish it

A dictionary is only useful if everyone has the same one. A proprietary canonical
vocabulary is a contradiction, because the point is shared meaning, and meaning
is not shared if it is licensed.

So the vocabulary is MIT and free to embed, fork, or vendor.

Translating tags that no corpus has seen yet, from a controller nobody has
integrated before, is a harder and separate problem. That is the commercial
product.

The schema is free. The translation is the product.

## Scope

This vocabulary describes what the corpus has seen. It is not exhaustive, its
history makes it CNC-weighted, and its descriptive metadata is incomplete in ways
the files record explicitly. See the coverage section of the [README](../README.md)
and [CONTRIBUTING.md](CONTRIBUTING.md) for the gaps most worth closing.
