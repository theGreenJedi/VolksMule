# Alibaba simple instrument-cluster screen

Research date: **2026-09-01**

This document screens the Prototype-1 driver instrument cluster after the physical-stalk work.

The target is deliberately conservative:

> **The driver gets the information and telltales required to operate the vehicle safely. The instrument cluster is not the infotainment computer.**

A dead navigation / media / general-purpose computer must not remove the speedometer, required telltales, drive state, basic battery information or critical warnings.

---

## 1. Architecture verdict

Carry a compact, independent **automotive instrument cluster** with:

- a clearly legible vehicle-speed indication;
- dedicated / persistent telltales where regulation or safety requires them;
- a modest central LCD/TFT area for variable information;
- documented CAN inputs for vehicle data;
- local 12-V power and wake behavior;
- local dimming / brightness control;
- no Android / CarPlay / navigation requirement;
- no cloud account;
- no dependency on the center infotainment display;
- no authority over propulsion, brakes, steering or charging simply because it displays their status.

The cluster is a **safety HMI endpoint**, not a vehicle master computer.

---

## 2. Why one giant software canvas is the wrong baseline

A full-width premium digital cockpit is easy to find on Alibaba, but it creates little value for Prototype 1 and can create unnecessary failure modes:

- slow boot;
- complex GPU / operating-system stack;
- proprietary graphics software;
- expensive display replacement;
- greater sunlight / thermal burden;
- greater temptation to move essential controls into menus;
- more difficult long-term firmware support.

Prototype 1 instead benefits from a small amount of display real estate used well.

A mixed architecture is attractive:

> **persistent driving essentials + dedicated telltales + small reconfigurable information area.**

---

## 3. FMVSS 101 strongly supports dedicated critical telltales

Current 49 CFR 571.101 governs the location, identification, color and illumination of motor-vehicle controls, telltales and indicators.

References:

- https://www.law.cornell.edu/cfr/text/49/571.101
- https://ecfr.io/Title-49/Section-571.101

One particularly useful architecture constraint is the rule governing **common display space**.

FMVSS 101 identifies critical telltales including brake-system malfunction, airbag malfunction, low tire pressure, ESC malfunction, passenger-airbag-off, high beam, turn signal and seat belt as telltales that cannot simply share one common cycling display space in the ordinary way.

This is a good reason not to design the entire legal / safety indication system as one generic screen page.

### VolksMule implication

Carry dedicated or otherwise compliant persistent indication zones for the required critical telltales.

The final exact telltale set must follow the complete VolksMule rules map and the actual installed systems, including the applicable requirements associated with:

- brake / ABS / ESC;
- restraint / airbag system;
- TPMS;
- turn signals / high beam / exterior lamps;
- seat-belt reminders;
- propulsion / ready / gear-state indications as applicable;
- charging / electrical faults where vehicle-level engineering requires them.

Do not freeze the graphic art until the regulatory implementation table is reconciled.

---

## 4. Preferred information hierarchy

### Always visible while driving

At minimum carry clear space for:

- vehicle speed;
- selected drive state / direction;
- propulsion-ready state;
- traction-battery state of charge;
- critical dedicated telltales;
- odometer / distance record as required by the final implementation.

### Simple variable display

Use the small central information area for useful secondary data such as:

- estimated range;
- trip distance;
- battery power / regen indication;
- charging status while plugged in;
- battery / coolant temperatures for service or warning states;
- service messages;
- diagnostic text / codes when deliberately invoked;
- TPMS pressure detail if the selected TPMS provides it;
- simple efficiency information.

### Do not put here by default

- maps;
- music album art;
- phone notifications;
- app stores;
- climate-control menus;
- wiper / headlamp menus;
- subscription status;
- advertising;
- general web content.

Those functions either belong elsewhere or do not belong in the car.

---

## 5. Wuhan Green Electronic Instruments — strongest current Alibaba-accessible cluster path

**Wuhan Green Electronic Instruments Co., Ltd.** is the strongest current Alibaba-accessible manufacturer found for this BOM row.

Current marketplace and manufacturer evidence describes a company focused on:

- automobile instrumentation;
- heavy-truck instruments;
- new-energy / electric-vehicle instrumentation;
- independent instrument development and manufacture;
- CAN-connected combination meters;
- IATF 16949 automotive quality-system claims.

References:

- https://greenyb.en.made-in-china.com/
- https://autopart.alibaba.com/product/electric-instrument-cluster
- https://www.alibaba.com/product-detail/E629-FQ-TFT-dashboard-meter-digital_1600667535496.html

### Why this supplier family is interesting

Unlike the enormous aftermarket market for BMW / Mercedes / Land Rover digital-dashboard conversions, Wuhan Green is currently exposing **new-energy-vehicle and commercial-vehicle instruments intended for vehicle manufacturing**.

That is much closer to the problem VolksMule actually has.

Current Alibaba results surface Green models including:

- E725 EV digital cluster around the $230 marketplace class at production MOQ;
- E629-FQ TFT CAN cluster around the $290–350 marketplace class depending quantity;
- E618 vehicle / bus LCD cluster;
- E645 7-inch TFT light-BEV cluster;
- other customized EV instrument families.

These prices and MOQs are marketplace observations only. They are not purchase commitments.

### Current status

> **CARRY Wuhan Green as the first supplier/manufacturer study; exact cluster OPEN.**

---

## 6. E408 — useful mixed-instrument architecture benchmark

A current Wuhan Green **E408** product listing is especially relevant as an architectural example.

The listing describes:

- electric-vehicle combination instrumentation;
- a central **7-inch TFT**;
- CAN-bus collection of battery, motor and other vehicle data;
- IATF 16949 certification claim;
- manufacturer customization.

Reference:

- https://greenyb.en.made-in-china.com/product/zdiGaOCjErkU/China-Factory-Direct-Sales-of-Electric-Vehicle-Combination-Meters-Mini-Vehicle-LCD-Dashboard-Analog-Driver-Instrument-Customizatione408.html

The E408 is **not selected**.

Its value is that it demonstrates the exact middle ground VolksMule wants: a normal-sized automotive combination meter with a modest central digital area rather than a dashboard-wide consumer-computer display.

---

## 7. E618 / E629 / E725 — useful product-family evidence

Other current Wuhan Green references confirm breadth rather than a single lucky listing.

### E618

Current listings describe an electric / bus combination instrument with CAN communication and an IATF 16949 claim.

References:

- https://greenyb.en.made-in-china.com/product/COfAIVkGfjhq/China-Oscilloscope-Multimeterlcr-Meter-Data-Logger-Electronic-Car-Dashboard-Electric-Vehicle-Combination-Instrumente618.html
- https://autopart.alibaba.com/product/speedometer-bus

### E629-FQ

Current direct Alibaba listing describes:

- TFT dashboard meter;
- electric-vehicle application;
- customized OE number;
- manufacturing intent;
- Green brand / Wuhan supplier.

Reference:

- https://www.alibaba.com/product-detail/E629-FQ-TFT-dashboard-meter-digital_1600667535496.html

### E725

Current Alibaba EV-cluster results surface the E725 as another dedicated electric-car dashboard family.

Reference:

- https://autopart.alibaba.com/product/electric-instrument-cluster

Together these are enough to conclude that the cluster is **not a sourcing gap**. The remaining problem is specifying the exact interface and required telltales.

---

## 8. CAN is acceptable here — secrecy is not

VolksMule already intends to use documented CAN / CAN-FD vehicle networks.

A CAN-connected cluster is therefore not a philosophical problem.

The gate is ownership of the interface.

Require:

- complete receive-message definitions / DBC or equivalent;
- exact scaling / units / timeout behavior;
- wake and sleep requirements;
- message-loss behavior;
- local configuration method;
- local firmware / recovery path;
- no VIN / cloud server required to replace the cluster.

### Preferred authority boundary

The cluster may **display**:

- speed;
- SOC;
- warning states;
- drive state;
- temperatures;
- charging state;
- diagnostics.

The cluster should not be the unique owner of:

- torque authorization;
- braking authority;
- steering authority;
- contactor control;
- charging state machine;
- lighting / wiper logic.

If the cluster goes dark, the car's controllers should still know what the car is doing.

---

## 9. Hardwired telltales are allowed where they buy resilience

Not every signal needs to enter through CAN.

For selected highest-priority warnings, a dedicated hardwired or separately driven telltale may be worthwhile if it improves fault containment and regulatory clarity.

Examples to evaluate later include:

- hazard / turn indication;
- high beam;
- brake-system warning;
- restraint / airbag warning;
- other telltales where the selected safety-system supplier already provides a direct warning output.

The final allocation must follow the safety architecture and test plan.

The key is to avoid one network gateway becoming the sole path for every warning lamp merely for wiring neatness.

---

## 10. Speed signal ownership

Vehicle speed should be derived from a well-defined vehicle-control / chassis signal, not from GPS as the primary road-speed source.

The exact source may eventually be:

- ABS / ESC wheel-speed computation;
- VCU-approved fused vehicle-speed value;
- another documented safety-grade source.

The cluster consumes the defined speed signal and displays it.

It does not create propulsion control authority by doing so.

GPS may be useful for diagnostics or comparison, but should not be the normal speedometer foundation.

---

## 11. Boot and degraded behavior

The cluster should:

- wake promptly with vehicle RUN / READY sequencing;
- present essential driving information without waiting for infotainment;
- perform a controlled telltale check as required by the final implementation;
- indicate stale / invalid critical inputs rather than silently freezing an old value;
- recover after LV brownout without dealer intervention;
- preserve odometer / required nonvolatile information correctly;
- provide a locally readable diagnostic state.

A boot animation is not a safety feature.

---

## 12. Brightness / visibility

FMVSS 101 includes illumination / visibility requirements for controls and indicators.

The final cluster therefore needs:

- daylight-readable speed and required indicators;
- night dimming;
- at least the brightness-control behavior required by the applicable standard;
- no bright white tablet permanently blasting the driver's eyes at night;
- reasonable viewing through sunglasses;
- a hood / binnacle / anti-glare strategy before display luminance is frozen.

A small shaded cluster can be easier to make legible than a giant exposed panel.

---

## 13. Physical packaging target

Do not freeze exact dimensions yet.

Carry a conventional instrument-binnacle zone centered on the driver with room for approximately a **7-inch-class central display plus dedicated telltales / surrounding instrument structure**.

This is a study envelope, not a product dimension.

Package for:

- steering-wheel sight lines;
- full seat-track range;
- tall / short driver eye points;
- sunlight hood / visor;
- rear connector access;
- cluster removal without dashboard destruction;
- no windshield removal for service.

The final steering wheel / airbag / column geometry owns the exact sight corridor.

---

## 14. What to reject

Reject a cluster if it requires:

- Android / consumer infotainment OS merely to show speed;
- proprietary cloud login;
- a phone connection for normal driving information;
- undocumented CAN messages;
- dealer/VIN online coding for ordinary replacement;
- center-infotainment computer to be alive;
- one giant common display implementation that cannot meet the telltale requirements;
- touchscreen interaction for required driving controls;
- replacement of the whole dashboard because the display fails.

Also reject a cheap gauge package that cannot demonstrate automotive environmental durability merely because its CAN IDs are easy to reverse engineer.

---

## 15. Exact data inputs to reserve

The first cluster I/O definition should anticipate at least these logical data groups.

### Vehicle motion / command

- vehicle speed;
- PRND / selected direction or equivalent state;
- READY / propulsion-enabled state;
- parking-brake state;
- turn / hazard state;
- high-beam state.

### HV / energy

- traction SOC;
- charging state;
- charge-power / estimated-time data if available;
- HV-system warning;
- reduced-power state;
- battery temperature warning / detail as useful.

### Chassis / safety

- brake warning states;
- ABS state / fault as required;
- ESC state / fault as required;
- TPMS state / warning;
- restraint / airbag warning;
- seat-belt status / warning;
- AEB / safety-system telltales as the final rules and supplier architecture require.

### Service / utility

- odometer;
- trip meter;
- 12-V system warning;
- coolant / thermal warning states;
- diagnostic / service message identifier.

This is an interface-planning list, not the final regulatory telltale table.

---

## 16. Supplier questions — hold for later outreach

Supplier outreach remains intentionally deferred.

When the cluster requirement / telltale matrix is mature, ask Wuhan Green and any surviving alternate for:

1. exact 2D / 3D drawing;
2. display size / resolution / luminance / contrast;
3. operating and storage temperature;
4. vibration / thermal / humidity / EMC qualification;
5. exact IATF manufacturing-site certificate;
6. full CAN / CAN-FD / LIN interface documentation;
7. DBC or equivalent signal table;
8. configurable telltale locations / dedicated LEDs;
9. FMVSS 101 implementation support and symbol / color options;
10. boot time;
11. brownout / invalid-message behavior;
12. odometer / nonvolatile-memory architecture;
13. local configuration / reflash / recovery procedure;
14. mating connector / terminals;
15. sample / prototype quantity and NRE for custom graphics / telltales;
16. replacement availability horizon;
17. whether a replacement cluster can be commissioned entirely offline.

No inquiry should be sent during this sourcing pass.

---

# Current verdict

### Cluster architecture

> **CARRY — independent conventional instrument cluster with modest central display and dedicated critical telltales.**

### Supplier path

> **CARRY — Wuhan Green Electronic Instruments as the first Alibaba-accessible EV / heavy-vehicle cluster manufacturer study.**

### Product benchmark

> **CARRY E408-style mixed architecture as a packaging / HMI benchmark; E618 / E629 / E725 families prove supplier depth.**

No exact Green model is selected.

### Electrical interface

> **CARRY documented CAN as the primary data plane, with selected hardwired safety indications allowed when they improve resilience.**

### Exact cluster

> **OPEN.**

Blocked legitimately on:

- final FMVSS 101 / regulatory telltale matrix;
- steering-wheel / driver eye / binnacle geometry;
- CAN message ownership and ECU selections;
- restraint / ESC / TPMS / AEB supplier interfaces;
- odometer / service-data architecture;
- required display and dedicated-telltale configuration.

The cluster is no longer an Alibaba sourcing unknown. It is now an interface, compliance and packaging definition task.
