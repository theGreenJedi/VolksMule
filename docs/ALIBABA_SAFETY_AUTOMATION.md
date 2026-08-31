# Alibaba safety automation: TPMS, AVAS, AEB/FCW, and required local warnings

This document records the Prototype 1 sourcing screen for safety automation that has a defined safety or regulatory job.

VolksMule is not trying to become a self-driving research platform.

> **Use computers where the safety function genuinely requires them. Do not let that computer grow into ownership of the vehicle.**

## Executive verdict

| Function | Sourcing verdict | Prototype 1 direction |
|---|---|---|
| TPMS | GREEN / automotive supplier | Direct TPMS with ordinary wheel sensors, local relearn and documented receiver interface |
| Pedestrian alert / AVAS | GREEN / automotive supplier | Dedicated 12-V AVAS module meeting FMVSS 141 at vehicle level |
| Rear visibility | GREEN / already screened | Dedicated camera/display path independent of infotainment boot |
| FCW/AEB/PAEB sensing | YELLOW / Tier-1 integration | Dedicated forward-safety module; minimum sensor set that passes FMVSS 127 |
| AEB brake actuation | YELLOW / calibration-critical | Integrate through selected ABS/ESC supplier; not a generic relay or hobby controller |
| Lane centering / self-driving | RED for Prototype 1 | Do not add unless a real requirement appears |
| Driver-facing camera | RED by default | No surveillance hardware without a requirement |
| Seat-belt reminder | GREEN / local vehicle logic | Dedicated telltale/audible path independent of infotainment |

## 1. Current regulatory timing to preserve

### FMVSS 127 — AEB / PAEB / FCW

NHTSA's current FMVSS 127 framework requires automatic emergency braking, pedestrian AEB, and forward collision warning for covered light vehicles.

Current compliance timing:

- general light-vehicle compliance: **September 1, 2029**;
- small-volume manufacturers, final-stage manufacturers, and alterers: **September 1, 2030**.

The standard is performance-based. It does not dictate that VolksMule install a specific number of cameras, radars, or a general-purpose autonomy computer.

References:
- https://www.nhtsa.gov/press-releases/nhtsa-fmvss-127-automatic-emergency-braking-reduce-crashes
- https://www.transportation.gov/bipartisan-infrastructure-law/regulations/2024-27349

### FMVSS 138 — TPMS

FMVSS 138 applies to passenger cars, MPVs, trucks and buses at or below 10,000-lb GVWR, subject to specified exceptions, and establishes vehicle-level TPMS performance including low-pressure and malfunction warnings.

Reference:
https://www.nhtsa.gov/document/laboratory-test-procedure-fmvss-138-tire-pressure-monitoring-systems

### FMVSS 141 — quiet-vehicle minimum sound

The EV pedestrian-alert requirement is a vehicle-level acoustic-performance requirement. A supplier module is only one part of compliance; installation location, vehicle noise, sound calibration, and test condition still matter.

Reference:
https://www.nhtsa.gov/es/document/laboratory-test-procedure-fmvss-141-minimum-sound-requirements-hybrid-and-electric

### FMVSS 208 — seat-belt reminders

As of the April 6, 2026 interim final rule, the enhanced front and rear seat-belt reminder requirements have a unified compliance date of **September 1, 2028**, with multi-stage manufacturers and alterers receiving an additional year.

Reference:
https://www.transportation.gov/regulations/federal-register-documents/2026-06614

## 2. TPMS — buy the solved system

A direct TPMS system is exactly the sort of solved automotive hardware VolksMule should buy.

### Baolong Automotive — strongest current Chinese road-intent lead
**Status: GREEN / first RFQ**

Baolong states that it delivered more than 75 million TPMS units in 2025, operates in China, Germany and the United States, serves many OEM platforms, and manufactures automotive sensor systems under IATF 16949 / functional-safety processes.

Reference:
https://en.baolong.biz/product/search.html

Why it fits:

- actual OEM TPMS supplier rather than an aftermarket clone seller;
- global service footprint;
- direct passenger-vehicle TPMS expertise;
- pressure-sensor and receiver/system capability;
- scale sufficient that replacement sensors should not depend on one tiny vendor.

### Alibaba role

Alibaba contains huge numbers of 315/433-MHz OEM-style TPMS sensor listings. These are useful for:

- market discovery;
- bench experimentation;
- understanding common valve/sensor form factors;
- initial cost comparison.

They are not automatically suitable for the road-intent vehicle merely because they transmit pressure.

### TPMS architecture requirement

Prefer:

- four direct wheel sensors;
- spare-tire sensor optional depending on final spare strategy;
- locally executable sensor-ID relearn;
- no cloud account;
- standard replaceable valve/service kits;
- documented RF frequency / protocol or supplier-supported replacement tool;
- instrument-cluster warning independent of infotainment.

### TPMS RFQ

Ask for:

1. FMVSS 138 vehicle-program support experience;
2. operating frequency options for North America;
3. battery-life specification;
4. pressure / temperature accuracy;
5. environmental and wheel-speed limits;
6. relearn method;
7. replacement-sensor pairing method;
8. receiver/gateway CAN documentation;
9. DTC / malfunction behavior;
10. aftermarket/service sensor availability;
11. valve stem / seal service parts;
12. sample/prototype quantity.

## 3. AVAS / pedestrian alert — dedicated appliance, not infotainment audio

The pedestrian-alert sound should come from a **dedicated automotive AVAS module**.

It should not depend on:

- media amplifier;
- infotainment operating system;
- phone;
- Bluetooth;
- cloud service;
- user playlist/audio settings.

### TEMB — strongest Chinese supplier lead
**Status: GREEN / first RFQ**

TEMB describes itself as an early Chinese AVAS developer, states that it participated in drafting China's AVAS standard, and offers dedicated passenger/commercial vehicle AVAS modules. Public product descriptions show 12/24-V architectures and automotive integration support.

Reference:
https://www.tembelectric.com/AVAS/

### TRION — secondary integration lead
**Status: YELLOW / prototype and supplier comparison**

TRION publishes CAN-controlled 12/24-V AVAS hardware with automotive temperature ranges and IP67 packaging.

Reference:
https://www.ev-components.com/avas-automotive/

### FMVSS 141 benchmark

HL Klemove publicly lists an AVAS system with FMVSS 141 / UNECE R138 regulatory support and HS-CAN, useful as a Tier-1 benchmark for what the supplier evidence should look like.

Reference:
https://www.hlklemove.net.cn/business/AE-solution/AVAS.do

### AVAS architecture

- dedicated fused 12-V feed;
- speed and direction input from a documented local vehicle bus;
- sound-generation logic inside the dedicated AVAS unit;
- system active regardless of infotainment state;
- no ordinary user-disable control for required operation;
- local diagnostic / fault indication;
- replaceable external speaker/module;
- final sound calibrated and vehicle-tested to FMVSS 141.

## 4. AEB: buy an automotive safety function, not an AI box

AEB is where marketplace sourcing stops being casual.

Generic Alibaba items described as "ADAS camera," "collision radar," or "AI driving box" should be treated as development curiosities unless the supplier can support a vehicle certification program.

### Freetech — strongest current Chinese Tier-1 lead
**Status: GREEN/YELLOW / first road-intent RFQ**

Freetech is a current high-volume Chinese ADAS Tier-1. In 2026 it reports more than one million annual deliveries, broad OEM adoption, and international vehicle nominations.

Its current FVC2 passenger-vehicle front camera lists:

- CAN-FD / FlexRay;
- 150-m detection range;
- AEB;
- FCW-related safety functions;
- integrated perception/controller functionality.

Its 2026 "Fuxing" program supports front smart-camera configurations and optional radar/multisensor fusion, with the supplier explicitly describing AEB regulatory support for international markets.

References:
- https://en.freetech.com/
- https://www.freetech.com/en/technology/controller/cmcpv/4
- https://en.freetech.com/news/56

### Important architecture rule

Do **not** begin by deciding that VolksMule needs 5 radars, 8 cameras, lidar, or an autonomy domain controller.

Begin with:

> **What is the minimum automotive sensor/controller architecture that passes the applicable FMVSS 127 performance envelope on the finished vehicle?**

Candidate study sequence:

1. integrated forward smart camera only;
2. forward smart camera + one front radar;
3. only add further sensing if testing/performance proves it necessary.

Night pedestrian performance, weather robustness, false-positive control, and braking authority may make radar+camera the practical answer, but the requirement should drive the sensor count.

## 5. AEB belongs to the brake architecture

The forward sensor does not independently own the brakes.

The intended signal chain is conceptually:

**forward safety sensor/controller -> validated AEB request -> VCU/chassis gateway as appropriate -> ABS/ESC pressure-control system -> hydraulic brakes**

Exact responsibility split must be agreed with the selected ABS/ESC/AEB supplier.

Requirements:

- brake controller remains the final calibrated pressure-control authority;
- driver brake input remains available;
- friction braking foundation works without AEB;
- AEB faults generate clear local telltales/DTCs;
- infotainment failure cannot disable AEB;
- sensor replacement/calibration has an offline workshop procedure;
- false-trigger and unavailable-state behavior is explicitly documented.

## 6. AEB RFQ

Ask Freetech / alternate Tier-1 suppliers:

1. Can you support a low-volume MPV/utility EV program?
2. Have your systems been developed against U.S. FMVSS 127 requirements?
3. What minimum sensor configuration do you recommend for FMVSS 127?
4. Can the system operate as a dedicated AEB/FCW function without lane-centering/autonomy features?
5. What ABS/ESC controller interfaces are supported?
6. CAN/CAN-FD message documentation available under NDA?
7. Calibration process and required targets/tools?
8. Windshield/camera-mount optical requirements?
9. Radar mounting/aim tolerances if radar is required?
10. Required vehicle signals: wheel speed, yaw, steering angle, brake pressure, accelerator, gear, etc.?
11. Required functional-safety work products?
12. Fault states and driver warning requirements?
13. Night pedestrian performance evidence?
14. Environmental/weather performance data?
15. Replacement sensor commissioning possible offline?
16. Does any safety function require cloud connectivity? (Required answer: no.)
17. Does any function require persistent video upload/recording? Prefer no.
18. Prototype quantity, development cost, calibration support, and lead time?

## 7. No driver-surveillance expansion

A forward road-facing safety camera does not justify a driver-facing camera.

Prototype 1 does not need:

- facial recognition;
- attention scoring;
- occupant video upload;
- cabin recording;
- remote surveillance;
- cloud-based driver identity.

If a future regulation explicitly forces a monitoring function, solve the narrow requirement then. Do not preinstall surveillance hardware "just in case."

## 8. Seat-belt reminder architecture

The two-seat layout makes this comparatively simple.

Provide local, independent status for:

- driver belt buckle;
- passenger belt buckle;
- passenger occupancy detection as required by the restraint strategy;
- visual warning in the dedicated cluster;
- audible warning through a local warning chime/buzzer path.

The warning must not depend on infotainment audio.

The exact implementation should be coordinated with the integrated restraint supplier because occupancy classification and airbag logic are already linked.

## 9. Rear visibility remains separate

Rear-camera architecture was screened in `ALIBABA_VISIBILITY_HARDWARE.md`.

The safety-automation rule remains:

- dedicated camera;
- dedicated/qualified display path;
- fast boot;
- reverse-triggered locally;
- no cloud;
- no media-computer dependency.

## 10. What Alibaba is good for in this category

### Strong

- TPMS sensor and valve discovery;
- AVAS speaker/module discovery;
- automotive cameras for bench/packaging research;
- radar bracket and harness fabrication;
- connectors;
- calibration targets/fixtures;
- warning buzzers/speakers.

### Caution

- complete TPMS receiver logic;
- safety telltale clusters;
- AEB smart cameras;
- radar modules.

### Do not select generically

- AEB controller;
- collision-warning ECU;
- "AI ADAS box";
- brake intervention controller;
- unknown radar/camera firmware.

Those functions need an actual automotive safety supplier and vehicle-level calibration.

## 11. Failure-domain rules

1. AEB failure does not remove normal hydraulic braking.
2. TPMS failure does not immobilize the car; it produces the required malfunction indication.
3. AVAS failure produces a diagnosable local fault.
4. Rear-camera failure does not crash infotainment or other vehicle networks.
5. Seat-belt warning remains available with infotainment disconnected.
6. Safety sensors do not require internet access.
7. Sensor calibration can be performed locally with documented tools/targets.
8. Optional ADAS functions cannot rewrite the behavior of steering/traction without an explicitly engineered interface.
9. Safety automation cannot become a reason to add hardware without a defined safety function.

## Current recommendation

Prototype 1 safety automation should be intentionally narrow:

- Baolong-class direct TPMS;
- TEMB-class dedicated AVAS;
- existing independent rear-camera path;
- front seat-belt warning integrated with the restraint/cluster architecture;
- a dedicated Freetech-class forward smart safety camera, with one front radar added if required to achieve robust FMVSS 127 performance;
- AEB actuation through the selected calibrated ABS/ESC brake supplier;
- no lane-centering, self-parking, hands-free driving, lidar, or driver-facing surveillance unless a later requirement earns them.

The goal is not the least electronics possible. It is the **least electronics necessary to make the vehicle safe, legal, understandable, and owner-controlled.**
