# Alibaba low-voltage electrical, CAN, diagnostics, and vehicle-control sourcing

This document records the Prototype 1 sourcing screen for the conventional 12-V system, fuse/relay distribution, wiring harnesses, connectors, CAN/CAN-FD networks, instrumentation, diagnostics, and the vehicle-control unit (VCU).

It follows the VolksMule canon:

> **The computer does not own the vehicle.**

The network may coordinate the vehicle. It must not become the only path by which ordinary physical functions work.

## Executive verdict

| Subsystem | Alibaba / China sourcing verdict | Prototype 1 direction |
|---|---|---|
| 12-V battery | GREEN, but local purchase preferred | Common locally replaceable automotive 12-V battery |
| Fuse / relay distribution | GREEN | Conventional visible/serviceable fuse and relay blocks |
| High-current LV fusing | GREEN with component qualification | MIDI / MEGA-class or equivalent documented fusing |
| Wiring harness manufacture | GREEN | Build to VolksMule drawings/BOM; 100% electrical test |
| Sealed connectors | GREEN | Standard families; avoid unique housings |
| J1962-style diagnostic connector | GREEN | Use familiar 16-pin physical service port |
| CAN/CAN-FD wiring | GREEN | Twisted-pair, documented topology and termination |
| Instrument cluster | YELLOW | Dedicated vehicle instrument unit, independent of infotainment |
| VCU | YELLOW | Supplier or controlled platform only if interfaces/calibration remain owner-accessible |
| Generic black-box BCM | RED as architectural default | Avoid making one sealed body computer own all convenience functions |
| Infotainment gateway | BUY / DESIGN boundary | Isolated from safety-critical networks; read-mostly by default |

## 1. Keep 12 V boring

Prototype 1 keeps a conventional 12-V low-voltage ecosystem unless evidence gives us a better reason.

### Baseline

- ordinary automotive 12-V auxiliary battery;
- common local group size selected after packaging and reserve-load analysis;
- ordinary terminals and hold-down;
- service access without removing the traction battery;
- DC/DC converter charges the 12-V bus from the HV pack;
- vehicle can still wake / diagnose / safely shut down using the 12-V system.

### Do not optimize the battery around Alibaba price

The exact auxiliary battery is a local-service item. Alibaba may be useful for factory sourcing later, but Prototype 1 should use a battery format that can be bought at an ordinary auto-parts store.

A lead-acid or AGM battery remains a credible baseline because it is cheap, cold-tolerant, familiar, and globally replaceable. A 12-V lithium auxiliary battery may be reconsidered only if it wins the total system trade.

## 2. Power distribution: fuse it where people can see it

Prototype 1 should favor conventional power distribution over a monolithic smart junction box.

### Preferred topology

At least two service zones are worth studying:

1. **front / under-hood electrical center**
   - radiator / condenser fans;
   - pumps;
   - ABS/ESC supply;
   - EPS supply;
   - lighting relays where appropriate;
   - horn;
   - HVAC auxiliaries;
   - spare fuse/relay positions.

2. **cabin / body electrical center**
   - instrument cluster;
   - wipers / washers control feed;
   - HVAC controls;
   - accessory sockets;
   - interior lighting;
   - rear camera/display supply;
   - diagnostics;
   - optional convenience loads.

High-current paths such as EPS, ABS, DC/DC output, PTC auxiliaries, fans, and other heavy 12-V loads may use separate bolted MIDI/MEGA-class fuse blocks near the source.

### Alibaba lead

Alibaba currently lists IATF-claimed multi-way MIDI/MEGA fuse holders in the 12/24/48-V class, including -40 C to +125 C products with individual high-current fuse positions.

Example discovery reference:
https://www.alibaba.com/product-detail/32V-7-way-SUV-Van-Truck_1600530569866.html

**Status: useful hardware lead, not yet approved.** The exact certification, plastic flammability, terminal heating, fuse clamping, vibration performance, and short-circuit interrupt assumptions must be verified before selection.

## 3. Relay philosophy

Use ordinary relays where an ordinary relay does the job.

Candidate relay-controlled loads include:

- horn;
- defrost;
- selected exterior lighting circuits;
- washer pump;
- accessory feeds;
- non-safety-critical pumps/fans where PWM control is not required.

Solid-state control is acceptable when required for PWM, diagnostics, efficiency, or life, but it should not become the default merely because a smart power module exists.

### Requirements

- replaceable relay form factor where practical;
- relay function printed on fuse-box cover / wiring diagram;
- spare relay compatibility;
- manual fuse/relay map in repository and vehicle;
- no cloud or proprietary coding required to replace a relay or fuse block.

## 4. Harnesses: Alibaba is genuinely strong here

The right sourcing model is:

> **VolksMule owns the schematic, pinout, wire sizes, labels, protection, and connector choices. A harness supplier manufactures it.**

### Strong supplier leads

#### ETOP Wire Harness
**Status: GREEN / low-volume RFQ lead**

ETOP states that it is IATF 16949 and UL certified, supports automotive and EV harnesses, has in-house prototyping/tooling, and accepts flexible quantities.

Reference:
https://www.etopwireharness.com/

#### Zhejiang Wenda Electronics
**Status: GREEN / connector + harness lead**

Wenda states IATF 16949 certification, automotive harness capability, new-energy connectors, and a large in-house manufacturing base.

Reference:
https://www.wendaconnector.com/

#### Cablum
**Status: GREEN / low-volume drawing-to-harness lead**

Cablum advertises IATF 16949 manufacturing specifically for custom/low-volume automotive programs using customer drawings and BOMs.

Reference:
https://cablum.com/solutions/automotive-wire-harness/

#### Wenzhou Yineng
**Status: GREEN / connector-family lead**

Yineng describes automotive connector and harness production under automotive quality systems and lists automotive safety/steering customers.

Reference:
https://www.yn-china.com/

### Harness RFQ

Require:

- IATF 16949 certificate and scope;
- wire manufacturer / specification;
- temperature and fluid exposure rating;
- conductor gauge and strand construction;
- terminal manufacturer and plating;
- crimp-height / pull-force process controls;
- connector family and exact part numbers;
- cavity plugs and secondary locks;
- branch protection / loom type;
- abrasion protection;
- labels at both ends of service branches;
- 100% continuity test;
- short-to-adjacent and insulation test where appropriate;
- serialized build / revision traceability;
- first-article harness before vehicle build;
- repair pigtails and loose terminals available separately.

## 5. Connector rule: standardize aggressively

VolksMule should deliberately minimize the number of connector families.

### Preferred categories

- sealed 2/3/4/6/8-way connectors for ordinary exterior devices;
- one or two medium-density ECU connector families;
- standardized high-current 12-V connectors / studs;
- dedicated HV connector families kept separate from LV;
- serviceable terminals with available extraction tools.

### Requirements

- independent terminal availability;
- cavity seals / plugs available;
- mating-cycle rating;
- current derating data;
- temperature range;
- IP rating where exposed;
- vibration qualification;
- no unique connector that exists only on one supplier ECU unless unavoidable.

## 6. CAN / CAN-FD network architecture

The network should be **small, documented, and segmented by consequence**.

### Study topology

#### Powertrain / HV CAN
Contains:

- VCU;
- BMS;
- front inverter/e-axle;
- rear inverter/e-axle;
- OBC/DC-DC;
- charge controller / EVCC;
- thermal-controller messages required for HV operation.

#### Chassis CAN
Contains:

- ABS/ESC;
- EPS;
- steering-angle signal;
- wheel-speed information;
- brake / stability data;
- safety-related vehicle-motion signals.

#### Body / instrumentation CAN
Contains only what actually benefits from networking:

- instrument cluster;
- selected HVAC status;
- body telltales;
- rear camera status if necessary;
- optional convenience features.

Many body functions may remain discrete/hardwired instead of existing on CAN merely because CAN exists.

### Infotainment boundary

Infotainment/general-purpose compute should connect through a controlled gateway.

Default behavior:

- infotainment may read vehicle status;
- write access is limited to explicitly permitted non-safety functions;
- safety networks remain operational if infotainment is unplugged;
- navigation/media updates cannot modify torque, brakes, steering, restraints, HV contactors, or essential visibility functions.

## 7. VCU: the sovereignty gate

A VCU is necessary because someone must coordinate:

- driver torque request;
- front/rear axle torque allocation;
- HV wake/shutdown sequencing;
- BMS limits;
- regenerative braking requests;
- charge state transitions;
- thermal limits;
- limp/degraded modes;
- fault handling;
- required interlocks.

But the VCU must not become a proprietary king computer.

### EVPT — strongest current Chinese road-intent supplier lead
**Status: YELLOW / serious RFQ**

EVPT states that it passed IATF 16949 and became a global VCU supplier to Valeo and Stellantis in 2020. Its history and product positioning make it credible enough for a road-intent supplier conversation.

Reference:
https://www.evpt.com.cn/en/h-col-115.html

It only fits VolksMule if the project can obtain enough control/documentation sovereignty.

### HiRain — engineering benchmark
**Status: YELLOW / OEM engineering benchmark**

HiRain's VCU offering describes AUTOSAR-based development, vehicle calibration, HIL/MIL testing, and full lifecycle engineering for EV/PHEV programs.

This is useful evidence of what a legitimate VCU development relationship looks like, but it may be far beyond Prototype 1 budget/volume.

### VCU RFQ: mandatory questions

1. Will you support a low-volume Prototype 1 program?
2. What 12-V supply range and environmental ratings apply?
3. How many CAN / CAN-FD channels?
4. Are all DBC files provided for vehicle-owned messages?
5. Can VolksMule define and retain ownership of application-level message IDs and scaling?
6. Is UDS or another diagnostic protocol supported and documented?
7. Are DTC definitions supplied?
8. Is calibration possible offline without a vendor server?
9. Can a replacement VCU be commissioned locally?
10. Is firmware recovery possible with documented tooling?
11. What happens if your company stops supporting the controller?
12. Are bootloader / programming interfaces documented under an appropriate license/NDA?
13. Can we export configuration/calibration files into the public project repository when they contain no supplier IP?
14. Can safety-critical torque logic be validated by HIL / fault injection?
15. Can the VCU operate with infotainment completely disconnected?

A supplier refusal on local replacement, offline diagnostics, or message documentation is an architectural red flag even if the hardware is excellent.

## 8. Instrumentation: a display is not infotainment

VolksMule still needs clear instrumentation.

A small dedicated automotive instrument cluster is reasonable for:

- speed;
- gear / drive state;
- HV / ready state;
- battery state of charge;
- range estimate;
- telltales and warnings;
- ABS / ESC / restraint / brake warnings;
- turn indicators;
- high beam;
- charge status;
- serious fault messages.

### Rules

- cluster boots independently of infotainment;
- required warnings do not wait for Android/Linux/phone boot;
- cluster receives only documented data;
- basic critical telltales should be implementable as dedicated outputs if necessary;
- failure of the center media/navigation screen must not remove required instruments.

Alibaba has many CAN/J1939 display products, but a generic truck display is a development tool until telltale, sunlight, boot-time, EMC, environmental, and vehicle-standard requirements are verified.

## 9. Diagnostics: make the socket boring and the protocol open

Prototype 1 should use a familiar **SAE J1962-style 16-pin physical diagnostic connector** even where federal emissions OBD requirements do not define the BEV service strategy.

Alibaba currently has hundreds of J1962-style connector listings at commodity prices.

Discovery reference:
https://www.alibaba.com/showroom/j1962-connector-24v-obd2.html

### Proposed pin philosophy

Use standard physical form factor, then document the actual assignment in the service manual.

At minimum provide:

- chassis ground;
- signal ground;
- protected 12-V diagnostic power;
- CAN-H / CAN-L for a diagnostic gateway or designated service bus;
- optional additional CAN pair if justified and safely isolated.

### Diagnostic owner-control requirement

The repository should eventually publish:

- DTC list;
- live data identifiers;
- service commands;
- reset / relearn procedure;
- component replacement procedure;
- network map;
- bus speed;
- DBC files for project-owned messages;
- firmware version identification;
- safe recovery process.

## 10. Hardwired fallback candidates

The following should be investigated for direct/local control rather than mandatory central-body-computer ownership:

- horn switch -> relay -> horn;
- hazard switch -> dedicated flasher/body logic independent of infotainment;
- brake pedal switch -> brake-light path plus separate ECU sensing as needed;
- headlamp switch -> local lighting control/relay;
- wiper stalk -> local wiper controller / relay;
- washer switch -> local pump path;
- rear defrost switch -> timed relay/local controller;
- manual door locks/windows -> no body network required;
- HVAC knobs -> dedicated HVAC controller;
- mechanical parking brake -> no actuator network required.

Exact circuits remain an electrical-engineering task; the point is architectural independence, not literally avoiding every microcontroller.

## 11. Failure-domain rules

1. One failed body module should not black out the whole vehicle.
2. Infotainment failure must not disable vehicle motion or essential controls.
3. A CAN short should have bounded consequences through network segmentation/gateway design.
4. Critical ECUs should have individually fused feeds.
5. Diagnostic access should remain possible when a noncritical module is removed.
6. VCU replacement must not require a cloud account.
7. Fuse/relay access should not require removing the dashboard.
8. Harness branches and connectors should be labeled/documented.
9. The car should tolerate removal of optional accessories without network tantrums.
10. Spare fuse positions and sensible service loops should be designed in.

## 12. Sourcing verdict

Alibaba is particularly strong for:

- fuse and relay hardware;
- connector bodies and terminals;
- harness fabrication;
- diagnostic connectors;
- switches and panels;
- commodity sensors where qualification is straightforward.

Alibaba is useful but dangerous for:

- generic VCUs;
- generic BCMs;
- integrated smart power-distribution modules;
- mystery CAN gateways;
- undocumented instrument clusters.

For those controller classes, availability is not enough. Documentation and owner-controlled service are part of the component specification.

## Current recommendation

Prototype 1 should use:

- conventional 12-V auxiliary battery;
- visible/serviceable fuse and relay centers;
- a harness manufactured to VolksMule-owned drawings;
- a deliberately small set of sealed connector families;
- separate powertrain/HV and chassis networks;
- body CAN only where networking earns its complexity;
- a dedicated instrument cluster independent of infotainment;
- a J1962-style physical service port;
- one modest VCU that coordinates powertrain/HV behavior but does not own ordinary body convenience functions;
- an isolated infotainment gateway.

The electrical architecture should make the vehicle easier to understand, not harder.
