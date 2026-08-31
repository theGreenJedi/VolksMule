# VolksMule Alibaba sourcing coverage audit

Audit date: **2026-08-31**

This document answers one question:

> **Have we screened the Prototype 1 subsystem skeleton deeply enough to stop broad Alibaba archaeology and move into supplier qualification, packaging, and part selection?**

Short answer:

**Yes.**

The broad sourcing-discovery mission has now covered every major BUY / DONOR / ADAPT subsystem in [WHAT_GOES_IN_THE_FIRST_MULE.md](WHAT_GOES_IN_THE_FIRST_MULE.md), plus the DESIGN systems where Alibaba/Chinese suppliers may later fabricate VolksMule-owned geometry.

That does **not** mean parts are production-approved, selected, ordered, or road-certified.

It means the project has answered the earlier discovery question:

> **Does a credible supplier/component ecosystem exist for the architecture we want, and where should Alibaba be used versus refused?**

For the major systems, the answer is now documented.

---

# Status legend

- **SCREENED** — dedicated sourcing research exists and the correct sourcing mode is understood.
- **SCREENED / SELECTION OPEN** — supplier families exist, but exact part depends on packaging, loads, electrical window, calibration, or supplier documents.
- **DESIGN / FABRICATION PATH SCREENED** — VolksMule owns the geometry/architecture; sourcing research identifies how to manufacture it.
- **SYSTEM ENGINEERING REQUIRED** — hardware exists, but must be integrated/calibrated as a safety system rather than generic-bought.
- **COMMODITY / NO SEPARATE DEEP DIVE NEEDED** — conventional hardware can be selected during BOM work without another broad marketplace mission.

---

# 1. Basic vehicle architecture

**Status: SCREENED AT SYSTEM LEVEL**

The basic architecture is already defined by canon and the Prototype 1 skeleton:

- compact two-seat BEV MPV/SUV;
- first-generation-CR-V-ish scale;
- welded steel central safety structure;
- bolt-on cradles/modules;
- front-primary e-drive;
- automatic on-demand rear traction;
- mechanical steering path;
- hydraulic friction brakes;
- removable/non-structural 400-V-class LFP pack;
- local diagnostics and owner control.

Alibaba does not decide this architecture. The sourcing work serves it.

---

# 2. Safety cell, body structure, cradles, battery enclosure

**Status: DESIGN / FABRICATION PATH SCREENED**

Detailed screen:

- [ALIBABA_STRUCTURE_FABRICATION.md](ALIBABA_STRUCTURE_FABRICATION.md)

Decision:

- VolksMule designs crash structure, cradles and battery enclosure.
- Prototype 1 geometry-changing weldments stay local while CAD moves.
- Alibaba/Chinese IATF suppliers remain useful for machined brackets, precision pieces, tooling, later stable revisions and production quoting.

**Discovery question resolved.**

---

# 3. Doors, latches, hinges, handles, seals, windows and body controls

**Status: SCREENED / SELECTION OPEN AFTER BODY GEOMETRY**

Detailed screen:

- [ALIBABA_BODY_CONTROLS_DOORS.md](ALIBABA_BODY_CONTROLS_DOORS.md)

Decisions:

- conventional doors;
- physical exterior/interior handles;
- mechanical interior release;
- manual windows are baseline;
- keyed/mechanical locks are baseline;
- powered convenience equipment only if it genuinely wins cost/packaging/serviceability;
- FMVSS 206 hardware treated seriously rather than as trim.

Supplier ecosystem exists. Exact hardware waits for door mass/section/axis geometry.

---

# 4. Suspension, hubs, bearings, springs and dampers

**Status: SCREENED / SELECTION OPEN**

Detailed screen:

- [ALIBABA_SUSPENSION_CORNERS.md](ALIBABA_SUSPENSION_CORNERS.md)

Decisions/findings:

- VolksMule owns hard points and kinematics;
- conventional passive springs/dampers;
- common Gen-III bolt-on hub family preferred;
- MacPherson front gets first packaging study;
- supplier families exist for arms, knuckles, hubs, dampers and springs.

Next work is geometry/load/package comparison, not more broad supplier discovery.

---

# 5. Steering / EPS

**Status: SCREENED / SUPPLIER DOCUMENTS REQUIRED**

Detailed screen:

- [ALIBABA_STEERING_EPS.md](ALIBABA_STEERING_EPS.md)

Strongest lead:

- Zhuzhou Elite.

Architecture:

- rack-and-pinion;
- continuous mechanical steering path;
- electric assist;
- local diagnostics/calibration;
- P-EPS / DP-EPS / C-EPS remain packaging/load choices.

Broad discovery is complete.

---

# 6. Friction brakes / ABS / ESC / AEB pressure control

**Status: SYSTEM ENGINEERING REQUIRED**

Detailed screen:

- [ALIBABA_BRAKES_ESC.md](ALIBABA_BRAKES_ESC.md)

Decisions:

- calipers/rotors/pads/hoses are commodity/proven hardware;
- hydraulic friction brakes remain stopping foundation;
- ABS/ESC is not a generic pump purchase;
- APG and WBTL/Bethel-class suppliers require vehicle-level calibration relationship;
- regen remains layered around friction braking.

No more generic Alibaba ABS-module searching is useful.

---

# 7. Driver command path — key, accelerator, selector, brake input, cluster

**Status: SCREENED / SAMPLE AFTER DOCUMENTS**

Detailed screen:

- [ALIBABA_DRIVER_COMMANDS_INSTRUMENTS.md](ALIBABA_DRIVER_COMMANDS_INSTRUMENTS.md)

Decisions:

- physical key: LOCK/OFF -> ACC -> RUN/READY;
- dual-channel contactless accelerator pedal;
- physical P-R-N-D selector, rotary knob first study;
- physical hydraulic brake pedal;
- mechanical parking brake preferred;
- dedicated instrument cluster separate from infotainment.

Strong supplier leads:

- Wayou/Jieou for pedal/selector;
- Wuhan Green Electronic-class cluster supplier.

---

# 8. Front/rear e-axles

**Status: SCREENED / SELECTION OPEN**

Detailed screen:

- [ALIBABA_EAXLE_CANDIDATES.md](ALIBABA_EAXLE_CANDIDATES.md)

Strong leads:

- Rawsuns READ2982-class front-primary candidate;
- Sumcont alternate integrated drive unit;
- other rear-assist families remain under comparison.

Durable requirement discovered:

> The rear-assist unit must tolerate full road speed while inactive or safely disconnect.

Next work is supplier docs, mechanical packaging and full speed/thermal/CAN comparison.

---

# 9. LFP cells / modules

**Status: SCREENED / SAMPLE QUALIFICATION NEXT**

Detailed screen:

- [ALIBABA_LFP_CELLS_MODULES.md](ALIBABA_LFP_CELLS_MODULES.md)

Strongest current path:

- REPT BATTERO 150-Ah / 171-Ah automotive BEV LFP families;
- EVE as second manufacturer path.

Decisions:

- manufacturer-direct/provenance first;
- automotive BEV cell family, not ESS cell because capacity looks attractive;
- seller-defined “Grade A” is not a technical specification;
- exact series count/capacity remains open.

Broad cell-market archaeology is complete enough to request real data and samples.

---

# 10. BMS

**Status: SCREENED / TWO-TRACK QUALIFICATION**

Detailed screen:

- [ALIBABA_BMS_CANDIDATES.md](ALIBABA_BMS_CANDIDATES.md)

Paths:

- Ligoo-class automotive road-intent BMS;
- Suzhou Miaoyi/Mewyeah motive-power Alibaba path;
- ENNOID/open platform for development/bench transparency;
- Orion/Preh as documentation/architecture benchmarks.

Rejected principle:

- generic ESS BMS does not become automotive because its voltage/channel count fits.

---

# 11. HV contactors, service disconnect, HVIL, isolation, connectors, fusing

**Status: SCREENED / SAMPLE AFTER ELECTRICAL WINDOW**

Detailed screen:

- [ALIBABA_HV_SAFETY_PLUMBING.md](ALIBABA_HV_SAFETY_PLUMBING.md)

Strong leads:

- Hongfa contactors;
- Yonggui HV interconnect/service disconnect;
- Chilye Alibaba-direct connectors/MSD;
- Bender-class insulation monitoring benchmark.

The exact ratings await final pack/current/fault calculations.

---

# 12. OBC, HV-to-12-V DC/DC and PDU

**Status: SCREENED / DOCS FIRST**

Detailed screen:

- [ALIBABA_OBC_POWER_ELECTRONICS.md](ALIBABA_OBC_POWER_ELECTRONICS.md)

Strongest current lead:

- Dilong 6.6-kW OBC + 1.5-kW 14-V DC/DC family.

Architecture safeguard:

> A 3-in-1 box is only simpler if its PDU is documented and serviceable.

A 2-in-1 OBC/DC-DC with VolksMule-owned transparent PDU remains a preferred fallback.

---

# 13. SAE J3400 vehicle-side charging

**Status: SCREENED / SUPPLIER INTEROPERABILITY EVIDENCE NEXT**

Detailed screen:

- [ALIBABA_J3400_CHARGING.md](ALIBABA_J3400_CHARGING.md)

Strong lead:

- MIDA EVCC-class vehicle charging controller.

Decisions:

- native J3400 inlet;
- PLC/ISO 15118/DIN 70121-capable EVCC path;
- physical release/service path;
- Tesla network access is optional ecosystem compatibility, not architecture ownership.

---

# 14. Utility AC power / V2L / future V2H

**Status: SCREENED / RFQ NEXT**

Detailed screen:

- [ALIBABA_UTILITY_POWER_V2L.md](ALIBABA_UTILITY_POWER_V2L.md)

Working first target:

- approximately 3-kW traction-HV -> 120-V / 60-Hz onboard utility inverter.

Strongest lead:

- Rawsuns RDA350-120-3KW family, subject to datasheet discrepancy resolution.

Benchmark:

- Bel 350INV60 6-kW 120/240-V vehicle inverter.

Architecture decision:

- useful local V2L first;
- grid-interactive V2H/V2G later;
- no cloud permission to power a tool.

---

# 15. Low-voltage electrical / harness / CAN / diagnostics / VCU

**Status: SCREENED / DRAWINGS NEXT**

Detailed screen:

- [ALIBABA_LOW_VOLTAGE_NETWORK.md](ALIBABA_LOW_VOLTAGE_NETWORK.md)

Decisions:

- conventional 12 V;
- visible fuse/relay distribution;
- sealed automotive connectors;
- harness built to VolksMule-owned drawings;
- separated safety/chassis/powertrain versus infotainment domains;
- accessible diagnostics;
- VCU is a sovereignty/interface decision, not a generic marketplace computer.

Harness suppliers become relevant after Rev-A schematics exist.

---

# 16. Physical controls / HMI

**Status: SCREENED**

Covered by:

- [ALIBABA_BODY_CONTROLS_DOORS.md](ALIBABA_BODY_CONTROLS_DOORS.md)
- [ALIBABA_DRIVER_COMMANDS_INSTRUMENTS.md](ALIBABA_DRIVER_COMMANDS_INSTRUMENTS.md)
- [ALIBABA_LOW_VOLTAGE_NETWORK.md](ALIBABA_LOW_VOLTAGE_NETWORK.md)

Canon:

> **The computer does not own the vehicle.**

Frequent/basic functions use knobs, switches, stalks, levers and tactile controls. A screen may inform and configure; it is not the sole authority for ordinary vehicle operation.

No additional broad Alibaba HMI sweep is needed.

---

# 17. Climate / battery thermal management

**Status: SCREENED / SYSTEM PACKAGING NEXT**

Detailed screen:

- [ALIBABA_THERMAL_MANAGEMENT.md](ALIBABA_THERMAL_MANAGEMENT.md)

Strong paths:

- Aotecar electric compressor family;
- NF/EVLINK-class HV coolant heaters;
- commodity pumps/valves;
- battery cold plates fabricated to VolksMule geometry.

Architecture:

- modular heat-pump HVAC;
- PTC/coolant-heater backup;
- no proprietary inseparable thermal octopus unless it proves a major whole-vehicle benefit.

---

# 18. Seats / belts / airbags / restraints

**Status: SYSTEM ENGINEERING REQUIRED**

Detailed screen:

- [ALIBABA_SEATS_RESTRAINTS.md](ALIBABA_SEATS_RESTRAINTS.md)

Strongest supplier path:

- Songyuan Safety;
- Jinheng alternate.

Decision:

- seat, belt, pretensioner, airbag, sensors, controller and crash structure are one validated restraint system;
- generic marketplace airbags are not candidates.

---

# 19. Glass / lights / mirrors / rear visibility / wipers

**Status: SCREENED / DONOR GEOMETRY NEXT**

Detailed screen:

- [ALIBABA_VISIBILITY_HARDWARE.md](ALIBABA_VISIBILITY_HARDWARE.md)

Key decision:

> **Try to design around a common existing AS1 windshield before creating custom glass.**

Lighting uses complete compliant optical modules, not random bulbs in borrowed optics.

Rear camera is independent of infotainment boot/cloud.

---

# 20. Wheels / tires / spare / jack / recovery

**Status: SCREENED / SIZE SELECTION OPEN**

Detailed screen:

- [ALIBABA_WHEELS_TIRES_RECOVERY.md](ALIBABA_WHEELS_TIRES_RECOVERY.md)

Current preference:

- roughly **28–34 in overall diameter** study envelope;
- relatively tall/narrow shape;
- real sidewall;
- locally replaceable North American tire size;
- full-size spare;
- front/rear engineered recovery points.

Alibaba may win initial unit price. Local replacement availability wins the size choice.

---

# 21. Required safety automation

**Status: SCREENED / SUPPLIER INTEGRATION LATER**

Detailed screen:

- [ALIBABA_SAFETY_AUTOMATION.md](ALIBABA_SAFETY_AUTOMATION.md)

Covered:

- TPMS;
- AVAS/pedestrian sound;
- rear visibility;
- seat-belt warning architecture;
- forward sensing / AEB path.

Strong paths:

- Baolong TPMS;
- TEMB-class AVAS;
- Freetech forward-safety/AEB supplier.

Boundary:

- required safety automation is not permission to install autonomy/surveillance hardware without a job.

---

# 22. Software / local diagnostics / firmware ownership

**Status: ARCHITECTURE SCREENED; IMPLEMENTATION LATER**

Covered principally by:

- [ALIBABA_LOW_VOLTAGE_NETWORK.md](ALIBABA_LOW_VOLTAGE_NETWORK.md)
- [ALIBABA_EAXLE_CANDIDATES.md](ALIBABA_EAXLE_CANDIDATES.md)
- [ALIBABA_BMS_CANDIDATES.md](ALIBABA_BMS_CANDIDATES.md)
- [ALIBABA_J3400_CHARGING.md](ALIBABA_J3400_CHARGING.md)

Supplier gate across every ECU:

- documented messages/interfaces;
- local diagnostics;
- firmware/calibration versioning;
- offline update/recovery;
- replacement/pairing without manufacturer-cloud authorization where avoidable.

The eventual VCU/control software is a VolksMule architecture/implementation mission rather than another Alibaba commodity-shopping mission.

---

# Commodity details that do not need another broad research campaign

The following still require engineering/BOM choices, but do not justify a new “does Alibaba have this?” mission unless a problem appears:

- conventional horn;
- ordinary 12-V battery;
- standard automotive fuses/relays;
- ordinary fasteners;
- washer reservoir/pump/nozzles;
- generic service connectors and clips;
- basic interior trim panels;
- cargo tie-downs;
- roof-rack attachment hardware after structural hard points exist;
- simple cup holders/storage bins;
- ordinary ducts/vents;
- jack handle/lug tools;
- basic rubber grommets/edge trim;
- service labels and fastener covers.

These should be selected during BOM/packaging work with the same principles of local availability, multi-sourcing and repairability.

---

# What remains genuinely open

Alibaba discovery did not—and should not—answer these questions:

1. **Exact vehicle packaging and dimensions.**
2. **Exact front/rear suspension hard points.**
3. **Exact e-axle front/rear combination.**
4. **Exact tire size / hub pattern / wheel diameter.**
5. **Exact LFP cell and series count / pack capacity.**
6. **Exact steering-assist architecture and rack geometry.**
7. **Exact brake sizing and ESC calibration.**
8. **Exact common windshield/donor glazing geometry.**
9. **Exact restraint/body crash integration.**
10. **Exact HVAC loop packaging.**
11. **Exact HV current/fuse/contactor ratings.**
12. **Exact 12-V harness, fuse map and CAN message matrix.**
13. **Exact VCU software/state machines.**
14. **Vehicle-level FMVSS compliance and validation.**

Those are engineering tasks, not marketplace-search tasks.

---

# Mission transition

## Broad Alibaba archaeology: COMPLETE ENOUGH TO STOP

The next phase should no longer be:

> Search Alibaba for more stuff.

It should be:

> **Use the supplier families already found to get engineering data, then make them coexist inside the first Mule.**

The current operational source remains:

- [ALIBABA_PROCUREMENT_QUEUE.md](ALIBABA_PROCUREMENT_QUEUE.md)

---

# Next mission sequence

## 1. Supplier-document campaign

Send/RFQ the highest-architecture-impact suppliers first:

- REPT BATTERO — 150/171-Ah BEV LFP cells;
- Rawsuns — READ2982 e-axle + RDA350 120-V utility inverter;
- Sumcont — alternate drive unit;
- Dilong — OBC/DC-DC/PDU;
- MIDA — J3400 EVCC;
- Yonggui / Chilye / Hongfa — HV interconnect/contactors;
- Ligoo / Miaoyi — road-intent BMS;
- Wayou/Jieou — accelerator pedal + physical selector;
- Zhuzhou Elite — EPS.

The first purpose of outreach is **engineering documents**, not ordering parts.

## 2. Interface freeze — Revision A

Build initial interface envelopes for:

- pack voltage/current range;
- front/rear e-axle mount/CV/cooling needs;
- hub/brake/wheel/tire envelope;
- steering rack/column envelope;
- J3400 inlet;
- HVAC module/heat exchanger volumes;
- common windshield candidate geometry;
- seat/restraint package;
- 12-V/CAN architecture.

## 3. First packaging CAD

Start placing the real candidate families inside the working CR-V-scale envelope.

The goal is not beauty. It is conflict discovery:

- occupants vs battery;
- crash structure vs steering;
- e-axles vs suspension travel;
- tires vs turning circle;
- battery vs ground clearance;
- HVAC vs service access;
- cargo/sleeping platform vs rear structure;
- restraints vs pillars/roof/doors.

## 4. Sample purchases only after documentation gates

Likely early samples:

- a few REPT cells for characterization;
- accelerator pedal/selector;
- HV connectors/service disconnect/contactors;
- thermal pumps/valves/heater as justified;
- utility inverter if docs clear the discrepancy;
- selected BMS development hardware.

Large/high-cost parts wait until packaging proves they belong.

---

# Final audit verdict

**Alibaba has done its first job.**

It demonstrated that VolksMule does not require inventing an entire automotive supply chain from scratch.

Credible ecosystems exist for essentially every major solved subsystem. More importantly, the research also identified where a marketplace purchase is the **wrong** answer:

- safety cell geometry;
- restraint-system mixing;
- generic ABS/ESC;
- ESS BMS masquerading as motive power;
- generic airbags;
- generic solar inverters on the traction bus;
- undocumented black-box vehicle controllers;
- bespoke structure outsourced before geometry stabilizes.

The project can now move from **supplier discovery** to **engineering orchestration**.

That is the point of the exercise.
