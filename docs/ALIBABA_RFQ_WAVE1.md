# VolksMule Alibaba supplier RFQ — Wave 1

Prepared: **2026-08-31**

This file is the operational outreach packet for the first supplier-document campaign.

The goal of Wave 1 is **not to buy the vehicle** and not to lock exact components prematurely.

The goal is to obtain enough original engineering information from the highest-impact suppliers to begin real packaging and interface work.

> **Docs first. Samples second. Large orders much later.**

---

# 1. Project introduction — common supplier preamble

Use this short preamble at the beginning of supplier conversations.

> Hello. We are developing VolksMule, an early-stage compact two-seat electric utility vehicle project in the United States. The working architecture is a repairable 400-V-class LFP EV with front-primary drive, automatic on-demand rear electric traction, SAE J3400 charging, conventional 12-V low-voltage systems, and locally serviceable controls/diagnostics. We are currently qualifying component families for prototype engineering. We are not asking you to certify our completed vehicle; we are asking for the original technical information needed to determine whether your component is suitable for prototype integration. Please identify the exact manufacturer and current model/revision for any product you recommend.

For Alibaba chat, keep the first message short and send the technical list after the supplier confirms an engineering contact is available.

---

# 2. Universal document request

Unless a supplier-specific section says otherwise, request:

1. current manufacturer-issued datasheet;
2. exact model and revision;
3. dimensional drawing and STEP/3D CAD if available;
4. electrical/mechanical connector manufacturer and mating part numbers;
5. pinout;
6. communications protocol / CAN DBC or equivalent interface documentation;
7. operating-temperature range;
8. environmental/IP rating;
9. thermal derating limits;
10. relevant automotive qualification / IATF / EMC / vibration evidence;
11. failure-state behavior;
12. local diagnostic and firmware/reflash procedure where applicable;
13. sample price and sample MOQ;
14. production pricing at representative low-volume quantities;
15. lead time;
16. expected product-support/production-continuity horizon;
17. North American engineering or after-sales contact if available.

## Supplier-response rule

Marketing PDFs alone are not a technical response.

A supplier may remain in the queue while documents are incomplete, but **no architecture freeze follows from a sales claim**.

---

# 3. Wave 1A — highest packaging/electrical impact

These conversations should happen first because their dimensions and interfaces constrain the first Mule.

---

## A1. REPT BATTERO — automotive LFP cells

**Target:** 150-Ah and 171-Ah automotive BEV LFP cells

**Why now:** cell geometry, mass, power limits, compression and thermal requirements directly constrain the pack box, cooling plates, BMS channel count, series count and vehicle floor.

Detailed research:

- [ALIBABA_LFP_CELLS_MODULES.md](ALIBABA_LFP_CELLS_MODULES.md)

### First message

> We are evaluating your 150-Ah and 171-Ah LFP cells that are classified in your BEV product family for a 400-V-class passenger/utility EV prototype. We would like to qualify the actual manufacturer-direct cell, not trader stock. Can you connect us with an application engineer and provide the current automotive datasheet/drawing for both cells?

### Technical follow-up

Please provide for both candidates:

1. exact product/model code and current revision;
2. nominal/min/max cell voltage;
3. nominal capacity and test conditions;
4. cell mass and tolerance;
5. full dimensions and dimensional tolerance;
6. terminal dimensions/material/thread or welding requirements;
7. continuous charge/discharge current versus SOC and temperature;
8. pulse current capability and duration;
9. DCIR versus SOC/temperature;
10. cycle-life curves and test conditions;
11. allowable charge temperature and low-temperature charge limits;
12. compression/preload requirement and allowable swelling;
13. recommended module clamping method;
14. vent location/orientation and required clearance;
15. thermal-propagation / abuse-test information available to prototype customers;
16. recommended cooling approach / maximum cell temperature gradient;
17. automotive qualification evidence for the exact cell family;
18. QR/serial traceability method;
19. lot/batch matching data supplied with an order;
20. UN 38.3 and shipping documentation;
21. prototype quantity pricing for 8, 16 and 20 cells;
22. matched-pack pricing for roughly 120–140 cells after qualification;
23. North American sample-stock/support options.

### Hard gate

**No pack-sized order until manufacturer-issued data, lot provenance and representative-cell testing agree.**

---

## A2. Rawsuns — READ2982 e-axle + RDA350 utility inverter

**Targets:**

- READ2982-class compact independent-suspension e-axle;
- alternatives for lower-drag/rear-assist duty;
- RDA350-120-3KW onboard 120-V utility inverter.

Detailed research:

- [ALIBABA_EAXLE_CANDIDATES.md](ALIBABA_EAXLE_CANDIDATES.md)
- [ALIBABA_UTILITY_POWER_V2L.md](ALIBABA_UTILITY_POWER_V2L.md)

### First message

> We are evaluating Rawsuns for two functions in a compact 400-V-class two-axle EV prototype: (1) a READ2982-class independent-suspension drive unit for primary propulsion and possible rear-assist variants, and (2) the RDA350-120-3KW 120-V/60-Hz onboard inverter. We need engineering documentation before selecting or buying samples. Could you connect us with the e-drive and inverter application engineers?

### E-axle technical follow-up

Please provide for READ2982 and the closest recommended rear-assist alternatives:

1. STEP/3D CAD and 2D installation drawing;
2. mounting points and allowable mount loads;
3. complete assembly mass;
4. motor type;
5. rated/peak power and torque;
6. complete motor-speed/torque curve;
7. continuous power versus coolant temperature/ambient;
8. reduction ratio;
9. maximum motor/mechanical speed;
10. overspeed duration limit;
11. axle output/CV spline specification;
12. supported halfshaft/CV geometry;
13. wheel-speed versus motor-speed relationship;
14. lubricant specification and service interval;
15. bearing design life;
16. coolant flow/pressure/temperature requirement;
17. inverter option and DC operating-voltage window;
18. CAN torque-command and regen protocol / DBC;
19. torque-command watchdog/fail-safe behavior;
20. resolver/position-sensor architecture;
21. coast drag versus vehicle/e-axle speed;
22. back-EMF/open-circuit behavior with inverter disabled;
23. maximum safe wheel/e-axle speed while producing zero torque;
24. whether any model includes a mechanical disconnect;
25. diagnostic trouble codes and local service/reflash procedure;
26. sample price for one complete drive unit with inverter/required harness/connectors;
27. expected production support horizon.

### Rear-assist hard gate

> **Any permanently coupled rear unit must tolerate the Mule's full road speed while inactive, or provide a validated disconnect.**

### RDA350 inverter follow-up

For `RDA350-120-3KW`, please provide:

1. exact current datasheet/revision;
2. confirmation of 200–450-VDC input operation;
3. confirmation of 120 VAC / 60 Hz output;
4. confirmation of **continuous 3.0-kW rating** and explanation of the conflicting 1000-W field on the current public product page;
5. efficiency map;
6. continuous/pulse output current;
7. overload/inrush capability;
8. output THD/waveform specifications;
9. galvanic-isolation rating;
10. neutral/ground topology;
11. CAN protocol / hardware enable input;
12. startup/precharge requirements;
13. short-circuit/overload/overtemperature behavior;
14. IP65/environmental test evidence;
15. vibration/EMC evidence;
16. fan life/serviceability;
17. STEP drawing and connector details;
18. prototype price for 1–2 units.

---

## A3. Sumcont — alternate 250–450-V integrated drive unit

**Target:** approximately 60-kW rated / 120-kW peak integrated drive-unit family

Detailed research:

- [ALIBABA_EAXLE_CANDIDATES.md](ALIBABA_EAXLE_CANDIDATES.md)

### First message

> We are comparing compact integrated drive units for a 400-V-class two-seat utility EV. Your roughly 60-kW rated / 120-kW peak, 250–450-V family appears close to our study envelope. We need the full mechanical/electrical/application package before choosing a prototype unit.

### Ask for

- all universal e-axle documents listed for Rawsuns above;
- exact gearbox/differential architecture;
- inverter integration boundary;
- front versus rear installation options;
- mounting/CV geometry;
- coast-drag and overspeed data;
- CAN/diagnostics;
- sample pricing.

### Gate

No sample without CAD, full speed/torque map, voltage window, thermal limits and documented control interface.

---

## A4. Dilong — OBC + DC/DC + optional PDU

**Target:** CDU8KM64-class 6.6-kW OBC + ~1.5-kW 14-V DC/DC; compare 2-in-1 and 3-in-1 variants

Detailed research:

- [ALIBABA_OBC_POWER_ELECTRONICS.md](ALIBABA_OBC_POWER_ELECTRONICS.md)

### First message

> We are qualifying a 400-V-class onboard power module for a North American EV prototype using SAE J3400 charging. We are interested in your 6.6-kW OBC + 14-V DC/DC family, and we need to compare your 2-in-1 product against the PDU-integrated 3-in-1 version. Please provide the engineering package for the exact current models.

### Ask for

1. exact model numbers/revisions;
2. HV battery operating window;
3. OBC charge-output voltage/current map;
4. supported AC input voltage/current/frequency;
5. power factor/efficiency maps;
6. DC/DC continuous and peak 14-V output;
7. DC/DC thermal derating;
8. galvanic-isolation specs;
9. coolant flow/temperature/pressure requirements;
10. CAN/UDS/DBC documentation;
11. charge-enable/state-machine responsibilities;
12. interaction expected with EVCC/BMS/VCU;
13. HVIL provisions;
14. connector part numbers;
15. EMC/environmental/automotive qualification evidence;
16. CAD;
17. local reflash/diagnostics;
18. 2-in-1 sample price;
19. 3-in-1 sample price;
20. exact PDU schematic/topology for the 3-in-1 version, including fuses/contactors/precharge/service boundaries.

### Architecture gate

**If the integrated PDU cannot be understood and serviced, use the 2-in-1 OBC/DC-DC and keep power distribution transparent.**

---

## A5. MIDA — J3400/NACS vehicle charging controller

**Target:** EVCC with HomePlug Green PHY, DIN 70121 / ISO 15118 and J3400/NACS support

Detailed research:

- [ALIBABA_J3400_CHARGING.md](ALIBABA_J3400_CHARGING.md)

### First message

> We are building the vehicle side of an SAE J3400 AC/DC charging system for a 400-V-class U.S. EV prototype. Your EVCC family advertises NACS, HomePlug Green PHY, DIN 70121 and ISO 15118 support. We need to understand the exact responsibilities, interfaces and interoperability evidence for the current module.

### Ask for

1. exact EVCC model/revision;
2. standards/conformance matrix;
3. J3400-specific implementation status;
4. HomePlug Green PHY chipset/module information;
5. DIN 70121 support;
6. ISO 15118-2 support;
7. ISO 15118-20 support;
8. Plug & Charge support/status if applicable;
9. AC charging state-machine responsibilities;
10. DC fast-charge state-machine responsibilities;
11. control-pilot/proximity input/output interfaces;
12. inlet lock/temperature-sensor interfaces;
13. CAN/J1939/UDS/DBC to BMS/VCU/OBC;
14. fast-charge contactor control responsibility/boundary;
15. charger interoperability test evidence;
16. J3400/NACS charging-station test list if available;
17. offline configuration/commissioning tool;
18. offline firmware-update/recovery process;
19. CAD and connector details;
20. prototype sample price.

### Gate

**CAN alone is not DC fast charging. PLC and full charging state-machine behavior must be documented.**

---

# 4. Wave 1B — HV safety and energy-management interfaces

---

## B1. Yonggui — HV connectors / service disconnect / harness

Detailed research:

- [ALIBABA_HV_SAFETY_PLUMBING.md](ALIBABA_HV_SAFETY_PLUMBING.md)

### First message

> We are defining the 400-V-class HV interconnect for a compact EV prototype and would like your recommended automotive connector and manual service-disconnect families for approximately 300–450-V battery operation. We need loose service parts, tooling and full interface documentation rather than a sealed proprietary harness-only solution.

### Ask for

- recommended exact connector/MSD families;
- continuous-current derating versus temperature;
- voltage rating;
- touch-safe/IP rating;
- HVIL contacts/architecture;
- mating-cycle rating;
- terminal/crimp specifications;
- required tooling;
- USCAR/LV-type test evidence applicable to exact family;
- CAD;
- harness-source options;
- loose terminals/seals/repair pigtails;
- samples.

---

## B2. Chilye — Alibaba-accessible HV connectors / MSD

**Target:** HVC800-class connectors and 80–500-A service-disconnect family

Detailed research:

- [ALIBABA_HV_SAFETY_PLUMBING.md](ALIBABA_HV_SAFETY_PLUMBING.md)

### First message

> We are evaluating your HVC800-class HVIL connector family and manual service disconnects for a 400-V-class EV prototype. Please recommend the smallest automotive family that covers the final current range and provide exact test documentation, CAD, terminals and service tooling.

Use the Yonggui request list plus:

- fuse options inside MSD;
- interlock switching sequence;
- finger-safe/service-state behavior;
- low-quantity sample availability.

---

## B3. Hongfa — automotive HV contactors

**Target:** HFE82V-class family after current/fault study

Detailed research:

- [ALIBABA_HV_SAFETY_PLUMBING.md](ALIBABA_HV_SAFETY_PLUMBING.md)

### First message

> We are selecting main positive/negative and precharge switching hardware for a 300–450-V EV traction battery. We are currently evaluating the HFE82V-class automotive HVDC relay family. Please connect us with an application engineer who can size the exact relay from continuous current, peak current and fault-interruption requirements.

### Ask for

- continuous-current thermal curves;
- contact resistance;
- make/break ratings across expected DC voltage;
- short-circuit withstand;
- fault interruption capability;
- auxiliary-contact options;
- welded-contact detection approach;
- coil/economizer behavior;
- lifetime versus current/temperature;
- automotive qualification;
- CAD;
- samples.

### Gate

**Do not size a contactor from nominal current alone.**

---

## B4. Ligoo — automotive road-intent BMS

Detailed research:

- [ALIBABA_BMS_CANDIDATES.md](ALIBABA_BMS_CANDIDATES.md)

### First message

> We are evaluating an automotive 400-V-class LFP BMS for a low-volume passenger/utility EV prototype. We need a master/slave Power-BMS architecture with local diagnostics and documented vehicle interfaces. Prototype engineering access and interface documentation are as important to us as channel count.

### Ask for

1. recommended family for roughly 110–140-series LFP cells;
2. architecture diagram;
3. cell measurement accuracy versus temperature;
4. temperature-channel architecture;
5. current-sensor interface;
6. isolation-monitor interface;
7. contactor/precharge control;
8. HVIL input/state handling;
9. crash input/shutdown;
10. redundant/failsafe behavior;
11. balancing current/strategy;
12. CAN/CAN-FD/DBC;
13. diagnostic trouble codes;
14. event/logging access;
15. calibration tool;
16. offline firmware update/recovery;
17. replacement/pairing procedure;
18. automotive qualification evidence;
19. prototype master/slave kit price.

### Gate

If basic commissioning/replacement requires a supplier cloud account or undisclosed CAN behavior, the system does not meet the project architecture.

---

## B5. Suzhou Miaoyi / Mewyeah — motive-power BMS alternate

Use the Ligoo request and ask specifically which of its current 88S/90S/132S-SUV/other motive-power families best supports the eventual VolksMule electrical window.

Do **not** choose the 132S option merely because it exists; final series count follows the selected cells/e-axles/OBC/charging window.

---

# 5. Wave 1C — direct driver/chassis interface documents

---

## C1. Wayou / Jieou — accelerator pedal and physical drive selector

Detailed research:

- [ALIBABA_DRIVER_COMMANDS_INSTRUMENTS.md](ALIBABA_DRIVER_COMMANDS_INSTRUMENTS.md)

### First message

> We are selecting a simple driver command set for a left-hand-drive electric utility vehicle: a dual-channel electronic accelerator pedal and a physical P-R-N-D selector. We prefer contactless/redundant sensing and a deterministic hardwired or fully documented interface. Please recommend current passenger/EV models and provide engineering drawings/signals.

### Accelerator ask

- recommended LHD pedal;
- STEP drawing;
- pedal travel;
- pedal force/return spring curve;
- Hall/contactless sensor architecture;
- number of redundant channels;
- exact signal curves/tolerances;
- power/ground arrangement;
- connector/mating part;
- open/short/channel-disagreement behavior;
- temperature/environmental data;
- endurance-cycle data;
- automotive qualification;
- 2–5-unit sample price.

### Selector ask

Preference order:

1. physical rotary P-R-N-D knob with positive detents;
2. short conventional lever if simpler/more robust.

Ask for:

- hardwired discrete/Gray-code version if available;
- CAN/LIN version only with complete interface documentation;
- truth table/DBC;
- detent positions;
- fault behavior;
- illumination;
- CAD;
- life-cycle data;
- sample price.

---

## C2. Zhuzhou Elite — EPS

Detailed research:

- [ALIBABA_STEERING_EPS.md](ALIBABA_STEERING_EPS.md)

### First message

> We are evaluating mechanically connected EPS architectures for a compact passenger/utility EV near first-generation-CR-V scale. We are comparing P-EPS, DP-EPS and C-EPS rather than assuming rack-assist. We need preliminary packaging/load envelopes and a locally calibratable interface before selecting the steering geometry.

### Ask for

- recommended EPS classes for expected front-axle mass/28–34-in tire study envelope;
- rack/column dimensions;
- rack travel/ratio options;
- peak/continuous assist torque/force;
- assist versus temperature/speed;
- steering torque/angle sensors;
- CAN/DBC;
- calibration ownership/tool;
- failed-assist mechanical behavior;
- local diagnostics/replacement procedure;
- automotive qualification;
- prototype pricing.

### Gate

Continuous mechanical steering path remains mandatory.

---

# 6. Wave 2 — deliberately later

These are important suppliers but should not be asked to finalize components before the first packaging model gives them real vehicle parameters.

## APG / WBTL — ABS/ESC/AEB pressure control

Wait for:

- mass/CG estimate;
- wheelbase/track;
- tire candidate;
- brake sizes/caliper piston areas;
- steering/suspension architecture.

Then request a system-calibration relationship, not a generic HCU.

## Songyuan Safety / Jinheng — restraints

Wait for:

- seat reference point;
- body/pillar/roof geometry;
- door architecture;
- steering-wheel/IP geometry;
- occupant package.

Then request one coordinated two-seat restraint system.

## Freetech — AEB sensor

Engage before windshield/body freeze, after:

- windshield candidate geometry;
- camera mounting zone;
- brake/ESC supplier path;
- vehicle height/track/CG package.

## Suspension component suppliers

Engage for production pieces after hard points/loads exist.

## Glass supplier

Engage after common-windshield donor study proves whether custom glass is necessary.

---

# 7. RFQ response intake template

Create one entry per supplier response.

```text
SUPPLIER:
DATE:
CONTACT NAME / ROLE:
MANUFACTURER OR TRADER:
FACTORY LOCATION:
TARGET PRODUCT:
EXACT MODEL:
REVISION:

DATASHEET RECEIVED: YES / NO
CAD RECEIVED: YES / NO
PINOUT RECEIVED: YES / NO / N/A
CAN/DBC RECEIVED: YES / NO / N/A
QUALIFICATION EVIDENCE: YES / PARTIAL / NO
DIAGNOSTIC TOOL/PROCESS DOCUMENTED: YES / PARTIAL / NO / N/A
CONNECTOR SOURCES DOCUMENTED: YES / PARTIAL / NO

SAMPLE MOQ:
SAMPLE PRICE:
LEAD TIME:
PRODUCTION MOQ:
PRODUCTION PRICE BASIS:

OPEN QUESTIONS:
- 

RED FLAGS:
- 

ARCHITECTURE CONFLICTS:
- 

NEXT ACTION:

STATUS:
CONTACTED / WAITING / DOCS PARTIAL / DOCS COMPLETE / SAMPLE CANDIDATE / HOLD / REJECT
```

---

# 8. Document-handling rule

Every meaningful supplier response should be preserved outside the ephemeral Alibaba message thread.

For each supplier, save:

- datasheets;
- drawings;
- screenshots/quotes where necessary;
- message-derived clarifications summarized in a text record;
- model/revision identifiers;
- dates;
- sample/price terms;
- unresolved questions.

Do **not** make the project depend on being able to find the same Alibaba listing later.

---

# 9. Wave-1 success criterion

Wave 1 is successful when we have enough original engineering information to build **Revision-A interface envelopes** for:

- cells/pack;
- front/rear drive units;
- onboard charging/DC-DC;
- J3400 EVCC;
- HV connectors/contactors/MSD;
- BMS;
- driver pedal/selector;
- preliminary EPS;
- utility AC inverter.

At that point the correct next artifact is not another supplier list.

It is the **first integrated packaging/interface model of the Mule.**
