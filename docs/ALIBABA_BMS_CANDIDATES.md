# Alibaba 400-V automotive BMS candidate screen

This document takes the VolksMule Alibaba sourcing mission into the **400-V-class battery-management system** for Prototype 1.

It follows the existing architecture:

- removable, non-structural, liquid-cooled LFP pack;
- roughly 400-V class;
- front-primary and automatic rear-assist e-axles;
- native SAE J3400 AC/DC charging;
- conventional 12-V low-voltage service ecosystem;
- local diagnostics and owner-controlled recovery.

It is subordinate to:

- [WHAT_THE_CAR_NEEDS.md](WHAT_THE_CAR_NEEDS.md)
- [WHAT_GOES_IN_THE_FIRST_MULE.md](WHAT_GOES_IN_THE_FIRST_MULE.md)
- [ALIBABA_SOURCING.md](ALIBABA_SOURCING.md)
- [ALIBABA_J3400_CHARGING.md](ALIBABA_J3400_CHARGING.md)

No candidate here is road-approved or production-selected.

> **A BMS whose voltage and current numbers fit is not necessarily an automotive BMS.**

---

# 1. Executive result

The Alibaba search produced a more useful answer than a cheap part number.

There are **two distinct BMS markets** hiding under the same search terms:

1. inexpensive high-voltage master/slave systems designed primarily for stationary ESS;
2. genuine motive-power / automotive BMS suppliers whose engineering, safety, diagnostics, and vehicle integration matter as much as the electronics.

VolksMule should therefore use a **two-track development strategy**.

## Track A — development / bench BMS

Use an open or highly documented BMS to develop:

- cell-monitoring architecture;
- contactor/precharge behavior;
- current and pack-voltage sensing;
- CAN interfaces;
- thermal-control requests;
- charging-limit logic;
- fault injection;
- pack test fixtures;
- closed-course Prototype 1 development where appropriate.

Current strongest open-development reference: **ENNOID**.

A generic JBD high-voltage BMS is useful as a low-cost ESS comparison/bench article, but the manufacturer now explicitly states that its HV V3 product is not engineered for EV motive power.

## Track B — road-intent automotive BMS

In parallel, qualify a real automotive supplier for the final road-intent pack.

Current strongest Chinese automotive supplier lead: **Ligoo New Energy**.

Current strongest Alibaba-direct motive-power lead: **Suzhou Miaoyi Technology / Mewyeah**, because Alibaba explicitly surfaces 88S, 90S, 132S SUV, 139S truck, and HEV BMS products rather than relabeled ESS hardware.

Neither is selected. Both need a serious RFQ and protocol/serviceability screen.

---

# 2. The Alibaba market: abundant hardware, mostly the wrong evidence

Current Alibaba BMS discovery pages contain many apparently suitable high-voltage products:

- 96S;
- 128S;
- 160S;
- 256S;
- 300S;
- 400–1000 V class;
- 100–300 A or higher;
- CAN;
- RS485;
- master/slave architecture;
- contactor outputs;
- insulation-monitoring claims;
- active balancing.

Representative marketplace discovery:

- https://www.alibaba.com/catalog/battery-management-systems-bms-_cid201765701
- https://www.alibaba.com/countrysearch/CN/battery-management-system.html

As screened on 2026-08-31, these pages include JBD, GCE, ENJ, JKESS, EC Smart and other high-voltage systems.

The problem is that many are explicitly sold for:

- solar storage;
- rack batteries;
- commercial/industrial ESS;
- inverter communication;
- container storage.

Those are legitimate products for their intended jobs. They are not automatically appropriate for a moving vehicle exposed to crash events, traction transients, automotive EMC, vibration, road temperature extremes, contactor weld faults, fast-charge coordination and vehicle safety-state logic.

This produces a hard sourcing rule:

> **Do not promote an ESS BMS into the road pack merely because its series count, voltage, current, CAN bus, or contactor outputs match.**

---

# 3. Do not freeze cell count around a BMS SKU

Prototype 1 is currently a **400-V-class LFP** vehicle, not a frozen 96S, 108S, 120S, 128S, or 132S vehicle.

The final cell count must be selected after reconciling:

- exact LFP cell/module voltage window;
- e-axle inverter operating range;
- OBC operating range;
- DC-fast-charge voltage window;
- maximum/minimum pack voltage;
- desired energy/capacity;
- packaging;
- service-module layout;
- thermal architecture.

Therefore:

> **Choose the pack electrical window first, then choose a BMS configuration that covers it. Do not distort the pack to fit a convenient BMS listing.**

The candidate BMS should ideally offer enough modularity that a modest series-count change does not force an architecture reset.

---

# 4. What the Prototype 1 BMS actually has to do

The BMS is not merely a cell-voltage alarm board.

The working architecture includes at least these roles.

## Cell supervision

- individual cell-voltage measurement;
- cell-temperature measurement at justified locations;
- open-wire/fault detection;
- balancing;
- distributed slave/BMU communication where used.

## Pack measurement

- pack current measurement;
- pack voltage measurement independent of summed cell voltage where practical;
- SOC estimation;
- SOH estimation/diagnostics;
- charge and discharge power/current limits.

## High-voltage safety control

- main positive/negative contactor control as architecture requires;
- precharge control;
- precharge timeout/fault detection;
- welded/stuck-contactor detection;
- HVIL monitoring/interface;
- isolation-monitoring interface or integrated IMD;
- service-disconnect awareness where useful;
- crash-triggered HV shutdown input/path;
- controlled fault shutdown;
- safe restart criteria.

## Thermal coordination

- cell-temperature limits;
- pack coolant/heater requests;
- charge/discharge derating;
- cold-charge inhibition;
- overtemperature emergency behavior.

## Vehicle communication

Documented interface with:

- VCU;
- EVCC/J3400 charging controller;
- OBC;
- front/rear inverters as required;
- instrument cluster;
- diagnostic/service tools.

## Serviceability

- local diagnostics;
- DTCs;
- offline configuration;
- offline firmware recovery/update;
- documented replacement procedure;
- no mandatory vendor cloud account to make the car function;
- exportable calibration/configuration where technically appropriate.

---

# 5. Control sovereignty

The BMS should be authoritative about the battery's instantaneous safe operating envelope.

At minimum it should publish or enforce:

- maximum charge voltage;
- maximum charge current/power;
- maximum discharge current/power;
- SOC;
- pack voltage/current;
- thermal state;
- isolation/fault state;
- contactor state;
- charge permission;
- drive/discharge permission;
- requested shutdown.

The EVCC may negotiate charging with an EVSE, and the VCU may request vehicle behavior, but neither should be able to override a BMS safety limit merely because software elsewhere wants more power.

> **The pack owns its safe limits. The rest of the car may ask; it may not command the pack to violate them.**

---

# 6. Candidate A — Ligoo New Energy automotive Power BMS

## Supplier

Ligoo New Energy Technology Co., Ltd.

Official site:

- https://en.ligoo.com/

Alibaba currently exposes Ligoo BMS as a supplier tag through third-party seller/distributor Zaozhuang Evlithium Electronic Technology Co., Ltd.:

- https://www.alibaba.com/balancing-bms-system-suppliers.html

For a safety-critical BMS, VolksMule should approach **Ligoo directly**, not silently convert a reseller listing into the engineering relationship.

## Why Ligoo moved to the top of the Chinese automotive list

Ligoo's current corporate site separates **Power BMS** from **Energy Storage BMS** and lists Power-BMS platforms at:

- 12 V;
- 48 V;
- 350/144 V;
- 600 V;
- 800 V;
- 1000 V.

The company says it supplies passenger-car, commercial-vehicle, heavy-truck and other motive-power BMS solutions.

Ligoo states that:

- it was founded in 2010;
- it has more than 16 years of BMS R&D/manufacturing experience;
- cumulative global installed base exceeded 7.5 million units as of June 2026;
- it was the first domestic BMS manufacturer to obtain functional-safety process certification;
- its automotive quality system follows vehicle-level standards including IATF 16949;
- it develops BMS, BDU and other automotive electronics in-house.

These are **manufacturer claims to verify**, but they are qualitatively different from a generic marketplace listing that only says `automotive grade`.

## Why the 600-V family is interesting

A product family labeled 600 V does not mean VolksMule has to become a 600-V vehicle.

It means the platform may have comfortable electrical headroom around a roughly 400-V-class pack, subject to exact operating-voltage range, cell-count support and sensing architecture.

## Risks

The likely challenge is not whether Ligoo can make a competent BMS.

The likely challenge is whether a small open vehicle project can obtain:

- prototype quantities;
- full CAN/CAN-FD documentation;
- UDS/DTC documentation;
- configurable calibration access;
- replacement/pairing procedure;
- offline firmware/recovery;
- sufficient interface documentation to avoid permanent vendor dependence.

An excellent proprietary OEM BMS that cannot be serviced or integrated without a supplier toolchain may still be wrong for VolksMule.

## Current verdict

**YELLOW-GREEN — strongest Chinese automotive-grade supplier lead.**

Advance to direct engineering RFQ.

---

# 7. Candidate B — Suzhou Miaoyi Technology / Mewyeah

## Alibaba evidence

Alibaba currently surfaces Suzhou Miaoyi Technology Co., Ltd. as a BMS manufacturer with products explicitly described as:

- **BMS ELECTRIC SPORT UTILITY VEHICLE (132S)**;
- **BMS vehicle (90S)**;
- **BMS for ELECTRIC CAR (88S)**;
- **BMS ELECTRIC TRUCK (139S)**;
- **BMS HEV hybrid electric vehicle**.

Representative Alibaba discovery:

- https://www.alibaba.com/vehicles-suppliers.html
- https://www.alibaba.com/electric-food-delivery-vehicle-suppliers.html

Alibaba lists BMS, battery pack, dashboard, central module and related vehicle electronics among the supplier's main products.

Third-party company-registration data identifies Suzhou Miaoyi Technology Co., Ltd. as an automotive-parts manufacturer whose business scope includes R&D, production and sale of battery-management systems and new-energy-vehicle electronic control systems.

## Why this matters

Miaoyi is the first Alibaba-native lead in this mission where the marketplace is explicitly presenting **high-series-count motive-power BMS products**, rather than asking us to infer automotive suitability from a stationary high-voltage box.

An LFP 132S system is also electrically in the general neighborhood of a 400-V-class vehicle architecture, though Prototype 1 must not freeze at 132S merely because this SKU exists.

## What is missing

Public engineering evidence is currently too thin to promote it beyond supplier-lead status.

Require:

- exact model numbers;
- cell chemistry and voltage range;
- automotive qualification evidence;
- environmental/vibration/EMC data;
- functional-safety development evidence;
- CAN/DBC documentation;
- UDS/DTC behavior;
- BDU/contactor/precharge topology;
- isolation-monitoring strategy;
- crash input/shutdown behavior;
- current-sensor architecture;
- thermal-control interfaces;
- charger/EVCC integration documentation;
- tooling and offline service path;
- actual current production/customer references for the exact platform.

## Current verdict

**YELLOW — best explicitly automotive Alibaba-direct BMS lead so far.**

Advance to RFQ; do not design around it yet.

---

# 8. Candidate C — ENNOID open BMS

## Source

- https://github.com/EnnoidMe/ENNOID-BMS
- https://www.ennoid.me/bms/gen-1

ENNOID is an open-source configurable master/slave BMS based around STM32 hardware with isolated slave communication.

Published project/product information includes:

- master/slave architecture;
- cell voltage/temperature monitoring;
- external high-current contactor control;
- configurable thresholds;
- isolated CAN;
- pack/load voltage measurement;
- precharge/predischarge control;
- current measurement;
- USB configuration/programming;
- software tooling;
- roughly 100–400 V Gen-1 operating application range;
- EV-oriented contactor mounting/integration options on the commercial Gen-1 hardware.

## Why ENNOID is strategically important

This is currently the strongest **owner-control benchmark** in the BMS screen.

The source and configuration path are inspectable. We can understand the state machine, modify interfaces, instrument it heavily, reproduce configurations, and test failure behavior without waiting for a supplier to expose a proprietary diagnostic utility.

That makes ENNOID attractive for:

- battery bench development;
- module characterization;
- CAN/VCU/EVCC integration development;
- contactor/precharge rig testing;
- fault injection;
- closed-course Mule development after an appropriate safety review.

## Why it is not automatically the road BMS

Open source does not substitute for validation.

Before entrusting a road-going 400-V pack to it we would need our own very serious evidence around:

- hardware fault containment;
- redundant/independent safety paths;
- EMI/EMC;
- automotive transients;
- vibration;
- environmental range;
- contactor-drive failure modes;
- watchdog behavior;
- cell-monitoring plausibility;
- current-sensor fault detection;
- functional-safety analysis;
- manufacturing/revision control.

## Current verdict

**GREEN development platform / YELLOW-RED road-production candidate until validated.**

Keep it in the lab/prototype track even if another supplier ultimately becomes the production-road BMS.

---

# 9. Candidate D — JBD HV V3

## Alibaba availability

Alibaba heavily exposes JBD high-voltage master/slave systems in configurations such as:

- 96S;
- 128S;
- 160S;
- 256S;
- 300S;
- up to roughly 1000 V;
- CAN/RS485;
- 100/200/300 A variants.

Representative marketplace page:

- https://www.alibaba.com/catalog/battery-management-systems-bms-_cid201765701

## Manufacturer evidence changes the answer

JBD's own current HV V3 page is explicit:

- product is for commercial/industrial stationary ESS;
- approximately 100–1000 V system range;
- up to 16S per slave board;
- CAN, RS485 and Modbus;
- insulation detection;
- precharge-related control;
- ESS-oriented certification targets including IEC 62619 and UL 1973;
- operating range published around -20 C to +65 C.

Most importantly, JBD states that the system is **not intended for motive-power EV integration**, because its safety algorithms, communication and isolation design are not engineered for automotive motive power.

Manufacturer page:

- https://www.jbdenergy.com/hv-v3-high-voltage-bms-box/68797149.html

## This is a sourcing success, not a rejection failure

Alibaba made the part look numerically plausible.

The actual manufacturer documentation told us **no**.

That is exactly how the VolksMule sourcing process is supposed to work.

## Current verdict

**RED for road/motive-power Prototype 1.**

**YELLOW as an inexpensive stationary/bench comparison article only**, if we ever have a specific test reason to own one.

Do not use it as the traction-pack BMS.

---

# 10. Benchmark — Orion BMS 2

Orion BMS 2 is not the Alibaba target; it is a useful North American off-the-shelf serviceability benchmark.

Official source:

- https://www.orionbms.com/products/orion-bms-standard/

Published features include:

- configurations from 24 through 180 series cells;
- expansion up to 800 VDC;
- charge-current and discharge-current limit calculation;
- dual programmable CAN 2.0B;
- OBD2 diagnostics;
- Windows/Linux service utility;
- wiring/installation/operation/troubleshooting documentation;
- downloadable mechanical drawings and STEP models.

As of this screen, the 96S unit is listed at approximately USD 1,225 and the 120S unit at approximately USD 1,345 before accessories.

## Why it matters

Orion demonstrates what **small-builder documentation and serviceability** can look like.

Even if an automotive Tier-1 BMS beats it on formal safety pedigree, that Tier-1 supplier should not get a free pass on documentation just because it is OEM-grade.

## Current verdict

**GREEN serviceability/integration benchmark; possible development alternative.**

Formal road-production qualification still requires its own safety/validation review.

---

# 11. Benchmark — Preh 400/800-V HV BMS

Official source:

- https://www.preh.com/en/products/e-mobility/battery-management-system/hv-bms

Preh's current HV-BMS architecture is a useful OEM benchmark because it explicitly separates:

- Battery Management Unit;
- Cell Supervising Sensor Unit;
- current/voltage sensor.

Published features include:

- 400-V and 800-V battery support;
- up to 72 cells per cell-supervising unit;
- internal isoSPI/daisy-chain communication;
- vehicle communication over CAN FD;
- optional PDU integration;
- operating environment around -40 C to +85 C;
- long-life automotive positioning.

## Why it matters

This is the architecture class our Alibaba/direct-Chinese road-intent candidates should be compared against.

We do not have to buy Preh to learn from the interfaces and decomposition that an established automotive supplier considers normal.

## Current verdict

**GREEN OEM architecture benchmark.**

---

# 12. Candidate ranking

| Candidate | Intended role | Current status | Reason |
|---|---|---|---|
| Ligoo Power BMS | Road-intent automotive supplier | **YELLOW-GREEN** | Serious motive-power product families and automotive manufacturing/safety process claims; owner-control/prototype access unknown |
| Suzhou Miaoyi / Mewyeah 88S/90S/132S/139S | Alibaba-direct automotive supplier lead | **YELLOW** | Explicit EV/SUV/truck BMS products on Alibaba; engineering evidence needs deep RFQ |
| ENNOID | Open development/bench BMS | **GREEN development** | Open architecture, configurable, inspectable, strong owner-control fit |
| Orion BMS 2 | Serviceability/development benchmark | **GREEN benchmark** | Excellent public integration/diagnostic documentation and high-series-count support |
| Preh HV BMS | OEM automotive benchmark | **GREEN benchmark** | Mature 400/800-V distributed automotive architecture |
| JBD HV V3 | ESS benchmark only | **RED motive power** | Manufacturer explicitly says not for EV motive-power integration |
| Generic 96S/128S/256S Alibaba ESS BMS | Marketplace discovery | **RED until proven otherwise** | Series count/current/CAN do not establish automotive suitability |

---

# 13. Functional-safety and automotive-evidence gate

VolksMule should not accept the phrase **automotive grade** without knowing what it means for the exact hardware/software revision.

For the road-intent BMS, request evidence covering the applicable automotive development and validation regime, including as relevant:

- ISO 26262 functional-safety process and product safety case;
- ASIL allocation/claims for the exact BMS functions, not merely a company certificate;
- IATF 16949 manufacturing site/status;
- automotive-qualified component strategy;
- EMC/emissions/immunity evidence;
- electrical-transient/load-dump/reverse-polarity behavior on the 12-V side;
- thermal cycling;
- vibration/mechanical shock;
- humidity/condensation;
- ingress/environmental protection as packaged;
- isolation dielectric testing;
- contactor-driver diagnostic coverage;
- current/voltage sensor diagnostic coverage;
- open-wire detection;
- watchdog/reset behavior;
- single-point/latent fault analysis;
- firmware configuration/revision control.

These are engineering qualification gates, not a claim that every listed standard is independently a U.S. federal certification requirement.

---

# 14. BMS + BDU/PDU boundary

Do not let supplier packaging obscure responsibility.

The final design may combine functions physically, but logically we need to understand:

```text
cells/modules
   |
   +--> cell supervision/BMU chain
   |          |
   |          v
   +-------> master BMS/BCU
                  |
                  +--> current sensor
                  +--> pack voltage sense
                  +--> isolation monitor / IMD interface
                  +--> HVIL
                  +--> crash input
                  +--> thermal requests
                  +--> CAN/CAN-FD diagnostics
                  |
                  v
               BDU/PDU
                  |
                  +--> main contactors
                  +--> precharge
                  +--> fusing
                  +--> service disconnect interface
                  +--> DC-charge path
                  +--> traction/OBC/DC-DC distribution
```

A supplier may call the integrated assembly `BMS`, `B-Box`, `BDU`, `PDU`, `HVJB`, or another name.

VolksMule needs the schematic responsibility, not the marketing noun.

---

# 15. Contactor and precharge requirements created by this screen

The BMS/BDU architecture must make the following behavior observable and testable:

1. Wake safely from 12-V power.
2. Validate pack/cell/sensor state before closing HV.
3. Verify isolation status before energization where architecture requires.
4. Close the appropriate first main contactor.
5. Precharge the downstream HV bus through a controlled resistor/path.
6. Verify bus rise and precharge timing.
7. Detect precharge short/open/timeout conditions.
8. Close the second main contactor only after valid precharge.
9. Remove/bypass precharge as designed.
10. Detect welded/stuck contactors at shutdown and startup.
11. Open HV in controlled fashion for serious faults.
12. Open/disable HV after crash input.
13. Preserve fault data for service diagnosis.
14. Refuse restart until the relevant safety conditions are satisfied.

We must be able to bench-test these states before road testing.

---

# 16. Charging interface requirements

The BMS must integrate cleanly with the J3400 EVCC screen already documented.

At minimum the vehicle needs a documented exchange for:

- present pack voltage;
- present pack current;
- SOC;
- maximum allowed charge voltage;
- maximum allowed charge current/power;
- cell/pack temperature limits;
- charge permission;
- isolation/HV fault state;
- contactor state;
- requested charge termination;
- emergency shutdown.

The BMS should not need to understand the public charging network's authentication/business logic.

The EVCC should not need to understand every cell.

The interface between them should be small, explicit, documented and testable.

---

# 17. Serviceability gate

A candidate that cannot answer these questions should not become architecture:

1. Can we obtain the CAN/DBC or a complete interface-control document?
2. Can we read all safety-relevant DTCs locally?
3. Can we replace the master BMS without a factory cloud account?
4. Can a replacement be commissioned with documented local tooling?
5. Can firmware be recovered offline?
6. Can calibration/configuration be backed up and restored?
7. Are slave/BMU addresses/replacements locally configurable?
8. Can current-sensor calibration be performed without factory authorization?
9. Can contactor/BDU diagnostics be run locally?
10. Can we obtain connector pinouts and mating-part numbers?
11. Can we buy replacement slave boards five or ten years later, or substitute them through a documented interface?
12. Is secure boot/keying designed to stop attackers without locking out the owner?

---

# 18. RFQ — Ligoo / Miaoyi / other road-intent automotive BMS suppliers

Send essentially the same engineering request to every serious candidate.

## Pack/application

1. Passenger/compact utility BEV, approximately first-generation-CR-V scale.
2. LFP chemistry.
3. Roughly 400-V class; exact series count intentionally not frozen yet.
4. Dual independent e-axles.
5. Native SAE J3400 AC/DC charging.
6. 12-V low-voltage vehicle supply.
7. Removable, non-structural liquid-cooled pack.

## Ask

1. Which exact current automotive/motive-power BMS platform fits this application?
2. Supported cell-series range?
3. Supported cell chemistries and voltage measurement range?
4. Number of cells and temperature channels per slave/BMU?
5. Master/slave physical topology?
6. Communication between slaves and master: isoSPI/daisy-chain/CAN/other?
7. Maximum pack operating voltage and dielectric withstand?
8. Pack-current sensor type/range/accuracy?
9. Pack-voltage measurement architecture?
10. Integrated isolation monitoring or external IMD interface?
11. Main-contactor outputs and driver diagnostic coverage?
12. Precharge control/state machine included?
13. Welded-contactor detection method?
14. HVIL input/interface?
15. Crash input and shutdown behavior?
16. Supported BDU/PDU products and schematic block diagram?
17. CAN and/or CAN-FD vehicle interfaces?
18. Full DBC/interface-control document available under NDA or openly?
19. UDS support and DTC list?
20. Charge-current/voltage limit message definitions?
21. J3400/ISO-15118 EVCC integration references?
22. Inverter/VCU integration references?
23. Thermal-control request outputs/messages?
24. SOC/SOH algorithm performance for LFP?
25. Cold-temperature LFP charge protection behavior?
26. Functional-safety process/certification for the exact platform?
27. ASIL target/achievement for relevant product functions?
28. IATF 16949 manufacturing site/certificate?
29. Automotive EMC/environmental/vibration test reports available?
30. Operating/storage temperature?
31. IP/environmental protection of master/slaves as supplied?
32. Hardware/firmware revision-control method?
33. Offline firmware update and brick-recovery procedure?
34. Local service/calibration software available?
35. Is an internet/vendor cloud account required for any commissioning or replacement operation?
36. Replacement master commissioning procedure?
37. Replacement slave/BMU commissioning procedure?
38. Current-sensor replacement/calibration procedure?
39. Connector supplier/part numbers and pinout?
40. 2D drawings and STEP models?
41. Prototype MOQ and price at 1 / 5 / 10 units?
42. Production pricing at 100 / 1000 units?
43. Engineering/NRE/customization charges?
44. Can a prototype engineering support agreement include CAN documentation and diagnostics?
45. Long-term supply commitment and product-change-notification process?

---

# 19. RFQ — ENNOID development platform

Before buying/configuring ENNOID for Mule bench use, verify:

1. Current supported/recommended hardware generation?
2. Exact 400-V-class series-count limit for the selected slave topology?
3. LFP cell range and calibration?
4. Current sensor options and accuracy?
5. Contactor-driver current capability and diagnostic behavior?
6. Precharge/predischarge circuit behavior?
7. External IMD integration method?
8. HVIL/crash input implementation recommendation?
9. Isolated CAN message definitions?
10. Watchdog architecture?
11. Safe-state behavior on slave communication loss?
12. Configuration backup/restore procedure?
13. Bootloader/recovery procedure?
14. Spare master/slave availability?
15. Current firmware release recommended for vehicle bench testing?
16. Known safety-critical limitations/open issues?

The point is not to pretend an open BMS is already certified. The point is to use openness to make the engineering observable.

---

# 20. Bench validation plan before any road use

Regardless of supplier, create a pack-electronics rig that can simulate or use a reduced-energy battery string and exercise the BMS/BDU safely.

Test at least:

- normal power-up;
- normal power-down;
- one cell high;
- one cell low;
- cell-sense wire open;
- temperature sensor open/short;
- overtemperature;
- undertemperature/cold-charge inhibit;
- current-sensor disagreement/fault;
- pack-voltage mismatch;
- insulation fault;
- HVIL open;
- precharge timeout;
- downstream bus short/high capacitance;
- welded positive contactor;
- welded negative contactor;
- stuck-open contactor;
- CAN loss to VCU;
- CAN loss to EVCC;
- BMU/slave communication loss;
- 12-V brownout;
- watchdog reset;
- crash input;
- charger unplug/error during charge;
- maximum-charge-current derating;
- maximum-discharge-current derating;
- emergency shutdown;
- fault logging after reset.

No road testing should be the first place we learn what the contactors do when the master loses a slave.

---

# 21. What Alibaba taught us in this phase

Alibaba did **not** fail because the first 128S high-voltage BMS listings were mostly ESS products.

It succeeded in three ways:

1. It proved high-voltage master/slave BMS hardware is broadly commoditized.
2. It exposed an explicitly automotive supplier, **Suzhou Miaoyi**, with 88S–139S motive-power products.
3. It exposed the gap between marketplace specifications and the engineering evidence a road vehicle needs.

The JBD investigation is especially valuable because the manufacturer's own documentation explicitly vetoed the tempting use case.

That is the sourcing discipline working correctly.

---

# 22. Current Prototype 1 direction

Carry forward these decisions:

1. **BMS remains a separate, explicit safety-critical subsystem.**
2. **Pack cell count remains open until the electrical window is frozen.**
3. **Distributed cell supervision + master BMS/BCU is the default architecture to investigate.**
4. **BMS owns safe charge/discharge limits.**
5. **BMS/BDU controls or directly supervises contactor and precharge safety behavior.**
6. **Isolation/HVIL/crash shutdown are first-class interfaces.**
7. **EVCC and BMS communicate through a small documented vehicle interface.**
8. **No cloud dependency for basic operation, diagnosis, replacement, or recovery.**
9. **Use ENNOID/open tooling to keep development moving and observable.**
10. **RFQ Ligoo and Miaoyi in parallel for road-intent automotive hardware.**
11. **Do not use JBD HV V3 or generic ESS BMS as the traction-pack road BMS.**
12. **Benchmark serviceability against Orion and automotive architecture against Preh.**

---

# 23. Mission conclusion

The 400-V BMS search has graduated from `find a 128S box` to an actual sourcing architecture.

The recommended next actions are:

- direct RFQ to Ligoo for a 400-V-class LFP motive-power BMS/BDU platform;
- Alibaba RFQ to Suzhou Miaoyi for the 132S SUV family and adjacent series-count platforms;
- retain ENNOID as the first open development/bench candidate;
- use Orion as the documentation/service benchmark;
- use Preh as the OEM architecture/environmental benchmark;
- explicitly reject JBD HV V3 and generic ESS high-voltage BMS for road motive power;
- build the BMS/contactor/EVCC bench rig before freezing pack or charging hardware.

With e-axle, onboard power electronics, J3400 and BMS now screened, the next Alibaba frontier should be **thermal management/HVAC**: battery coolant hardware, heat-pump compressor, cabin HVAC, PTC backup, pumps, valves, heat exchangers and the interfaces that let the battery and cabin share resources without becoming an unserviceable thermal octopus.
