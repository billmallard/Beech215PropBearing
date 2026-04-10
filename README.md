# Beech 215 Propeller Pitch Control Bearing — Open Source Replacement

## Project Goal

Develop open-source engineering documentation, CAD models, and manufacturing drawings sufficient to reproduce the **pitch control (actuator) bearing** for the Beechcraft 215 Series electric controllable-pitch propeller under the FAA **owner-produced parts** provisions of 14 CFR 21.9(a)(5).

This bearing (Beech P/N **B200-202**) has not been manufactured in decades. Existing units are irreplaceable through normal supply channels. Failure of this bearing can result in loss of pitch control — at minimum a grounded aircraft, potentially worse. The goal of this project is to ensure that early Bonanza operators are not forced to retire otherwise airworthy aircraft for lack of a mechanically simple part.

---

## Affected Aircraft and Propeller Systems

### Aircraft (FAA Type Certificate A-777)
The Beech 215 propeller was approved on the following Bonanza models:

| Model | Serial Numbers | Approved As |
|-------|---------------|-------------|
| 35    | D-1 through D-1500 | Beech controllable prop item 1(e) |
| A35   | D-1501 through D-2200, D-15001 | Items 1(e), 1(f) |
| B35   | D-2201 through D-2680 | Items 1(e), 1(f) |
| C35   | D-2681 through D-3400 | Items 1(e), 1(f), 1(g) |
| D35   | D-3401 through D-3698 | Items 1(e), 1(f), 1(g) |
| E35   | D-3293, D-3699 through D-3998 | Items 1(e), 1(f) |
| F35   | D-3999 through D-4391 | Items 1(e), 1(f), 1(g) |
| G35   | D-4392 through D-4865, D-15002 | Item 1(f) |
| 35R   | D-25R1 and up | Items 1(e), 1(f) |

### Propeller Assemblies
The 215 Series propeller was produced in four assembly variants:

| Assembly P/N | Hub P/N | Blade P/N | Notes |
|-------------|---------|-----------|-------|
| 215-110 | 215-109 | 215-207-88 | Manual electric |
| 215-108 | 215-107 | 215-207-88 | Manual electric |
| 215-116 | 215-107 | 215-213-84 | E-225-8 and E185 S/N 22183+ |
| 215-117 | 215-109 | 215-213-84 | E-225-8 and E185 S/N 22183+ |

Engines: Continental E-185-1, -8, -11 and E-225-8

---

## The Part: Pitch Control (Actuator) Bearing — B200-202

### Function
The pitch control bearing is the heart of the 215 propeller's pitch-change mechanism. Its outer race is keyed to the stationary sleeve (preventing rotation with the prop) and rides in the threaded ring gear hub. Its inner race rotates with the propeller and connects via control bolts to the yoke, which translates axial bearing movement into blade pitch change. When the electric motor drives the ring gear, the bearing assembly travels fore or aft, changing blade angle.

### Key Specifications (from Beech Manual 115187A1)
- **Lubrication interval**: Every 250 hours (MIL-G-3278 / AN-G-25 grease, max 4 grams)
- **Seal type**: Rubber grease seals retained by snap rings on each side
- **Snap ring retention**: Must be tight; expand by peening inner circumference if loose
- **Run-in after repack**: Rotate rapidly ~3 minutes; seal and snap ring must remain stationary

### Why It Fails
Lack of 250-hour relubrication is the primary failure mode. Bearing destruction leads to loss of pitch change capability. Replacement bearings are no longer available through any production source.

### Hub Wear Tolerances (Figure 2-1A, Manual 115187A1)
For context on mating hardware dimensions:

| Feature | Limit |
|---------|-------|
| Bushing width | 0.743 in. minimum |
| Diametrical clearance, bolt head to bushing | 0.0035 in. minimum |
| Total combined clearance at ends of gear hub | 0.017 in. maximum |
| Inside diameter, front bushing | 0.447 in. maximum |
| Outside diameter, small end of bolt | 0.433 in. minimum |
| Inside diameter, rear bushing | 0.510 in. maximum |
| Outside diameter, large end of bolt | 0.496 in. minimum |
| Minimum thickness of bearing lug (0.060 in. from top) | 0.175 in. minimum |

---

## Repository Structure

```
Beech215PropBearing/
├── README.md               — This file
├── docs/                   — Reference documentation
│   ├── A-777.pdf           — FAA Aircraft Specification (Rev. 57, 1996)
│   ├── beech_prop_215-manual.pdf  — Beech 215 Overhaul Manual (115187A1)
│   ├── electricpropelleroperation.pdf — Electric prop operation manual
│   ├── PropArticle.pdf     — ABS article: 250-hr bearing lubrication (Mantei)
│   └── *.html              — Service facility reference pages
├── specs/                  — Engineering specifications (to be developed)
│   └── (bearing dimensional data, material specs, tolerances)
└── cad/                    — CAD models and drawings (to be developed)
    └── (STEP, DXF, FreeCAD files)
```

---

## Regulatory Framework: Owner-Produced Parts

Under **14 CFR 21.9(a)(5)**, an aircraft owner may produce a replacement part for their own aircraft without an FAA Production Approval (PMA) provided:

- The owner produces the part (or has it produced) for installation on their own aircraft
- The part conforms to its approved design (dimensions, materials, processes)
- The installing mechanic determines it's airworthy (Form 337 or logbook entry as appropriate)

This project collects and develops the technical data needed to establish "conformance to approved design" for the pitch control bearing. It does **not** create a PMA part, STC, or parts for sale.

**This repository does not constitute FAA approval of any part. All fabrication and installation decisions remain the responsibility of the aircraft owner and the certifying mechanic.**

---

## How to Contribute

This project needs:

1. **Dimensional measurements** of a serviceable B200-202 bearing (OD, ID, width, ball size, ball count, race geometry, lug dimensions and positions)
2. **Material identification** (bearing steel grade, seal material, snap ring material/spec)
3. **CAD models** — FreeCAD preferred for open-source accessibility; STEP welcome
4. **Manufacturing drawings** per ASME Y14.5 with appropriate GD&T
5. **Comparable modern bearings** — cross-reference to current-production bearing that meets or can be modified to meet the dimensional requirements
6. **Legal/regulatory input** from A&Ps and DAR/DARs familiar with owner-produced parts

If you own or have access to a 215 propeller, **measured dimensional data is the highest-priority contribution** right now.

---

## Reference Documents in This Repository

| Document | Description |
|----------|-------------|
| `A-777.pdf` | FAA Type Certificate Data Sheet A-777, Revision 57 — lists all approved propeller configurations for Beech 35 series |
| `beech_prop_215-manual.pdf` | Beech 215 Overhaul Manual (115187A1, revised Nov 1962) — complete disassembly, inspection, repair, reassembly, parts breakdown |
| `electricpropelleroperation.pdf` | Beech electric prop operation and service manual |
| `PropArticle.pdf` | ABS Newsletter article by Mark R. Mantei — practical 250-hour lubrication procedure from an owner's perspective |

---

## Related Resources

- American Bonanza Society (ABS) — technical library and member expertise
- Airborne Electronics — STC electronic prop governor replacement
- Beech Manual P/N 115187A1 — definitive technical reference (copy in `docs/`)
- FAA Type Certificate A-777 (copy in `docs/`)

---

## Aircraft Reference

This project was initiated in connection with N734B, a Beechcraft Bonanza.

---

## License

Documentation and original work in this repository is released under **Creative Commons CC BY-SA 4.0**. Contributed CAD files will carry the same license unless otherwise noted. Reference documents (Beech manuals, FAA specifications) are included for research purposes under their respective terms.
