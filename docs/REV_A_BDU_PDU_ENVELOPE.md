# Revision-A BDU / transparent HV-distribution envelope

This file turns the existing high-voltage safety-plumbing research into a physical Revision-A packaging envelope for the **Battery Disconnect Unit / Power Distribution Unit (BDU/PDU)**.

It does **not** freeze final fuse size, contactor current, branch count, busbar geometry, current sensor, service disconnect, or enclosure dimensions. It exists so the pack and underbody CAD reserve real space for the hardware that safely connects the battery to the rest of the vehicle.

> **High-voltage distribution must be inspectable, diagnosable, serviceable and boring. Do not hide safety architecture in a supplier black box.**

---

## 1. Functional scope

Prototype 1 needs an HV-distribution assembly that can support, as applicable:

- traction-battery positive and negative isolation;
- precharge;
- main pack fuse;
- pack current measurement;
- service disconnect;
- HVIL;
- insulation monitoring;
- protected branch to front inverter/e-axle;
- protected branch to rear inverter/e-axle;
- OBC / AC-charge path;
- protected DC fast-charge path;
- HV-to-12-V DC/DC;
- HVAC compressor;
- HV coolant/PTC heater;
- 120-V utility/V2L inverter;
- future reserved branch space only where useful.

The exact branch topology remains open until current, fault and component-location studies converge.

---

## 2. Main-contactor physical benchmark

Hongfa is the strongest current Chinese automotive contactor path.

### Conservative packaging benchmark — HFE82V-400M

Current Hongfa data publishes:

- vehicle application family;
- **400 A continuous** carry capability at 85 °C;
- up to 1000-V switching variants;
- 12-V and 24-V coils;
- M6 load terminals;
- IP67-class sealed contact chamber;
- approximately **95.8 × 49 × 93 mm** outline in the current selection data / drawing family;
- approximately **730–740 g** mass;
- automotive/IATF manufacturing context.

### Smaller alternate — HFE82V-300C

Current data publishes:

- **300 A continuous** at 85 °C;
- up to 1000 VDC;
- approximately **88.3 × 42.5 × 74.5 mm**;
- approximately **370 g**.

### Revision-A rule

Carry **two 400-A-class contactor envelopes** in CAD—one main positive and one main negative.

This is a conservative physical reserve, **not a final electrical rating**.

The 300-A part may still win after the pack/current study. The final contactor rating follows:

- validated continuous current;
- peak duration/current;
- ambient/enclosure temperature;
- cable/busbar temperature;
- charge and discharge duty;
- fault interruption requirement;
- cell and pack limits.

Do not downsize CAD around the smallest relay first and discover later that thermal/current margin requires a larger one.

---

## 3. Precharge contactor benchmark

Hongfa's HFE82V-40E provides a useful small-HV-contactor class for the precharge path:

- 40 A continuous at 85 °C;
- up to 1000-V-class insulation/switching family;
- IP67 sealed design;
- 12/24-V-class family availability.

The precharge contactor is not selected by continuous traction current.

Final precharge hardware follows:

- total DC-link capacitance of both inverters and auxiliary HV loads;
- chosen precharge resistor;
- required precharge time;
- resistor pulse energy;
- fault cases where the main contactor fails to close;
- stuck-welded and open-circuit diagnostics.

Carry one **small 40–60-A-class HV contactor zone** plus resistor and thermal clearance.

---

## 4. Main fuse benchmark

Mersen's current **MEV50A EVpack** family is a useful automotive benchmark because it is explicitly designed for:

- EV/HEV battery-pack protection;
- BDU/BMS applications;
- 500 VDC systems;
- 60–800 A ratings;
- up to 30-kA interrupting rating at 500 VDC for the MEV50A family.

A 400-A MEV50A variant is available in compact 30G/38G/45G packages.

### Revision-A rule

Carry physical space for a **400-A-class EV fuse package** as a conservative benchmark, but do not freeze the 400-A rating.

Fuse selection must be coordinated with:

- pack maximum continuous current;
- pack short-circuit current;
- cable/busbar ampacity;
- main-contactor breaking capability;
- inverter fault-clearing needs;
- charging branch behavior;
- time-current coordination;
- minimum breaking current and arc-energy behavior.

The fuse and contactor must be selected as a coordinated protective pair, not by matching headline amperage.

---

## 5. Current sensing

A 300–400-A Hall/current-transducer class is physically modest compared with the contactors and IMD, but it still needs a straight bus/cable path and local LV wiring.

LEM's HASS family demonstrates the category:

- 300-A nominal model;
- up to 900-A measurement range on HASS 300-S;
- 5-V supply;
- galvanically isolated open-loop Hall measurement;
- automotive-like -40 to +85 °C class operating range on the documented family.

That exact HASS model is not a final recommendation and some distributor listings mark it not for new designs.

### Revision-A requirement

Reserve a **current-sensor / bus pass-through zone** near the BDU master current path.

Final sensor must provide:

- bidirectional current measurement;
- validated accuracy over temperature;
- sufficient peak range;
- bandwidth appropriate to pack protection/control;
- documented failure behavior;
- local diagnostics;
- automotive environmental qualification.

---

## 6. Insulation-monitor benchmark

Bender remains the engineering benchmark for the insulation-monitor role.

### iso165C physical benchmark

Published device dimensions are approximately:

- **141.82 mm wide**;
- **111.4 mm high**;
- **43.2 mm deep**;
- <220 g class mass in current documentation.

The iso165C is designed for electric-drive insulation monitoring and CAN integration. Its published monitored-voltage class must be reconciled with the exact final pack and transient envelope.

Bender's IR155 family provides a current 0–1000-V EV insulation-monitoring benchmark and supports 12/24-V vehicle supply.

### Revision-A rule

Carry an approximately **170 × 140 × 70-mm gross IMD/service zone**.

Do not bury the IMD where its HV/LV connectors or diagnostic access require dismantling cell compression structure.

---

## 7. Manual service disconnect / HVIL

Yonggui's current **YG1130** manual maintenance switch is a strong supplier benchmark:

- **400 A**;
- **1000 VDC** power rating;
- 24-V signal path;
- **HVIL: yes**;
- IP67/IP6K9K after mating;
- -40 to +125 °C environment;
- >=50 mating/service cycles.

Yonggui's larger ESC-MSD family publishes:

- 250 / 350 / 400-A classes;
- 1500 VDC;
- IP68 mated;
- >=200 mechanical cycles.

Exact YG1130/ESC-MSD mounting envelope for our quoted configuration still needs supplier CAD.

### Revision-A requirement

The service disconnect should be accessible from a dedicated service opening without:

- dropping the pack;
- opening the cell compartment;
- removing seats or welded structure;
- using software or cloud permission.

Reserve a provisional **~180 × 140 × 120-mm MSD/service-hand zone** at a pack edge/top service bay until Yonggui/Chilye CAD replaces it.

This is a vehicle-level placeholder, not a claim about product dimensions.

The service disconnect must interrupt HVIL before high-current contacts are physically exposed.

---

## 8. Main BDU physical layout

A transparent first layout should be organized so a competent technician can trace the energy path visually from the service manual and enclosure labels.

### Preferred sequence, conceptually

Battery cells/modules → service disconnect → main fuse → current sensing → main contactors / precharge → protected distribution branches.

The exact ordering of fuse/current sensor/contactors depends on the final safety analysis and supplier recommendations; the conceptual point is transparency and testability.

### Revision-A gross enclosure reserve

Carry approximately:

> **600 × 350 × 180 mm gross BDU/PDU service envelope**

for first whole-vehicle CAD.

This reserve is intended to fit, with service/creepage/busbar clearance:

- two 400-A-class main contactors;
- one small precharge contactor;
- precharge resistor;
- one main EV fuse;
- current sensor/shunt;
- insulation-monitor electronics where integrated into the same service bay;
- branch fuses/contactors as required;
- busbars;
- LV/HVIL connector strip;
- covers/guards;
- diagnostic/service access.

**600 × 350 × 180 mm is not a supplier product dimension.** It is an intentionally generous Revision-A integration box.

The CAD should try to shrink it only after the current/fault study and real component models are placed.

---

## 9. Separate BDU vs integrated PDU

Dilong's 3-in-1 OBC/DC-DC/PDU remains interesting only if the PDU is completely documented.

Revision A should continue to prefer a **separate transparent BDU/PDU** unless an integrated unit provides:

- complete HV block diagram;
- branch current ratings;
- fuse types and replacement method;
- contactor part numbers/ratings;
- precharge topology;
- HVIL topology;
- DC-fast-charge branch details;
- front/rear-inverter branch details;
- HVAC/PTC/V2L branches as needed;
- isolation/dielectric data;
- crash-shutdown behavior;
- local diagnostics;
- service instructions;
- individual replacement parts.

If those are withheld, the integrated PDU is a black box and loses.

> **A slightly larger transparent box is preferable to a smaller proprietary box that owns the car's HV plumbing.**

---

## 10. Branch philosophy

Do not put every HV load on one giant undifferentiated bus without branch protection.

Potential branches include:

1. front inverter/e-axle;
2. rear inverter/e-axle;
3. OBC / charge electronics;
4. DC fast-charge path;
5. HV-to-12-V DC/DC;
6. HVAC compressor;
7. PTC/coolant heater;
8. V2L inverter.

Not every branch needs an independent contactor.

Final protection/isolation strategy follows:

- wire/busbar ampacity;
- fault-current contribution;
- crash isolation needs;
- service segmentation;
- component internal contactors/fuses;
- regulatory and supplier requirements.

Use the **fewest safety devices that produce a clear, validated fault tree**, not the fewest parts possible and not maximum electronics for its own sake.

---

## 11. Pack-current mismatch is an engineering blocker, not a sourcing excuse

Current public data create an important unresolved electrical question:

- two READ2982 units are 55 kW rated each, or ~110 kW combined rated mechanical power;
- at a roughly 384-V nominal 120S LFP pack, 110 kW corresponds to roughly 286 A before losses and auxiliaries;
- combined peak drive-unit power is much higher;
- the detailed REPT 150-Ah baseline publicly documents only 150 A continuous discharge for that cell revision.

Therefore:

> **Do not freeze the BDU at 300 or 400 A until the final cell configuration and continuous-power requirement reconcile.**

Possible outcomes include:

- the 171-Ah cell has a stronger documented power rating;
- the pack uses parallel strings / another module architecture;
- continuous e-axle power is intentionally limited;
- a different automotive LFP cell wins.

The BDU packaging envelope should survive any of those plausible paths.

---

## 12. Crash and service placement

Place the BDU/PDU so that:

- the service disconnect is reachable from a protected service opening;
- high-current busbars are not directly under occupant feet without protection;
- the box is inside the battery/crash protection envelope where practical;
- crash sensors can command contactor opening;
- HVIL detects opened covers/connectors where justified;
- ordinary service does not expose live busbars;
- enclosure covers are bolted and reusable;
- fuse and contactors can be replaced after safe pack isolation;
- labels show isolation procedure and stored-energy/precharge hazards;
- coolant cannot leak onto exposed HV terminals.

---

## 13. Revision-A physical boxes to carry now

### Main contactors

Two conservative Hongfa 400-A-class envelopes:

> **~96 × 49 × 93 mm each**

### Precharge contactor

One small 40–60-A HV contactor zone.

### IMD

Gross service reserve:

> **~170 × 140 × 70 mm**

### Manual service disconnect

Gross provisional hand/service zone:

> **~180 × 140 × 120 mm**

until supplier CAD arrives.

### Complete BDU/PDU service envelope

> **~600 × 350 × 180 mm**

as the Revision-A conservative whole-box reserve.

---

## 14. Current conclusion

The BDU/PDU is no longer a blank rectangle or an invitation to buy a proprietary integrated box.

Revision A can now package a realistic transparent HV safety assembly around production-class contactors, fuse, current sensing, insulation monitoring, manual service disconnect, precharge and branch protection.

Current status:

> **BDU/PDU PACKAGING BLOCKER SUBSTANTIALLY REDUCED / FINAL ELECTRICAL RATINGS WAIT FOR CELL + CURRENT + FAULT STUDY / EXACT MSD AND BRANCH CAD STILL SUPPLIER-DEPENDENT**

The next important step is not searching Alibaba for more orange boxes. It is reconciling the pack-current requirement and then replacing the conservative placeholders with the exact quoted supplier models.

---

## 15. Sources reviewed

Public research current as of **2026-08-31**:

- Hongfa HFE82V-400M current vehicle-relay datasheet/product material;
- Hongfa HFE82V-300C current datasheet/product material;
- Hongfa HFE82V-40E current product material;
- Mersen MEV50A EVpack fuse family;
- Bender iso165C / IR155 automotive insulation-monitoring material;
- Yonggui YG1130 and ESC-MSD current product material;
- LEM HASS current-sensor family for category sizing;
- existing VolksMule `ALIBABA_HV_SAFETY_PLUMBING.md` and `ALIBABA_OBC_POWER_ELECTRONICS.md` screens.
