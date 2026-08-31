# Alibaba high-voltage safety plumbing

This document records the Prototype 1 sourcing screen for the hardware that safely connects the traction battery to the rest of the vehicle:

- main HV contactors;
- precharge path;
- main pack fuse;
- manual service disconnect (MSD);
- high-voltage interlock loop (HVIL);
- insulation monitoring device (IMD);
- high-voltage connectors;
- high-voltage harnesses;
- busbars and pack feedthroughs.

The pack enclosure and crash integration remain VolksMule-designed. These safety components should be bought from proven suppliers rather than reinvented.

## Executive verdict

| Function | Current direction |
|---|---|
| Main contactors | **BUY — Hongfa-class automotive HVDC relays** |
| Precharge contactor/resistor | **BUY / size after bus capacitance is known** |
| Main HV fuse | **BUY from traceable automotive fuse manufacturer/distributor; price is secondary** |
| Manual service disconnect | **BUY — Chilye/Yonggui-class automotive MSD with HVIL** |
| HV connectors | **BUY — Chilye/Yonggui automotive families; standardize aggressively** |
| HVIL | **DESIGN loop using connector/MSD interlock contacts** |
| Insulation monitor | **BUY — Bender automotive IMD is the benchmark** |
| HV cable/harness | **BUY/FABRICATE to VolksMule-owned drawings through qualified harness supplier** |
| Busbars | **DESIGN, then source/fabricate** |
| BDU/PDU enclosure/topology | **DESIGN or adapt transparent supplier hardware; avoid black box** |

## 1. Contactor architecture

Prototype 1 needs a deliberate battery-disconnect unit rather than a mystery integrated box.

A conventional first study architecture is:

- pack-positive main contactor;
- pack-negative main contactor;
- precharge contactor or relay;
- precharge resistor;
- main pack fuse;
- service disconnect;
- pack-current measurement as required by the BMS;
- HVIL monitoring;
- insulation monitoring;
- accessible voltage-sense points only where safely enclosed and documented.

The exact topology can change after the BMS, OBC/PDU and DC-fast-charge path are reconciled, but every switching/protection function must remain identifiable on the schematic.

## 2. Hongfa — first HV contactor RFQ

**Status: GREEN / road-intent supplier lead**

Hongfa publishes dedicated high-voltage DC relays for EV and charging applications. Its current EV application page lists families including:

- HFE80V-20C;
- HFE82V-150D;
- HFE82V-200W;
- HFE82V-300C.

Hongfa states that it supplies automotive OEM/Tier-1 customers and provides HVDC relay, BDU and PDU products for the automotive market.

References:
- https://en.hongfa.com/Products/relays/dc-relay
- https://www.hongfa.com/Solution/Item/electric-vehicle

### RFQ requirements

Ask for candidate 400-V-class automotive contactors after pack peak current and fault-current studies are available:

- continuous carry current versus ambient and terminal temperature;
- make/break voltage and current capability;
- short-circuit withstand;
- contact welding limits;
- bidirectional interruption capability where required;
- coil voltage/current and economizer behavior;
- auxiliary-contact option for welded/open-state detection;
- mechanical/electrical life;
- vibration/shock/environmental qualification;
- isolation/dielectric ratings;
- terminal torque and busbar interface;
- mounting orientation;
- dimensional CAD;
- exact automotive qualification/certification evidence;
- traceability and production continuity.

### Rule

Do not select a contactor from its nominal amp rating alone. Breaking capacity under the actual pack voltage/fault conditions matters.

## 3. Precharge stays visible

Precharge should not disappear into undocumented supplier firmware.

The purpose is to charge downstream DC-link capacitance before the main contactor closes, reducing inrush current and contact damage.

Prototype 1 should document:

- resistor value/power based on actual downstream capacitance;
- precharge time target;
- voltage threshold for successful precharge;
- timeout behavior;
- welded/stuck contactor detection;
- BMS/VCU responsibility split;
- diagnostic DTCs.

Exact resistor and relay selection waits until the e-axle inverter, OBC/DC-DC/PDU and DC-fast-charge architecture are frozen enough to know the capacitance and fault cases.

## 4. Manual service disconnect — Chilye and Yonggui

A real physical service disconnect strongly fits VolksMule.

### Chilye

**Status: GREEN/YELLOW — direct Alibaba-accessible lead**

Suzhou Chilye Green Technology is an IATF-16949-listed EV high-voltage component manufacturer. Alibaba currently surfaces Chilye-branded:

- 80–500 A manual service disconnect families;
- 500-A MSD products;
- automotive high-voltage connectors;
- PDU/harness products.

Alibaba discovery reference:
https://www.alibaba.com/search/page?SearchScene=imageTextSearch&productId=1601268136673

Chilye also directly lists a 1000-V/250-A HVC800 connector with IP67/IP6K9K and HVIL contacts:
https://www.alibaba.com/product-detail/HVC800-Series-250A-1000V-DC-2_1600252076330.html

### Yonggui

**Status: GREEN/YELLOW — stronger interconnect benchmark / direct RFQ**

Yonggui publishes dedicated EV manual-maintenance-switch products including YG1040, YG1052 and YG1130, alongside broad automotive HV interconnect, harness and PDU/BDU families.

References:
- https://www.yongguielectric.com/ev-connectors-solution/
- https://www.yongguielectric.com/products/new-energy-and-vehicle-connectors-system/

Yonggui states that its automotive connector work is based on IATF 16949 processes and that products can be tested to USCAR requirements.

### MSD requirements

- rated voltage above worst-case pack voltage;
- continuous current above expected vehicle current with margin;
- fault/short-circuit coordination with the pack fuse;
- integrated HVIL contacts;
- touch-safe construction;
- IP rating appropriate to pack location;
- keyed/mis-mate protection;
- clear lock/unlock state;
- serviceable without proprietary software;
- safe access only after the vehicle service procedure is followed;
- spare availability independent of a cloud account.

## 5. HV connectors — standardize the family, not just the pin count

Connectors should be selected as a small family covering:

- traction e-axles/inverters;
- OBC/DC-DC;
- compressor/PTC heater;
- battery/PDU interfaces;
- charge-path internal connections where separable connectors are appropriate.

### Chilye HVC800 example

Current Alibaba listing publishes:

- 1000 VDC;
- up to 250 A;
- IP67 mated / IP6K9K;
- 360-degree shielding;
- HVIL conductors;
- 25/35/50-mm² cable support.

This makes it a useful candidate family, pending full qualification documents and exact current/temperature derating.

### Yonggui

Yonggui has broader EV connector families and publishes USCAR-oriented test capability. It also exposes 2D/3D drawings through its engineering process and supports whole-vehicle interconnection solutions.

### Connector requirements

- HVIL integrated where disconnecting under service should open the interlock loop;
- touch protection;
- secondary lock / CPA as appropriate;
- polarity/keying;
- shielding where required for EMC;
- current derating versus conductor size/ambient;
- mating-cycle rating;
- terminal/crimp or ultrasonic-weld process specification;
- salt/spray/fluid/vibration/environmental data;
- independently purchasable mating halves, terminals, seals and service tools;
- CAD/drawings;
- no unnecessary proliferation of proprietary families.

## 6. HVIL belongs to VolksMule logic

The high-voltage interlock loop should be simple enough to draw and troubleshoot.

Potential HVIL participants include:

- pack service disconnect;
- pack cover/service connector if justified;
- major HV connectors that expose live HV when unmated;
- PDU/BDU service covers where appropriate;
- charge-path components if required by the final architecture.

The BMS/VCU must define clear behavior for:

- HVIL open before drive enable;
- HVIL opening while energized;
- contactor-opening request;
- fault latching/restart policy;
- DTC and instrument warning;
- service diagnosis.

No app or cloud path belongs in this loop.

## 7. Insulation monitoring — Bender is the benchmark

**Status: GREEN benchmark / purchase path outside Alibaba acceptable**

Bender's automotive ISOMETER products are specifically designed to monitor isolation between an unearthed EV high-voltage system and vehicle chassis.

Current examples:

### IR155-3203 / IR155-3204

- designed for EV unearthed DC drive systems;
- 0–1000-V system range;
- continuous insulation measurement;
- 12/24-V supply;
- monitors DC and motor/inverter side behavior.

Reference:
https://www.bender.de/en/products/insulation-monitoring/isometer-ir155-3203-ir155-3204/

### iso165C / iso175 class

Bender also publishes CAN-connected automotive IMDs for high-voltage vehicle networks.

Reference:
https://www.bender.de/en/products/insulation-monitoring/isometer-iso175/

### Rule

Alibaba may later reveal a legitimate automotive IMD supplier, but we do not downgrade from a proven automotive isolation monitor simply to save a few dollars. This device exists to detect dangerous insulation degradation from water, salt, damaged cables/connectors and other faults.

## 8. Main fuse — not an Alibaba price contest

The traction-battery main fuse must coordinate with:

- pack short-circuit current;
- contactor limits;
- cable/busbar ampacity;
- inverter/PDU faults;
- DC fast-charge current;
- crash/fault-clearing strategy.

Use a traceable automotive EV fuse from a reputable manufacturer/distributor with:

- DC voltage rating above pack maximum;
- documented time-current curve;
- interrupt rating above available fault current;
- environmental/vibration data;
- terminal/mounting specification;
- production traceability.

Alibaba can help identify manufacturers, but counterfeit/gray-market brand-name fuses are not worth the risk. Purchase-channel integrity is part of the specification.

## 9. High-voltage cable and harnesses

VolksMule should own:

- conductor size;
- route;
- bend radius;
- shielding requirement;
- connector pinout;
- HVIL conductors;
- labels;
- branch lengths;
- abrasion/heat protection;
- mounting/clamp locations.

A qualified harness supplier may manufacture the finished harness.

Prefer orange automotive HV cable with documented:

- voltage rating;
- temperature rating;
- conductor construction;
- oil/coolant/fluid resistance;
- abrasion properties;
- shielding where required;
- automotive standards compliance.

The same principle from low voltage applies: **the supplier manufactures our documented harness; the harness does not become undocumented supplier IP.**

## 10. Busbars

Busbars are highly suitable for drawing-based fabrication after the pack geometry is fixed.

Candidate manufacturing processes:

- stamped/bent copper;
- insulated laminated busbars where justified;
- plated copper;
- flexible laminated links for movement/tolerance where needed.

Require:

- material/copper grade;
- plating specification;
- cross-section and temperature-rise calculation;
- joint resistance target;
- torque specification;
- creepage/clearance;
- insulation/fire behavior;
- dimensional inspection.

Do not use the free busbars included with marketplace cells as the pack ampacity specification.

## 11. BDU/PDU ownership rule

An integrated supplier BDU/PDU may be excellent, but it only wins if we can answer:

- What is inside it?
- What fuse is inside it?
- Which contactors?
- What is the precharge topology?
- What are the busbar ratings?
- How does HVIL route?
- Which branches are protected?
- Can each internal service part be identified/replaced?
- Are the drawings and pinouts available?

If not, a visibly laid-out VolksMule BDU/PDU built from proven contactors/fuses/connectors may be the simpler long-term answer.

## 12. Initial supplier ranking

### Main contactors
1. **Hongfa** — first RFQ.
2. Alternate Tier-1 automotive contactor supplier — mandatory second source before production freeze.

### MSD / HV connectors
1. **Yonggui** — strongest system/interconnect benchmark and first engineering RFQ.
2. **Chilye** — strongest direct Alibaba-accessible low-volume candidate.

### Insulation monitoring
1. **Bender automotive ISOMETER** — benchmark and likely first Prototype 1 choice unless a peer product wins on evidence.

### Fuse
1. Reputable automotive EV fuse manufacturer/distributor selected after fault-current analysis; marketplace price secondary.

## 13. Bench/vehicle validation gates

Before energizing the integrated HV system:

- contactor coil/control logic verified at low voltage;
- auxiliary-contact state detection verified;
- precharge sequence validated with representative downstream capacitance;
- timeout and failed-precharge behavior verified;
- HVIL open/close logic verified;
- service-disconnect detection verified;
- IMD communication/fault thresholds integrated;
- main-fuse coordination reviewed against fault-current analysis;
- connector keying/HVIL/touch protection inspected;
- harness continuity, shielding and isolation tested using appropriate HV-safe procedures/equipment;
- all high-voltage work follows a documented safe-energy-state procedure.

Destructive high-energy fault tests belong with appropriately equipped labs and test facilities, not improvised workshop testing.

## Current conclusion

The high-voltage safety hardware is **highly sourceable without surrendering the architecture**.

The emerging Prototype 1 stack is:

> **manufacturer-grade LFP cells -> transparent BDU with Hongfa-class contactors + traceable main fuse + precharge -> physical Chilye/Yonggui-class service disconnect -> standardized HVIL connectors/harnesses -> Bender-class isolation monitor -> documented branches to e-axles, OBC/DC-DC, charging and thermal loads.**

Alibaba is especially useful for the Chilye-class connector/MSD layer and supplier discovery. It is not a reason to economize on the fuse or isolation monitor.

Most importantly, every HV safety function remains visible on the schematic and diagnosable locally.
