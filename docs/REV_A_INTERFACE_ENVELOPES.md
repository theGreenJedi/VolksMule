# VolksMule Revision-A interface envelopes

Prepared: **2026-08-31**

This is the first bridge from supplier discovery into whole-vehicle packaging.

It does **not** freeze parts.

It records what is currently known well enough to draw a box, what is provisional, and what supplier information is still blocking useful CAD.

> **A candidate earns space in the Mule before it earns a part number.**

The governing vehicle envelope remains [HOW_BIG_THE_FIRST_MULE_SHOULD_BE.md](HOW_BIG_THE_FIRST_MULE_SHOULD_BE.md).

---

# 1. Whole-vehicle working box

Current Prototype 1 target envelope:

| Item | Revision-A target |
|---|---:|
| Overall length | **172–180 in / 4369–4572 mm** |
| Overall width, no mirrors | **68–72 in / 1727–1829 mm** |
| Overall height | **64–68 in / 1626–1727 mm** |
| Wheelbase | **101–107 in / 2565–2718 mm** |
| Track | **about 60–64 in / 1524–1626 mm** |
| Turning circle | **36 ft or less** |
| Preferred curb mass | **below 4000 lb / 1814 kg** |
| Working maximum curb target | **4200 lb / 1905 kg** |
| Working GVWR | **about 5500 lb / 2495 kg or less** |
| Payload target | **at least about 1000 lb / 454 kg** |
| Running clearance target | **>= 7.87 in / 200 mm** |
| Front/rear axle clearance target | **>= 7.09 in / 180 mm** |
| Approach target | **>= 28 deg** |
| Breakover target | **>= 14 deg** |
| Departure target | **>= 20 deg** |

These remain targets, not final production dimensions.

---

# 2. Tire / wheel envelope

Current design preference:

- **roughly 28–34 in overall tire diameter**;
- relatively tall/narrow rather than wide/low-profile;
- useful sidewall;
- snow-cutting geometry favored;
- locally replaceable North American size;
- smallest common wheel diameter that clears the final brakes;
- full-size spare.

Illustrative packaging candidates:

| Size | Approx. OD | Role |
|---|---:|---|
| 225/75R16 | ~29.3 in | common moderate-size study point |
| 215/85R16 | ~30.4 in | especially tall/narrow study point |
| 235/85R16 | ~31.7 in | taller utility/truck study point |
| 235/80R17 | ~31.8 in | 17-in fallback if brakes require more wheel |

None is frozen.

## CAD envelope rule

The first suspension/steering CAD should reserve **34-in maximum tire diameter** for conflict checking, then evaluate whether the actual production size can be smaller.

This prevents body/crash/battery geometry from accidentally making the upper end impossible before tire selection is complete.

## Width rule

Do not freeze a nominal section width merely because 215/225 initially felt comfortable. Overall diameter, sidewall, load, snow behavior, brake clearance and local availability lead the decision.

---

# 3. Battery-cell envelopes — REPT automotive BEV LFP

Manufacturer source:

- https://www.reptbattero.com/150ah-battery-cell/
- https://www.reptbattero.com/171ah-battery-cell/
- https://www.reptbattero.com/battery-cell/

## Candidate A — 150 Ah

Published manufacturer data:

- chemistry: LFP;
- application: BEV;
- nominal voltage: 3.2 V;
- capacity: 150 Ah;
- dimensions: **54 x 173 x 145 mm**;
- mass: **2.87 kg**;
- energy density: 170 Wh/kg;
- published 10–80% fast-charge figure: 1.2C.

### Cell-only series studies

| Count | Nominal energy | Cell mass | Cell geometric volume |
|---:|---:|---:|---:|
| 120S | ~57.6 kWh | ~344 kg | ~163 L |
| 128S | ~61.4 kWh | ~367 kg | ~173 L |
| 132S | ~63.4 kWh | ~379 kg | ~179 L |

These exclude busbars, compression, cooling plates, insulation, BMS, contactors, enclosure, shields and service clearances.

## Candidate B — 171 Ah

Published manufacturer data:

- chemistry: LFP;
- application: BEV;
- nominal voltage: 3.2 V;
- capacity: 171 Ah;
- dimensions: **60 x 194 x 112 mm**;
- mass: **2.94 kg**;
- energy density: 188 Wh/kg;
- published 10–80% fast-charge figure: 1.5C.

### Cell-only series studies

| Count | Nominal energy | Cell mass | Cell geometric volume |
|---:|---:|---:|---:|
| 120S | ~65.7 kWh | ~353 kg | ~156 L |
| 128S | ~70.0 kWh | ~376 kg | ~167 L |
| 132S | ~72.2 kWh | ~388 kg | ~172 L |

## First packaging conclusion

The 171-Ah candidate is especially interesting because its published cell geometry provides **more nominal energy than the 150-Ah cell while using slightly less raw cell volume**, at only a modest cell-mass increase.

That does not make it selected. Power capability, compression, thermal behavior, low-temperature charging, current limits, cost and provenance still matter.

## Illustrative lattice sanity check — not a module design

A purely geometric 12-cell stack would be approximately:

### 150 Ah

- 12 x 54 mm = 648 mm stack length;
- 173 mm second dimension;
- 145 mm cell height.

Ten such 12-cell groups could geometrically fit in a rough 2 x 5 lattice around **1296 x 865 mm** before module walls, cooling, compression, electrical clearance and service structure.

### 171 Ah

- 12 x 60 mm = 720 mm stack length;
- 194 mm second dimension;
- 112 mm cell height.

Ten such groups in a rough 2 x 5 lattice would be around **1440 x 970 mm** before all real pack overhead.

This is only a sanity check showing that a roughly 60–66-kWh 120S cell field is not obviously incompatible with the current vehicle footprint.

**Do not infer final module count or orientation from this illustration.**

## Missing before pack CAD can advance beyond boxes

- exact min/max cell voltage under automotive operating limits;
- continuous/pulse current map;
- DCIR map;
- compression/preload requirement;
- swelling allowance;
- terminal details;
- vent clearance;
- cooling recommendation;
- low-temperature charge limits;
- abuse/propagation information.

These are Wave-1 RFQ items.

---

# 4. Front-primary e-axle envelope — Rawsuns READ2982

Manufacturer source:

- https://www.rawsuns.com/ev-transaxle/electric-axle/

Published data:

- independent-suspension CV e-axle;
- total assembly mass: **62 kg**;
- rated/peak motor power: **55 / 110 kW**;
- rated/peak motor torque: **110 / 270 Nm**;
- rated/peak motor speed: **4775 / 14000 rpm**;
- single reduction: **11.93:1**;
- wheel-end maximum output torque: **2982 Nm**.

## Revision-A status

**Performance envelope: usable for study.**

**Physical box: BLOCKED.**

Rawsuns' public page does not provide enough mounting/CV/CAD dimensions to allocate a responsible physical volume.

### CAD action

Reserve a provisional generic front drive-unit zone but mark it **DO NOT FREEZE** until STEP/installation drawings arrive.

Do not move the front axle, steering rack or battery merely to fit an invented drive-unit box.

---

# 5. Rear-assist e-axle envelope

Rawsuns READ2624 published data:

- independent-suspension CV e-axle;
- mass: **60 kg**;
- rated/peak power: **30 / 60 kW**;
- rated/peak torque: **90 / 220 Nm**;
- rated/peak speed: **3183 / 10000 rpm**;
- reduction: **11.93:1**.

## Known conflict

With a roughly 28-in tire, the 10,000-rpm motor-speed limit corresponds to only roughly 70 mph wheel speed.

Therefore READ2624 cannot be assumed to remain permanently coupled on a faster Mule.

## Rear requirement

A rear-assist candidate must demonstrate one of:

1. sufficient full-road-speed inactive motor/mechanical capability;
2. a mechanical disconnect;
3. a different reduction ratio;
4. another validated architecture that prevents overspeed/back-EMF/failure while inactive.

## Physical box

**BLOCKED pending CAD/drawings.**

---

# 6. Alternate drive-unit envelope — Sumcont

Public Sumcont material confirms the company supports passenger/commercial EV power systems including motors/controllers, drive axles, VCU, PDU, BMS and related integration.

Reference:

- https://en.sumcont.com/About.html
- https://en.sumcont.com/Service.html

The previously screened approximately 60-kW-rated / 120-kW-peak, 250–450-V drive family remains an alternate.

## Revision-A status

Electrical/performance concept: **candidate**.

Physical dimensions / exact mass / CV geometry: **BLOCKED pending exact-model package**.

Do not use a generic motor diameter from another Sumcont product as the 3-in-1 drive-unit envelope.

---

# 7. OBC + 12-V DC/DC envelope — Dilong DA8KM22A

Manufacturer sources:

- https://en.dilongkeji.com/html/product/166_1.html
- https://www.powerdilong.com/products/dilong-integrated-charger-2-in-1-6.6kw-obc-and-1.5kw-dcdc-combo-unit-for-electric-vehicle

Published data for the liquid-cooled 2-in-1 family includes:

- OBC: 6.6 kW;
- AC input: 85–264 VAC, nominal 220 VAC;
- HV family supports 400-V-class variants;
- example 400-C variant output window: **300–550 VDC**;
- DC/DC: **1.5 kW**;
- LV output: **14 VDC** family;
- CAN control;
- IP67;
- liquid cooling;
- dimensions: **380 x 260 x 108 mm**;
- mass: approximately **10 kg** on the detailed product page;
- published efficiency: >=94%.

## Revision-A packaging box

Reserve at least:

**400 x 280 x 130 mm**

for first collision/service routing study, before connectors, hose bends, mounting brackets and service-tool clearance are finalized.

That margin is provisional—not a supplier specification.

## Why 2-in-1 is currently favored for packaging study

The corresponding CDU8KM64 3-in-1 OBC + DC/DC + PDU is published around:

- **501 x 380 x 150 mm**;
- 6.6-kW OBC + 1.5-kW DC/DC + PDU;
- IP67;
- CAN;
- liquid cooled.

The 3-in-1 is dramatically larger.

Until the PDU architecture is documented and proves worthwhile, **Revision A should package the smaller 2-in-1 DA8KM22A first and reserve a separate transparent HV distribution zone**.

---

# 8. HV distribution / BDU envelope

Exact physical box remains open.

Revision-A function block must reserve space/access for:

- main positive contactor;
- main negative contactor;
- precharge relay/contactor;
- precharge resistor;
- main pack fuse;
- current sensor;
- insulation monitor;
- service disconnect interface;
- HVIL routing;
- busbar/harness exits;
- low-voltage service connector;
- visible/testable measurement points where safe/appropriate.

Supplier families already screened:

- Hongfa contactors;
- Yonggui / Chilye HV interconnect/MSD;
- Bender-class insulation monitor.

## Rule

Do not package this as an anonymous sealed “PDU box” until the topology and service boundaries are known.

---

# 9. J3400 / EVCC envelope

MIDA public source:

- https://www.evmida.com/products/best-evcc-controller-dc-fast-charger-for-ev-trucks-and-buses/

Current public EVCC capabilities include:

- HPGP 1.1;
- SLAC;
- DIN SPEC 70121;
- ISO 15118-2 AC/DC;
- ISO 15118-20 AC/DC EIM/PnC;
- bidirectional communication support;
- CAN 2.0B;
- J1939;
- UDS;
- NACS support claimed on current product page;
- integrated flash bootloader.

## Important Revision-A conflict

MIDA's current public EVCC is described as designed for a **24-V vehicle environment**.

VolksMule baseline low voltage is **12 V**.

### Resolution options

Preferred order:

1. MIDA provides a 12-V automotive variant;
2. use a small dedicated automotive 12->24-V converter for the EVCC;
3. choose another EVCC with equivalent PLC/ISO support and native 12-V power.

**Do not change the entire vehicle low-voltage architecture for this single controller.**

## Physical envelope

**BLOCKED** — current public page does not provide dimensions sufficient for packaging freeze.

## J3400 inlet

Also **BLOCKED pending exact inlet family and CAD**.

Body charge-port geometry must remain open until inlet, lock, temperature sensing, cable bend radius and emergency release are defined.

---

# 10. Utility AC inverter envelope — Rawsuns RDA350-120-3KW

Manufacturer source:

- https://www.rawsuns.com/on-board-household-appliance-inverter-1kw-20kw/

Published current family data:

- model designation: RDA350-120-3KW;
- nominal input: **350 VDC**;
- published input range: **200–450 VDC**;
- output: **120 VAC / 60 Hz**;
- dimensions: approximately **365 x 230 x 104 mm**;
- mass: **10 kg**;
- forced-air cooling;
- CAN communication;
- IP65.

## Documentation conflict

The manufacturer page's 3-kW model row includes a contradictory **1000-W output-power field**.

Therefore:

- physical envelope may be used provisionally;
- electrical 3-kW rating may **not** be frozen until exact datasheet confirms it.

## Revision-A packaging box

Provisionally reserve around:

**390 x 260 x 140 mm**

including preliminary air/connector/service allowance.

Do not place it where mud/water exposure or blocked fan flow turns an IP65 box into an installation failure.

---

# 11. Utility inverter OEM benchmark — Bel 350INV60

Manufacturer source:

- https://www.belfuse.com/products/power-supplies/dc-ac-inverters/350inv60-120-240-9g

Published:

- 240–430 VDC input;
- 6 kW;
- 120/240 VAC;
- liquid cooled;
- CAN;
- IP65/IP67;
- dimensions **384 x 374 x 163 mm**.

This box is retained in CAD only as a **worst-case mature-COTS comparison envelope**, not a likely Prototype 1 purchase at present cost.

If a low-cost Chinese unit cannot meet basic safety/environmental requirements, the architecture remains valid; the sourcing problem is simply unsolved at the preferred price.

---

# 12. Thermal-management envelope

Existing sourcing screen:

- [ALIBABA_THERMAL_MANAGEMENT.md](ALIBABA_THERMAL_MANAGEMENT.md)

Revision-A must reserve distributed space for:

- HV electric compressor;
- cabin evaporator/blower/HVAC box;
- front heat exchanger/condenser/radiator area;
- battery chiller/heat exchanger as required;
- PTC/coolant heater;
- pumps;
- valves;
- expansion/reservoir/degas provision;
- refrigerant service ports;
- coolant fill/drain/service access;
- battery cold plates;
- e-axle/inverter coolant branches.

## Status

System family: **known**.

Exact box dimensions: **not frozen**.

Do not create one giant central thermal-module envelope. Package serviceable modules and hose routes.

---

# 13. Steering envelope

Existing screen:

- [ALIBABA_STEERING_EPS.md](ALIBABA_STEERING_EPS.md)

Revision-A architecture:

- rack and pinion;
- collapsible column;
- continuous mechanical path;
- EPS assist;
- physical steering wheel;
- steering-angle sensing for ESC/AEB.

First comparison remains:

- P-EPS;
- DP-EPS;
- C-EPS if crash/column package makes sense.

## Physical envelope

**BLOCKED pending Zhuzhou Elite candidate drawings and first front-suspension hard-point study.**

Do not freeze front cradle rails until rack position and full tire steering-lock envelope coexist.

---

# 14. Suspension / wheel-end envelope

Existing screen:

- [ALIBABA_SUSPENSION_CORNERS.md](ALIBABA_SUSPENSION_CORNERS.md)

Front first study:

- conventional MacPherson geometry;
- Gen-III bolt-on hub with ABS encoder;
- ordinary ball joint/control arm;
- passive coil/damper;
- anti-roll bar only if handling requires.

Rear:

- compact multi-link/trailing-link versus wishbone comparison remains open.

## Required CAD sweeps

At each corner model:

- full jounce;
- full rebound;
- maximum steering lock front;
- 34-in tire conflict envelope;
- CV angle/plunge;
- brake caliper/wheel barrel clearance;
- snow/mud chain-clearance consideration if desired;
- fender/body clearance;
- shock/spring service path.

---

# 15. Brake envelope

Architecture:

- hydraulic four-wheel discs;
- supplier-calibrated ABS/ESC/AEB pressure control;
- conventional service friction parts;
- mechanical parking-brake retention preferred.

Physical sizes remain **BLOCKED** by:

- final GAWR;
- tire rolling radius;
- wheel diameter;
- target deceleration/thermal analysis;
- ESC supplier relationship.

## Rule

Wheel diameter cannot freeze before brake rotor/caliper envelope is known, and brake size cannot be inflated merely to justify a larger wheel.

---

# 16. Windshield / visibility envelope

Existing screen:

- [ALIBABA_VISIBILITY_HARDWARE.md](ALIBABA_VISIBILITY_HARDWARE.md)

Revision-A priority:

**Select several common existing AS1 windshield families and import their real geometry into CAD before designing A-pillars/cowl/roof opening around custom glass.**

This is currently one of the largest body-geometry blockers.

Required candidate data:

- glass overall outline;
- curvature / scan/CAD if obtainable;
- installed angle;
- ceramic/frit/bonding zone;
- wiper park/sweep compatibility;
- camera/AEB optical zone;
- local North American replacement depth.

Do not draw a beautiful bespoke windshield and then ask who can make it.

---

# 17. Occupant / seat / restraint envelope

Existing screen:

- [ALIBABA_SEATS_RESTRAINTS.md](ALIBABA_SEATS_RESTRAINTS.md)

Revision-A must show:

- two occupied seating envelopes;
- manual seat fore/aft adjustment range;
- H-point/SgRP study position;
- head clearance;
- steering/pedal reach;
- belt upper/lower anchor paths;
- frontal/side-airbag deployment zones;
- passenger occupancy/child-seat strategy;
- front-passenger tether anchorage provision;
- door/side-structure intrusion space.

Exact seat/restraint hardware remains blocked until the body package is real enough for Songyuan/Jinheng engineering discussion.

---

# 18. Low-voltage / CAN envelope

Baseline:

- normal replaceable 12-V battery;
- HV-to-14-V DC/DC;
- visible fuse/relay centers;
- documented CAN/CAN-FD;
- diagnostic connector;
- separate safety/chassis/powertrain roles from infotainment;
- physical key;
- physical controls.

Revision-A electrical drawing should begin with **functional network blocks**, not detailed harness lengths.

Required blocks:

- VCU;
- BMS;
- front inverter/e-axle;
- rear inverter/e-axle;
- ABS/ESC;
- EPS;
- restraint controller;
- EVCC;
- OBC/DC/DC;
- cluster;
- thermal controllers;
- body lighting/wiper functions;
- infotainment gateway boundary.

## 24-V exception register

MIDA EVCC is the first known candidate that presently requests 24 V.

Create no generalized 24-V bus yet.

If retained, give it the smallest deliberate conversion path required.

---

# 19. Driver controls envelope

Current baseline:

- physical keyed switch: LOCK/OFF -> ACC -> RUN/READY;
- physical accelerator pedal;
- physical hydraulic brake pedal;
- physical rotary P-R-N-D selector first study;
- physical mechanical parking brake;
- dedicated cluster;
- knobs/switches/stalks for lights, wipers, HVAC/defrost, hazards and other frequent functions.

Wayou/Jieou pedal/selector physical drawings remain a small but important cockpit blocker.

Because these are relatively inexpensive sample candidates, they may be among the earliest hardware purchases after documentation review.

---

# 20. Known hard blockers for first integrated CAD

The following missing information should be treated as active blockers rather than silently guessed:

## Highest priority

1. **READ2982 installation/CAD envelope and CV interface.**
2. **Rear e-axle candidate CAD + full-speed inactive behavior.**
3. **REPT exact engineering/compression/terminal/thermal data.**
4. **Several real common-windshield geometries.**
5. **Preliminary steering rack/EPS dimensions.**
6. **Seat/occupant reference envelope.**

## Medium priority

7. Exact J3400 inlet CAD and cable bend radius.
8. MIDA EVCC dimensions and 12-V option answer.
9. HV BMS master/slave physical envelopes.
10. HVAC compressor/HVAC-box dimensions.
11. Brake rotor/caliper size after first axle-load estimate.
12. HV BDU/PDU packaging after first current/fault study.

## Already usable as real boxes

- REPT 150/171 cell geometry;
- Dilong DA8KM22A 2-in-1 dimensions;
- Dilong CDU8KM64 3-in-1 comparison dimensions;
- Rawsuns RDA350 utility-inverter physical envelope;
- Bel 350INV60 benchmark envelope;
- whole-vehicle size/weight targets;
- maximum tire envelope.

---

# 21. Revision-A packaging order

Do not draw the body shell first.

Recommended CAD order:

1. wheelbase / track / 34-in tire sweep boxes;
2. two occupied front-seat envelopes;
3. 120S REPT 150-Ah and 171-Ah alternative cell-field boxes;
4. approximate crash-structure/battery-protection zones;
5. front/rear axle centerlines;
6. placeholder e-axle no-go zones until supplier CAD arrives;
7. front MacPherson / steering-lock workspace;
8. cargo floor and ~6-ft sleeping/tool-platform target;
9. Dilong OBC/DC-DC box + HV distribution service zone;
10. thermal service zones;
11. J3400 charge-port zone;
12. utility-inverter zone;
13. windshield/cowl/A-pillar geometry only after common-glass candidates are loaded;
14. refine structure around the actual systems rather than styling around empty space.

---

# 22. Revision-A success criterion

Revision A does not need to prove the final Mule.

It succeeds when it can answer:

- Can ~60–70 kWh of automotive LFP fit without eating cargo, occupants or ground clearance?
- Can both e-axles coexist with real independent suspension and useful steering angles?
- Can the vehicle stay within the CR-V-scale exterior box?
- Can it retain roughly 60 ft3 useful cargo target and a 6-ft sleeping/tool platform?
- Can the battery remain removable/non-structural?
- Can the major electronics/thermal modules be serviced without dismantling the vehicle?
- Can a tall/narrow 28–34-in tire envelope coexist with turning circle and off-road clearances?
- Can common windshield geometry preserve good outward visibility?
- Can the safety systems be packaged without turning the whole car into a proprietary computer?

If the answer to one is no, Revision A has done its job: it found the conflict early.

> **The next Mule exists first as a set of boxes that do not lie to each other.**
