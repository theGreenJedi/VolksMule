# VolksMule Alibaba procurement queue

This is the **current action index** for the detailed Alibaba / Chinese-supplier sourcing research.

The detailed research documents remain the engineering record. This file answers the simpler operational questions:

1. Who should we contact first?
2. What should we ask them for?
3. What could we plausibly buy for Prototype 1?
4. What evidence blocks a purchase?
5. What should never be bought as a generic marketplace part?

> **Nothing in this queue is a production-approved component.**

## Status legend

- **CONTACT NOW** — enough evidence exists to start an RFQ / engineering conversation.
- **DOCS FIRST** — promising hardware, but do not buy before technical documents arrive.
- **SAMPLE AFTER DOCS** — a prototype/sample purchase may make sense once interfaces/provenance are verified.
- **DONOR/BENCH ONLY** — useful for development, not current road-intent path.
- **DO NOT GENERIC-BUY** — must be integrated/calibrated/qualified as a system.
- **LOCAL PREFERRED** — Alibaba may inform price/supply, but roadside/service availability wins.

---

# Tier 1 — first supplier conversations

These suppliers most strongly constrain the physical/electrical architecture and should be contacted before detailed packaging freezes.

## 1. REPT BATTERO — automotive LFP cells

**Priority:** 1  
**Status:** CONTACT NOW → SAMPLE AFTER DOCS  
**Target:** 150-Ah and 171-Ah BEV LFP cells  
**Channel:** manufacturer-direct; verified Alibaba presence

Why first:

- manufacturer explicitly classifies these cells as BEV products;
- 150-Ah cell is directly listed by REPT on Alibaba at prototype-friendly MOQ;
- 150–175 Ah cell class naturally supports roughly 58–75 kWh 1P pack studies in the likely series-count range;
- avoids trader provenance problem.

Ask for:

- exact revisions;
- cell drawings;
- continuous/pulse power maps;
- current limits versus SOC/temperature;
- compression/swelling requirements;
- vent/orientation rules;
- lot matching data;
- serial/QR traceability;
- automotive qualification evidence;
- prototype quantity 8–20 cells, then ~130–150 matched cells;
- North American engineering/after-sales support.

Purchase gate:

**No pack-sized cell order until a manufacturer-issued datasheet, lot traceability, and representative-cell characterization agree.**

Detailed screen: [ALIBABA_LFP_CELLS_MODULES.md](ALIBABA_LFP_CELLS_MODULES.md)

## 2. Rawsuns — compact e-axles

**Priority:** 2  
**Status:** CONTACT NOW / DOCS FIRST  
**Target:** READ2982-class independent-suspension e-axle; rear-assist alternatives

Why:

- READ2982 currently best-shaped Alibaba-discovered mechanical fit;
- integrated reduction/differential/CV architecture;
- plausible front-primary role.

Ask for:

- CAD and mount points;
- driveshaft/CV interface;
- full speed/torque map;
- continuous and peak thermal limits;
- inverter/controller options;
- CAN torque/regen protocol / DBC;
- coast drag;
- back-EMF behavior;
- overspeed limits;
- bearing/lube life;
- diagnostic/reflash procedure;
- prototype pricing.

Hard gate:

**Rear-assist unit must tolerate full vehicle road speed while inactive or mechanically disconnect safely.**

Detailed screen: [ALIBABA_EAXLE_CANDIDATES.md](ALIBABA_EAXLE_CANDIDATES.md)

## 3. Sumcont — alternate integrated drive unit

**Priority:** 3  
**Status:** CONTACT NOW / DOCS FIRST  
**Target:** ~60-kW rated / 120-kW peak, 250–450-V-class 3-in-1 drive unit

Role:

- second-source drivetrain candidate;
- packaging/performance comparison against Rawsuns.

Gate:

No purchase without mechanical drawings, efficiency/thermal map, CAN documentation, speed limits, cooling specification, and diagnostics.

Detailed screen: [ALIBABA_EAXLE_CANDIDATES.md](ALIBABA_EAXLE_CANDIDATES.md)

## 4. Dilong — OBC + DC/DC + optional PDU

**Priority:** 4  
**Status:** CONTACT NOW → SAMPLE AFTER DOCS  
**Target:** CDU8KM64-class 400-V 6.6-kW OBC + 14-V/1.5-kW DC/DC + PDU; 2-in-1 alternative

Why:

- one of the strongest manufacturer-accessible onboard-power paths;
- can eliminate substantial custom power-electronics work.

Ask for:

- exact HV input window;
- AC input specification;
- OBC output current/voltage maps;
- DC/DC continuous/peak output and thermal derating;
- coolant requirements;
- CAN/UDS/DBC documentation;
- PDU schematic/topology;
- internal fusing/contactors/precharge/HVIL details;
- fast-charge path treatment;
- connector part numbers;
- CAD;
- offline reflash/diagnostics;
- sample price.

Architecture gate:

**If the PDU is a black box, use Dilong's 2-in-1 OBC/DC-DC and keep the PDU transparent.**

Detailed screen: [ALIBABA_OBC_POWER_ELECTRONICS.md](ALIBABA_OBC_POWER_ELECTRONICS.md)

## 5. MIDA — vehicle-side charging controller

**Priority:** 5  
**Status:** CONTACT NOW / DOCS FIRST  
**Target:** EVCC supporting J3400/NACS vehicle-side charging

Required features already advertised in candidate family:

- HomePlug Green PHY;
- DIN 70121;
- ISO 15118-2/-20;
- CAN/J1939/UDS;
- control-pilot wake behavior.

Ask for:

- exact standards conformance/testing;
- PLC modem/chipset;
- J3400-specific implementation status;
- AC and DC charge state machine responsibilities;
- CAN/DBC;
- BMS/VCU interface;
- charger-station interoperability evidence;
- offline configuration;
- sample hardware and engineering support.

Gate:

**A CAN-only controller is not a DC fast-charge implementation.**

Detailed screen: [ALIBABA_J3400_CHARGING.md](ALIBABA_J3400_CHARGING.md)

## 6. Yonggui — HV interconnect / service-disconnect family

**Priority:** 6  
**Status:** CONTACT NOW → SAMPLE AFTER DOCS  
**Target:** automotive HV connectors, manual maintenance switch/MSD, HV harness, PDU/BDU interface parts

Why:

- deep EV interconnect portfolio;
- IATF 16949 process claims;
- USCAR-oriented testing;
- 2D/3D engineering support;
- manual-maintenance-switch product families.

Ask for:

- 400–500-V vehicle connector recommendation;
- current/temperature derating;
- USCAR/LV215 test reports for exact family;
- HVIL architecture;
- touch-safe/IP ratings;
- terminals/crimp tooling;
- mating cycle;
- CAD;
- loose service parts;
- prototype quantities.

Detailed screen: [ALIBABA_HV_SAFETY_PLUMBING.md](ALIBABA_HV_SAFETY_PLUMBING.md)

## 7. Chilye — Alibaba-direct HV connectors/MSD

**Priority:** 7  
**Status:** CONTACT NOW → SAMPLE AFTER DOCS  
**Target:** HVC800-class connectors and 80–500-A manual service disconnect

Why:

- actual EV component manufacturer;
- direct Alibaba presence;
- low-volume accessibility;
- current HVC800 listing includes 1000 V, 250 A, HVIL, IP67/IP6K9K.

Ask for exact test reports, mating parts, terminals, service tools, CAD, derating and MSD fuse/interlock options.

Detailed screen: [ALIBABA_HV_SAFETY_PLUMBING.md](ALIBABA_HV_SAFETY_PLUMBING.md)

## 8. Hongfa — HV contactors

**Priority:** 8  
**Status:** CONTACT NOW / DOCS FIRST  
**Target:** HFE82V-class 150/200/300-A automotive HVDC relays after actual current study

Ask for:

- continuous-current thermal curves;
- break/make capability at expected pack voltage;
- short-circuit withstand;
- auxiliary contacts;
- coil economizer behavior;
- weld detection strategy;
- automotive qualification;
- CAD;
- prototype/production channel.

Gate:

**Nominal current rating alone is insufficient; fault interruption and contact-weld behavior must match the pack.**

Detailed screen: [ALIBABA_HV_SAFETY_PLUMBING.md](ALIBABA_HV_SAFETY_PLUMBING.md)

---

# Tier 2 — safety/chassis supplier conversations

## 9. Ligoo — automotive road-intent BMS

**Status:** CONTACT NOW / DOCS FIRST

Target a 400-V-class automotive Power BMS architecture with:

- master/slave topology;
- contactor/precharge control;
- pack current sensing;
- HVIL/isolation/crash interfaces;
- CAN/diagnostics;
- offline calibration/replacement.

Gate: prototype access plus interface sovereignty.

Detailed screen: [ALIBABA_BMS_CANDIDATES.md](ALIBABA_BMS_CANDIDATES.md)

## 10. Suzhou Miaoyi / Mewyeah — Alibaba-direct motive-power BMS

**Status:** CONTACT NOW / DOCS FIRST

Reason:

- explicit 88S/90S/132S SUV/139S truck/HEV BMS offerings;
- actual motive-power product families rather than generic ESS channel count.

Gate: exact automotive functional-safety/environmental evidence and full local diagnostics.

Detailed screen: [ALIBABA_BMS_CANDIDATES.md](ALIBABA_BMS_CANDIDATES.md)

## 11. Zhuzhou Elite — EPS

**Status:** CONTACT NOW / DOCS FIRST

Target:

- P-EPS / DP-EPS / C-EPS appropriate to final front geometry and steering loads;
- rack/column drawings;
- assist map ownership/calibration;
- steering torque/angle sensing;
- CAN/diagnostics;
- failed-assist behavior.

Gate: continuous mechanical steering path and local calibration/replacement.

Detailed screen: [ALIBABA_STEERING_EPS.md](ALIBABA_STEERING_EPS.md)

## 12. APG / Zhejiang Asia-Pacific — brake/ESC integration

**Status:** CONTACT NOW / ENGINEERING RELATIONSHIP REQUIRED

Target:

- hydraulic friction brake foundation;
- ESC/ABS/AEB pressure control;
- regen blending interface;
- vehicle calibration support.

This is not a catalog-parts purchase.

Detailed screen: [ALIBABA_BRAKES_ESC.md](ALIBABA_BRAKES_ESC.md)

## 13. WBTL / Bethel — alternate brake/ESC supplier

**Status:** CONTACT NOW / ENGINEERING RELATIONSHIP REQUIRED

Second source for ESC/ABS/AEB calibration and hydraulic control.

Detailed screen: [ALIBABA_BRAKES_ESC.md](ALIBABA_BRAKES_ESC.md)

## 14. Songyuan Safety — integrated restraint system

**Status:** CONTACT NOW / SYSTEM ENGINEERING REQUIRED

Ask for one coordinated two-seat package covering:

- belts;
- pretension/load limitation;
- airbags;
- restraint ECU/sensors;
- occupancy strategy;
- sled/development support;
- FMVSS-relevant validation.

Gate:

**Never mix-and-match seller airbags/pretensioners because connectors fit.**

Detailed screen: [ALIBABA_SEATS_RESTRAINTS.md](ALIBABA_SEATS_RESTRAINTS.md)

## 15. Freetech — forward safety camera / AEB

**Status:** CONTACT LATER, BEFORE BODY/GLASS FREEZE

Why timing matters:

- windshield optical zone and mount geometry affect the body/glass architecture;
- FMVSS 127 will require AEB/PAEB performance on the intended production timeline.

Ask for the minimum sensor configuration that can satisfy the U.S. performance target—camera first, radar only if necessary.

Detailed screen: [ALIBABA_SAFETY_AUTOMATION.md](ALIBABA_SAFETY_AUTOMATION.md)

---

# Tier 3 — thermal, body, wiring and commodity manufacturers

## 16. Aotecar — electric compressor / heat-pump hardware

**Status:** CONTACT NOW / DOCS FIRST

Need 300–450-V-class compressor options with:

- R1234yf compatibility;
- CAN/LIN documentation;
- compressor map;
- thermal derating;
- oil/refrigerant requirements;
- NVH;
- CAD.

Detailed screen: [ALIBABA_THERMAL_MANAGEMENT.md](ALIBABA_THERMAL_MANAGEMENT.md)

## 17. NF / EVLINK-class HV coolant heater

**Status:** DOCS FIRST → SAMPLE

Target roughly 200–440 V, 3–7 kW CAN-capable coolant heater with independent thermal safety and documented interface.

Detailed screen: [ALIBABA_THERMAL_MANAGEMENT.md](ALIBABA_THERMAL_MANAGEMENT.md)

## 18. ETOP / Wenda / Cablum / Yineng — wiring harnesses/connectors

**Status:** CONTACT AFTER ELECTRICAL DRAWINGS REV A

Supplier job:

> manufacture the harness from VolksMule-owned schematic, BOM, lengths, connector definitions and labels.

Require 100% continuity testing, crimp/process control, revision traceability and repair pigtails/terminals.

Detailed screen: [ALIBABA_LOW_VOLTAGE_NETWORK.md](ALIBABA_LOW_VOLTAGE_NETWORK.md)

## 19. ChuangJia / ChonKia — latches/handles/manual regulator/switchgear

**Status:** CONTACT AFTER DOOR ENVELOPE EXISTS

Baseline request:

- conventional latch/striker;
- mechanical interior release;
- keyed mechanical exterior entry;
- manual window regulator/crank;
- physical switch/stalk options.

Power windows/locks are optional only if they genuinely win the whole-system trade.

Detailed screen: [ALIBABA_BODY_CONTROLS_DOORS.md](ALIBABA_BODY_CONTROLS_DOORS.md)

## 20. CF Auto Parts — hinges

**Status:** CONTACT AFTER DOOR MASS/axis EXISTS

Need static/fatigue load, sag, corrosion, pin/bushing serviceability and FMVSS 206 support data.

Detailed screen: [ALIBABA_BODY_CONTROLS_DOORS.md](ALIBABA_BODY_CONTROLS_DOORS.md)

## 21. Shida / Letu / Xinqiang — door/body seals

**Status:** CONTACT AFTER SECTION GEOMETRY EXISTS

Prefer a small set of common replaceable profiles rather than bespoke decorative sealing systems.

Detailed screen: [ALIBABA_BODY_CONTROLS_DOORS.md](ALIBABA_BODY_CONTROLS_DOORS.md)

## 22. Jinjiang / Xingjie / Dongfeng JC / Meili — suspension hardware

**Status:** CONTACT AFTER HARD-POINT STUDY

- Jinjiang: arms/steering/suspension manufacturing;
- Xingjie: Gen-III hub/bearing families;
- Dongfeng JC: passive dampers;
- Meili: springs.

VolksMule owns the hard points and motion geometry; suppliers make the pieces.

Detailed screen: [ALIBABA_SUSPENSION_CORNERS.md](ALIBABA_SUSPENSION_CORNERS.md)

## 23. SYP / Xinyi-class automotive glazing

**Status:** CONTACT AFTER COMMON-WINDSHIELD DONOR STUDY

First rule:

> **Try to make the body fit an existing mass-market AS1 windshield before paying for custom glass.**

Detailed screen: [ALIBABA_VISIBILITY_HARDWARE.md](ALIBABA_VISIBILITY_HARDWARE.md)

## 24. Baolong — TPMS

**Status:** CONTACT AFTER WHEEL/TIRE/HUB SIZE NARROWS

Need direct TPMS, local sensor relearn, standard service kits and independent instrument warning.

Detailed screen: [ALIBABA_SAFETY_AUTOMATION.md](ALIBABA_SAFETY_AUTOMATION.md)

## 25. TEMB — AVAS

**Status:** CONTACT LATER / EASY INTEGRATION ITEM

Dedicated 12-V pedestrian-sound appliance; must not depend on media/infotainment audio.

Detailed screen: [ALIBABA_SAFETY_AUTOMATION.md](ALIBABA_SAFETY_AUTOMATION.md)

---

# Local / non-Alibaba preference list

Alibaba should **not** win every category.

## Tires

**LOCAL PREFERRED**

The size decision is driven by North American replacement depth:

- roughly 28–34-inch overall diameter study envelope;
- tall/narrow preference;
- real sidewall;
- full-size spare;
- common enough to replace in an ordinary town.

Alibaba may be cheaper for the first set, but it does not get to choose an orphan tire size.

Detailed screen: [ALIBABA_WHEELS_TIRES_RECOVERY.md](ALIBABA_WHEELS_TIRES_RECOVERY.md)

## 12-V auxiliary battery

**LOCAL PREFERRED**

Use a common local group size; no reason to strand the vehicle waiting for a shipped auxiliary battery.

## Main HV fuse

**TRACEABLE DISTRIBUTOR / MANUFACTURER PREFERRED**

Do not trade fault-interruption confidence for marketplace price.

## Insulation monitoring device

**BENDER-CLASS AUTOMOTIVE IMD PREFERRED**

Alibaba can compete only if an alternative proves peer automotive evidence.

## Ordinary brake consumables

Select caliper/rotor/pad dimensions to give a broad replacement ecosystem. Production parts may be sourced globally; roadside replacement availability matters.

---

# Explicit no-buy list

These items should **not** be purchased as generic Alibaba parts for road-intent Prototype 1:

- unknown airbag inflators;
- unknown pretensioners;
- random restraint ECU;
- generic ABS/ESC hydraulic controller without vehicle calibration support;
- generic AEB/ADAS 'AI box';
- ESS-only JBD HV V3 BMS as traction BMS;
- mystery '400-V CAN BMS' without motive-power evidence;
- third-party CATL/EVE cells solely because the listing says 'Grade A';
- counterfeit/gray-market branded HV fuses/contactors;
- steering rack/EPS with undocumented calibration/failure behavior;
- NACS-shaped inlet sold as proof of J3400 system compatibility;
- generic LED bulb in an unqualified reflector as headlamp architecture;
- touchscreen-only essential controls;
- cloud-required lock/start/service modules.

---

# First sample-buy sequence

This is a **research sequence**, not authorization to spend money automatically.

## Very low risk / high information

1. **Connector/MSD samples** from Chilye/Yonggui after drawings/test docs are received.
2. **Switch/knob/stalk samples** when dashboard control packaging begins.
3. **Seal profile samples** when body aperture sections exist.

## Moderate cost / bench value

4. **8–20 manufacturer-direct REPT/EVE cells** after exact data/provenance is confirmed, for incoming characterization and mechanical packaging reference.
5. **Thermal pump/heater/compressor samples** after interface documents are adequate.
6. **OBC/DC-DC sample** only after Dilong provides protocol, connector, thermal and fault documentation.

## High cost — never blind-buy

7. e-axle;
8. automotive BMS;
9. EPS;
10. brake/ESC controller;
11. restraint system;
12. AEB sensor/controller.

Those require engineering relationship/documentation first.

---

# Purchasing evidence checklist

Before any architecture-relevant Alibaba purchase, record in the repo:

- manufacturer legal name;
- seller relationship to manufacturer;
- exact model/revision;
- product URL as discovery evidence;
- manufacturer datasheet URL/copy reference;
- CAD/drawing received?;
- interface/pinout received?;
- CAN/DBC/diagnostics received where applicable?;
- environmental data received?;
- automotive qualification evidence received?;
- applicable regulatory evidence received?;
- MOQ;
- sample price;
- production price band if meaningful;
- lead time;
- replacement availability;
- alternate supplier/family;
- known blockers;
- bench-validation plan;
- BUY / DONOR / ADAPT / DESIGN status.

A screenshot or marketplace title alone is not a sourcing record.

---

# Current top ten actions

1. RFQ REPT 150/171-Ah BEV cells.
2. RFQ Rawsuns READ2982 and road-speed-safe rear-assist options.
3. RFQ Sumcont 60/120-kW 250–450-V drive unit.
4. RFQ Dilong 2-in-1 and 3-in-1 OBC/DC-DC families.
5. RFQ MIDA J3400/ISO-15118 EVCC.
6. RFQ Yonggui EV HV connector + MSD family.
7. RFQ Chilye HVC800 + MSD sample set.
8. RFQ Hongfa automotive HV contactors after preliminary current envelope is written.
9. Open BMS conversations with Ligoo and Miaoyi/Mewyeah.
10. Open EPS/brake safety-system conversations with Zhuzhou Elite and APG/WBTL.

The rest of the supplier queue should follow as packaging geometry matures.

## Operational principle

> **Alibaba is our industrial catalog and sometimes our purchasing channel. It is not our engineering authority.**

The project owns the architecture, requirements, interfaces, evidence standard and substitution strategy.
