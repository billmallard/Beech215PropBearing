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

## Engineering Pathway

### Why Replacement Bearings Are Feasible

A competent bearing manufacturer can reproduce this bearing from a sample and a drawing. The metallurgy and manufacturing processes for precision thrust bearings are well understood. SAE 52100 bearing steel — the industry standard for precision bearings — is available, documented, and routinely machined by aerospace shops. This is not exotic technology.

The historical barriers have been:
- **Minimum order quantities** — bearing houses want to run thousands, not dozens
- **No engineering drawing** — someone has to produce one from a physical sample
- **FAA PMA** — required only if selling commercially; not required for owner-produced parts
- **Liability exposure** — manageable with proper documentation and the owner-produced parts pathway

### The Reverse Engineering Path

**Step 1: CMM Inspection**

A Coordinate Measuring Machine (CMM) — or a portable equivalent like a Faro articulated arm — can capture every measurable feature of a disassembled bearing to sub-0.025mm accuracy in a few hours. What you get: a feature extraction report with raceway profiles, OD/ID, radii, contact angles, cage geometry, and lug dimensions. This is the raw dimensional dataset.

For a bearing, the critical dimensions include:
- Bore diameter and OD (toleranced to 0.005mm or better)
- Raceway radius and contact angle (defines load path and fatigue life)
- Internal clearance between races and rolling elements
- Lug geometry, position, and thickness

A Creality Raptor or similar consumer 3D scanner can capture envelope and gross geometry (useful for cage design and overall envelope) but cannot capture the critical toleranced dimensions. Use the scanner for what it's good at; use precision instruments or CMM for the rest.

**Step 2: Engineering Drawing**

The CMM report feeds a formal engineering drawing produced in SolidWorks or equivalent, with:
- Full GD&T callouts per ASME Y14.5
- Material specification: SAE 52100 bearing steel, hardened and ground
- Surface finish requirements on critical race surfaces
- Proper title block with revision control

This drawing is the deliverable that everything else depends on. It's what a machine shop quotes against, what ABS would need to endorse a production run, and what a DER would want if anyone ever pursued PMA.

**Step 3: Bearing Manufacturer**

With a drawing in hand, the target is a precision machine shop specializing in small-lot custom bearings — not SKF or Timken direct (impractical minimum orders), but aerospace-capable shops that do custom work. Several exist in the US. The drawing is what they quote against.

**Step 4: First Article Inspection**

The manufacturer produces a sample. A second CMM session measures it against the drawing tolerances and against the known-good original. If it conforms, you have a reproducible part with a documented paper trail.

### The Documentation Chain

```
Physical bearing sample
    → CMM inspection report (raw measurements, traceable to NIST)
        → Engineering drawing (GD&T, material, finish)
            → Manufacturer quotation and production
                → First article inspection report
                    → Conformance to approved design established
```

This chain is what makes the installation legitimate under 14 CFR 21.9(a)(5). It is also the package that ABS would need to see before endorsing a community production run.

### Cost Estimate (Order of Magnitude)

| Activity | Estimated Cost |
|----------|---------------|
| CMM inspection | $300–600 (or a favor from a sympathetic shop) |
| Engineering drawing | $500–1,500 (or free with a sympathetic ME) |
| First article bearing (prototype) | $500–2,000 |
| First article inspection | $300–600 |
| **Total** | **~$2,000–4,000** |

A retired aerospace ME in the DFW, Wichita, or Dayton area would be a natural fit for the drawing work — they have the skills, software, and often the time, and they respond well to exactly this kind of preservation project.

### The ABS Parallel

The American Bonanza Society successfully coordinated reproduction of magnesium v-tail elevator skins — a similar situation of an unobtainium structural part with no production source. The process took time but it got done. A CMM report, a drawing, and a first article bearing would be the natural submission package for ABS consideration.

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

### Highest Priority: Dimensional Data

If you own or have access to a B200-202 bearing — serviceable or worn — **measured dimensional data is the most valuable contribution you can make.** A worn bearing is useful for capturing design intent from a disassembled sample; a serviceable bearing is the validation reference.

Critical dimensions needed from a disassembled bearing:
- Outer race OD, inner race ID, overall width
- Raceway radius and contact angle (both inner and outer)
- Ball diameter and ball count
- Internal clearance (radial and axial)
- Lug dimensions: thickness, width, bore diameter, bolt hole spacing, position relative to races
- Snap ring groove dimensions and location
- Seal groove dimensions

If you have access to a CMM or Faro arm, a full feature extraction report is ideal. If not, careful micrometer and radius gauge measurements of a disassembled bearing are a meaningful starting point.

### Other Contributions Needed

1. **Engineering drawing** — Someone with SolidWorks or similar and GD&T experience to convert a CMM report into a formal drawing per ASME Y14.5
2. **Material verification** — Confirm bearing steel grade (SAE 52100 expected), seal material, snap ring spec
3. **CAD models** — FreeCAD preferred for open-source accessibility; STEP welcome
4. **Bearing manufacturer contacts** — Small-lot precision bearing shops with aerospace capability
5. **Cross-reference search** — Any current-production bearing that meets or can be modified to meet these dimensions
6. **A&P / DER input** — Regulatory guidance on owner-produced parts documentation and airworthiness determination
7. **ABS contacts** — Anyone with a relationship at ABS who could help evaluate community interest in a coordinated production run

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
