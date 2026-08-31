# Revision-A REPT BEV cell envelope

This file converts the current public engineering data for REPT BATTERO's **150-Ah and 171-Ah LFP BEV cells** into a disciplined Prototype 1 battery-pack input.

It does **not** freeze the cell, series count, pack capacity, module layout, or cooling method.

The goal is to separate what we genuinely know from the current manufacturer material from what still requires original application-engineering data.

> **Cell dimensions are not pack dimensions. Compression, terminals, venting, cooling, busbars, sensing, insulation, crash protection and service access all belong in the pack.**

---

## 1. Current candidates

REPT's current BEV product family explicitly includes 150-Ah and 171-Ah LFP cells.

### 150-Ah family

Current REPT public product data:

- chemistry: LFP;
- capacity: 150 Ah;
- nominal/rated voltage: approximately 3.2 V on the current product page;
- marketing envelope: approximately 54 × 173 × 145 mm;
- energy density: approximately 170 Wh/kg;
- mass: approximately 2.87 kg;
- fast-charge marketing: 10–80% at 1.2C;
- application: BEV.

A detailed REPT specification dated 2023-09-14 identifies **CB54173145EA-150Ah** and gives substantially better mechanical/electrical detail.

### 171-Ah family

Current REPT public product data:

- chemistry: LFP;
- capacity: 171 Ah;
- rated voltage: 3.2 V on current product page;
- dimensions: **60 × 194 × 112 mm**;
- energy density: **188 Wh/kg**;
- mass: approximately **2.94 kg**;
- fast charge 10–80%: **1.5C**;
- application: BEV.

Current REPT English material shows a wider mass tolerance than the Chinese product page. That is another reason to request the exact current engineering revision rather than treating marketing tables as release drawings.

---

## 2. 120S1P first packaging comparison

These numbers are **raw-cell arithmetic**, not finished-pack predictions.

| Item | 150 Ah | 171 Ah |
|---|---:|---:|
| Nominal cell energy at 3.2 V | 480 Wh | 547.2 Wh |
| 120S nominal energy | **57.6 kWh** | **65.664 kWh** |
| Approx. raw-cell mass, 120 cells | **344.4 kg** | **352.8 kg** |
| Approx. raw cell volume, 120 cells | **166.9 L** using detailed 150-Ah dimensions | **156.4 L** using current 171-Ah marketing dimensions |
| Approx. gravimetric energy density from current mass | ~167 Wh/kg from detailed 150 spec | ~186 Wh/kg |
| Approx. volumetric energy density from the stated boxes | ~345 Wh/L | ~420 Wh/L |

### Why the 171-Ah cell remains especially interesting

On the currently published envelope, the 171-Ah option gives roughly **14% more nominal energy** than the 150-Ah option for only about **8.4 kg more raw cell mass across 120 cells**, while its simple bounding-box volume is actually smaller.

That makes it a strong packaging candidate.

It does **not** make it the winner yet.

We still lack an equivalent detailed 171-Ah application specification covering compression, terminal geometry, current maps, venting and thermal integration.

---

## 3. Detailed 150-Ah electrical envelope

REPT specification **CB54173145EA-150Ah, REV 01/01, dated 2023-09-14** publishes:

- nominal capacity: 150 Ah;
- nominal voltage: 3.2 V;
- operating voltage at 0–60 °C: **2.5–3.65 V**;
- operating voltage at -30–0 °C: **2.0–3.65 V**;
- standard discharge current: 50 A;
- maximum continuous discharge current: **150 A at 25±2 °C**;
- peak discharge current: **450 A for 60 s, SOC >=30%**;
- standard charge current: 50 A;
- maximum continuous charge current: **150 A at 25±2 °C**;
- peak charge current: **300 A for 60 s, SOC <=70%**;
- charge temperature: **0–55 °C**;
- discharge temperature: **-30–60 °C**;
- ACR at 1 kHz: <=0.50 mΩ.

### 120S1P electrical sanity check

At 120 cells in series:

- nominal bus at 3.2 V/cell: **384 V**;
- warm operating minimum at 2.5 V/cell: **300 V**;
- published maximum at 3.65 V/cell: **438 V**;
- cold low-end theoretical boundary at 2.0 V/cell: **240 V**.

At nominal voltage, simple current × voltage arithmetic gives approximately:

- 150 A continuous discharge: **57.6 kW**;
- 450 A / 60-s peak discharge: **172.8 kW**;
- 150 A continuous charge: **57.6 kW**;
- 300 A / 60-s peak charge: **115.2 kW**.

These are not delivered-power guarantees. Real pack power depends on cell voltage under load, SOC, temperature, busbar/cable losses and BMS limits.

### Architecture implication

A 120S1P 150-Ah pack looks credible for transient dual-e-axle demand but its published **continuous** cell current deserves careful reconciliation against:

- front e-axle continuous power;
- rear thermal-load-sharing strategy;
- highway grade / towing / hot-weather continuous power;
- HVAC and accessory loads;
- DC fast-charge targets.

Do not select motor peak power and assume the cell can sustain it indefinitely.

---

## 4. A revision inconsistency that must be resolved

Current REPT marketing material advertises the 150-Ah BEV cell at **1.2C fast charging from 10–80%**.

The detailed 2023 CB54173145EA specification publishes a maximum continuous charge current of **150 A (1C)** at 25±2 °C, with a temperature/SOC-dependent charge map.

Possible explanations include:

- a newer cell revision;
- a revised fast-charge algorithm;
- a different exact 150-Ah model sharing the same marketing family;
- marketing shorthand under defined thermal/SOC conditions.

### Rule

> **The current supplier-issued specification for the exact quoted cell revision controls.**

No pack charge-power claim should be based solely on the 1.2C marketing number.

---

## 5. Detailed 150-Ah dimensions under preload

The 2023 REPT specification gives the 150-Ah cell dimensions under **3000±200 N preload at 27% SOC**:

- thickness: **53.80±0.50 mm**;
- width: **174.26±0.50 mm**;
- shoulder height: **145.67±0.60 mm**;
- total height: **148.31±0.60 mm**.

This matters enormously.

The cell's mechanical envelope is defined in a compressed state, so a pack designer cannot simply multiply free-standing marketplace dimensions by cell count.

---

## 6. Pack preload is explicitly required

The same REPT specification states that **safety testing, cycle-life testing and system/pack design require preload**, with:

- permitted preload range: **1500–5000 N**;
- recommended preload tolerance: **±200 N**.

### Revision-A consequence

The battery enclosure/module architecture must include a controlled compression structure.

That structure needs to accommodate:

- initial preload;
- cell dimensional tolerances;
- temperature expansion;
- cycle-life swelling/creep;
- relaxation of pads/end plates/fasteners;
- manufacturing tolerance stack;
- service/reassembly procedure;
- crash-load isolation so the normal compression system is not mistaken for crash structure.

### What remains unknown

Need REPT application-engineering data for:

- preferred nominal preload within the 1.5–5.0 kN range for automotive life;
- preload vs SOC/temperature recommendation;
- expected swelling-force curve through life;
- thickness growth vs SOC and cycle count;
- allowable end-plate deflection;
- recommended compression-pad material/thickness, if any;
- whether preload is per cell face in one row or defined for a specific module stack arrangement.

Until those arrive, **3.0 kN is a dimensional test condition, not automatically the production module target.**

---

## 7. Terminal and top-cover geometry we can use

The REPT overall-dimensions drawing for CB54173145EA-150Ah shows:

- positive and negative terminals at opposite ends of the top cap;
- approximately **123.00±0.30 mm terminal center spacing**;
- terminal-pad bounding dimensions around **23.00±0.15 mm**, with surrounding top-feature dimensions around **24.50±0.20 mm**;
- top feature heights around **25–26.5 mm** as dimensioned in the drawing;
- a central top feature between the terminals consistent with the cell safety/vent region in the drawing.

### Still blocked

The available specification does **not** give enough information to release busbar or terminal hardware.

Need:

- terminal material;
- exact threaded/stud/weld interface;
- thread size/pitch if threaded;
- permitted tightening torque;
- terminal axial/radial load limits;
- busbar flatness/contact-area requirement;
- plating/contact resistance requirement;
- allowed ultrasonic/laser welding process if applicable;
- top insulation/creepage keepout;
- service replacement method.

The safety instructions explicitly say **do not weld the battery directly**. Busbar attachment therefore follows the exact approved terminal interface, not improvisation on the can.

---

## 8. Venting and orientation

The 150-Ah dimensional drawing visibly places a central top feature between the terminals, but the available text does not define:

- vent opening pressure;
- required vent keepout;
- gas volume/composition;
- flame/particle behavior;
- vent direction tolerance;
- permitted installation orientations;
- required spacing to the pack lid/busbars.

The storage guidance says **do not store upside down**, which is not enough to establish every permitted installed orientation.

### Revision-A rule

Carry the cells **upright with the top/vent region unobstructed** until REPT explicitly approves another orientation.

The pack must reserve a protected vent-management path that keeps hot gas/particles away from occupants, HV conductors and structural escape routes.

Do not design a lid directly against the top of the cell because the drawing seems flat.

---

## 9. Thermal interface is still a real blocker

The detailed specification defines charge/discharge temperature limits and temperature-dependent charge behavior, but it does **not** provide a pack cooling-interface recommendation.

Need from REPT:

- preferred cooling face(s): bottom, broad side, narrow side, or another arrangement;
- maximum allowable cell temperature gradient;
- recommended coolant/plate temperature range;
- cell thermal resistance / conductivity model;
- heat generation vs current/SOC/temperature;
- required contact pressure if a cooling plate touches a cell face;
- TIM type/thickness/compressibility recommendations;
- insulation requirements between aluminum can and cold plate;
- low-temperature heating limits;
- fast-charge thermal boundary conditions.

### Current design rule

Do **not** freeze the cold-plate geometry around a guessed cooling face.

Reserve room for liquid cooling and serviceable thermal interfaces while we obtain REPT's application data.

---

## 10. Cell case electrical isolation requires attention

The safety section states that the negative pole must not be connected to the shell and describes the shell as **positive-electric/potential** in its warning language.

Therefore the pack must treat cell cans/top hardware as electrically consequential until REPT supplies the exact insulation construction and isolation requirements.

Need:

- can electrical potential/isolation definition for the exact production revision;
- blue-film/outer insulation dielectric rating;
- required creepage/clearance between cells and grounded enclosure;
- permitted compression-contact materials;
- insulation inspection/hipot requirements after module assembly.

Do not assume the aluminum cell can is a harmless grounded mechanical surface.

---

## 11. Shipping/storage clues useful to logistics

The 2023 specification states:

- transport SOC: **10–30%**;
- normal shipment status if no special request: approximately **20–50% SOC**;
- avoid severe vibration, impact, crush, sun and rain;
- storage preferred around -10 to 40 °C within the broader specified range;
- extended idle storage beyond roughly three months is not recommended without attention.

These are useful prototype logistics notes, not a finished hazmat/import plan.

---

## 12. 171-Ah cell — what we know and what we do not

The current 171-Ah official marketing data are attractive:

- 171 Ah;
- 3.2 V;
- 60 × 194 × 112 mm;
- ~2.94 kg;
- 188 Wh/kg;
- 1.5C 10–80% fast-charge claim;
- BEV application.

But a detailed REPT 171-Ah specification comparable to CB54173145EA-150Ah was **not located in the current public research pass**.

Therefore do not import the 150-Ah cell's:

- preload range;
- terminal geometry;
- current limits;
- vent design;
- orientation rules;
- thermal assumptions;
- voltage limits

into the 171-Ah design by analogy.

They may be similar. Similar is not engineering evidence.

### 171-Ah hard document request

Ask REPT for:

1. exact model/revision;
2. full product specification;
3. 2D/3D drawing;
4. free and specified-preload dimensions;
5. required preload/swelling force curves;
6. terminal interface and torque/weld requirements;
7. vent specification and permitted orientation;
8. current/power maps vs SOC and temperature;
9. voltage limits vs temperature;
10. thermal model and preferred cooling interface;
11. automotive qualification/abuse evidence;
12. lot/QR traceability and prototype sampling process.

---

## 13. First pack packaging guidance

Revision-A CAD should carry **both** cell alternatives.

### 150-Ah model

Use the detailed compressed dimensions for an engineering cell block, but add explicit placeholders for:

- compression/end plates;
- side insulation;
- intercell spacing/pads;
- cooling interface;
- top terminal/busbar region;
- vent headspace/path;
- cell-monitor wiring;
- module lifting/service structure;
- enclosure crash/underbody protection.

### 171-Ah model

Use only a clearly labeled **provisional 60 × 194 × 112 mm marketing box** with generous overhead for the same functions.

Do not release module drawings around it until supplier mechanical data arrive.

---

## 14. Current comparison verdict

### REPT 150 Ah

**Status:** STRONG ENGINEERING BASELINE / DETAILED PUBLIC SPEC EXISTS / CARRY

Strengths:

- exact detailed cell spec found;
- explicit automotive traction standards references;
- explicit current limits;
- explicit preload requirement;
- detailed dimensional drawing;
- enough information to make Revision-A packaging materially more realistic.

Open concerns:

- ~57.6-kW nominal continuous 120S1P power from dated current limit needs whole-vehicle reconciliation;
- thermal integration data missing;
- terminal attachment details incomplete;
- current marketing 1.2C charge claim differs from dated detailed specification.

### REPT 171 Ah

**Status:** PACKAGING-FAVORITE ON CURRENT MARKETING DATA / DETAILED ENGINEERING DATA REQUIRED

Strengths:

- higher energy density;
- roughly 65.7 kWh at 120S1P;
- only modest raw cell-mass increase vs 150 Ah;
- smaller raw bounding-box volume on current published dimensions;
- current BEV product and fast-charge positioning.

Blocking weakness:

- no equivalent detailed public engineering specification found in this pass.

### Current mission choice

> **Carry both. Use the 150-Ah cell as the better-documented mechanical/electrical baseline; treat the 171-Ah cell as the leading packaging challenger pending REPT original engineering data.**

Do not let the prettier energy-density number beat documentation.

---

## 15. Sources reviewed

Research current as of **2026-08-31**:

- REPT BATTERO official 150-Ah BEV product page;
- REPT BATTERO official 171-Ah BEV product page;
- REPT BATTERO current BEV cell family matrix / passenger-vehicle brochure;
- REPT Product Specification **CB54173145EA-150Ah, REV 01/01, 2023-09-14**, including electrical limits, preload requirement and dimensional drawing.

The supplier request is also tracked in [`ALIBABA_RFQ_WAVE1.md`](ALIBABA_RFQ_WAVE1.md) and Issue #28.
