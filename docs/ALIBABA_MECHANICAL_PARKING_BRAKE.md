# Alibaba mechanical parking-brake sourcing screen

Research current as of **2026-09-01**.

This document closes a remaining Phase-5 brake hardware gap around a deliberately simple requirement:

> **VolksMule must be able to remain parked with both the high-voltage system and the 12-V electrical system dead.**

The Prototype-1 baseline is therefore a conventional mechanical parking brake:

**hand lever -> equalizer/adjuster -> dual Bowden cables -> mechanical rear-brake actuation.**

An electronic parking brake may be studied later only if it proves a concrete whole-vehicle advantage. It is not the baseline and it is not required for the first Mule.

---

## 1. Why the mechanical baseline fits VolksMule

A cable-operated parking brake provides:

- direct local driver control;
- no ECU dependency;
- no software state machine required to hold the vehicle;
- no 12-V motor required to apply/release;
- no cloud/app/proximity-key dependency;
- obvious failure modes;
- simple roadside diagnosis;
- ordinary independent-shop service;
- inexpensive replaceable cables and lever hardware.

This matches the broader project principle:

> **The computer does not own the vehicle.**

---

## 2. Working architecture

### Driver control

First study:

- conventional center-console hand lever;
- ratchet/pawl mechanical hold;
- obvious physical released/applied state;
- simple switch only for the parking-brake telltale if needed.

A foot-operated mechanical pedal remains an alternate if cabin packaging proves materially better, but the hand lever is easier to inspect, service and modulate during prototype work.

### Force distribution

Preferred layout:

- one front cable or direct lever pull;
- mechanical equalizer/compensator;
- independent left/right rear Bowden cables;
- threaded or equivalent mechanical adjustment;
- no powered actuator in the force path.

### Rear actuation

First preference:

- mechanical parking-brake lever integrated into the selected rear caliper.

Alternative:

- drum-in-hat parking brake if the final rear rotor/hub family naturally supports it and the packaging/service benefit is worth the extra shoes/springs/hardware.

Do not choose drum-in-hat merely because it is traditional; do not choose an electric rear caliper merely because it is modern.

---

## 3. Strong cable supplier — Dongguan SumHo Control Cable

SumHo is the strongest current Chinese control-cable lead found for this function.

Current manufacturer material states:

- company founded in 2000;
- automotive brake/control/Bowden cable design and production;
- parking/handbrake cable products;
- custom development capability;
- in-house R&D and test equipment;
- IATF 16949 certification shown by the manufacturer;
- ISO 9001, ISO 14001 and SA8000 claims/certification material;
- large-scale cable production;
- automotive customer/support experience.

Current manufacturer pages explicitly show handbrake/brake cable products rather than only throttle or lawn-equipment cables.

Sources:

- https://www.sum-ho.com/
- https://www.sum-ho.com/r-d-capabilities.html
- https://www.sum-ho.com/Auto-Mobile-Control-Cable-pl42246347.html

### Current verdict

> **STRONG YELLOW-GREEN custom parking-brake cable supplier path once rear-brake geometry is known.**

Why it fits:

The cable is exactly the sort of component VolksMule should specify by interface and performance rather than invent internally.

We can define:

- sheath length;
- free cable length;
- effective travel;
- end fittings;
- bracket interfaces;
- routing radius;
- load;
- corrosion protection;
- temperature range;
- fatigue/life target;

and let a mature control-cable manufacturer build it.

---

## 4. Alibaba-direct alternate — Hebei Junxiang

Alibaba currently lists **Hebei Junxiang Auto Spare Parts Co., Ltd.** as an IATF-16949-filtered supplier with factory-direct parking-brake cables, including left/right Hyundai Tucson references.

Current public listings show:

- existing parking-brake cable production;
- IATF 16949 marketplace certification filter;
- full-customization/ODM capability on supplier pages;
- ordinary production MOQs around 100 pieces on existing parking-brake listings.

Sources:

- https://www.alibaba.com/catalog/Auto-Brake-Cables_cid127686027?categoryId=127686027&companyAuthTag=IATF+16949
- https://www.alibaba.com/gear-shifting-control-cable-suppliers.html

### Current verdict

> **YELLOW-GREEN alternate production supplier; public MOQ makes it more attractive after cable geometry settles than during Mule-1 iteration.**

---

## 5. Lever assembly — donor/common first

Alibaba contains complete handbrake lever assemblies and generic mechanical levers, but the lever is not a place where custom production gives Prototype 1 much value.

A mature donor/common lever already provides:

- stamped/forged structure;
- pivot;
- ratchet and pawl;
- release button/rod;
- return spring;
- cable attachment;
- mounting flange;
- switch provision for telltale.

### Preferred strategy

1. package a common compact-car/SUV handbrake lever assembly;
2. select based on lever ratio, travel, mounting geometry and local service availability;
3. adapt the floor bracket to the lever rather than commissioning a unique ratchet mechanism;
4. custom lever only if cabin/cargo packaging proves a real conflict.

### Current verdict

> **DONOR / BUY common lever assembly first. Alibaba is an alternate source after a useful geometry is identified.**

A lever that happens to be cheap is not useful if its cable travel and mechanical advantage do not match the rear brakes.

---

## 6. Force and travel are the real interface

The parking brake must be designed as a force/travel chain.

Need to establish:

### Rear brake requirement

- cable force required at each rear caliper/shoe mechanism;
- cable travel from released to fully applied;
- mechanism return force;
- allowable overtravel;
- wear-compensation behavior;
- left/right tolerance.

### Lever requirement

- lever arm length;
- mechanical ratio;
- useful handle travel;
- maximum reasonable driver hand force;
- ratchet tooth spacing;
- reserve travel after pad/shoe wear;
- release force.

### Cable requirement

- tensile load with safety margin;
- operating travel;
- elastic stretch under load;
- friction/hysteresis through actual routing;
- sheath compression;
- minimum bend radius;
- temperature/corrosion effects;
- end-fitting retention.

> **Overall cable length alone is not a parking-brake specification.**

SumHo's own current engineering material emphasizes travel/stroke, routing friction and lost motion as key cable-design variables.

---

## 7. Equalizer and adjustment

A mechanical equalizer is preferred so one lever can actuate both rear wheels while accommodating small cable differences.

Design requirements:

- left/right load sharing;
- visible mechanical condition;
- corrosion-resistant hardware;
- accessible adjustment;
- no hidden proprietary automatic actuator;
- enough adjustment for manufacturing tolerance and cable bedding;
- service procedure that does not require special software.

The equalizer itself can be:

- stamped steel;
- forged/machined simple hardware;
- donor/common assembly;
- locally fabricated to drawing.

This is not a high-value custom electronics problem.

---

## 8. Cable routing rules

Route the cables so they are protected but replaceable.

Require:

- broad bend radii;
- no contact with rotating CV shafts;
- no full-jounce/rebound tension changes that apply the brake;
- no exhaust-system issue in an EV, but still protect from e-axle/inverter/rotor heat;
- stone/salt/water protection;
- drainage rather than trapped water;
- clips that can be released with ordinary tools;
- no routing inside a sealed structural cavity that requires cutting the body to replace a cable;
- enough slack for cradle/suspension movement but not enough to snag.

If rear cradle removal requires disconnecting the parking-brake cables, that interface should be deliberate and easy to access.

---

## 9. Environmental and durability gates

The final cable system should be qualified for:

- salt spray/corrosion;
- water and mud exposure;
- freeze/thaw;
- low-temperature stiffness;
- high-temperature softening near brakes;
- repeated application cycles;
- tensile proof load;
- end-fitting pullout;
- sheath retention;
- abrasion/chafe;
- contamination ingress;
- parking on grade under GVWR conditions.

Prototype bench/vehicle tests should include:

- dry new system;
- wet/salted system;
- cold-soaked system;
- worn rear pads/shoes;
- one cable with increased friction;
- asymmetric adjustment;
- cable disconnect/failure;
- full-GVWR grade hold;
- release after extended high-load application.

---

## 10. Parking-brake telltale

A simple mechanical/electrical switch at the lever is sufficient for the driver warning/telltale path.

The telltale may be read by the cluster/vehicle controller, but the switch does **not** control the brake.

A failed telltale circuit must not release or prevent application of the mechanical brake.

---

## 11. Relationship to the service brake

The parking brake is not a substitute for the four-wheel hydraulic service brake.

The road-intent brake architecture remains:

- hydraulic friction service brakes;
- conventional master-cylinder/assist foundation;
- calibrated ABS/ESC/AEB pressure control;
- regen layered around friction braking;
- independent mechanical parking hold.

The mechanical parking brake may offer limited emergency deceleration if manually applied, but its primary design requirement is secure static holding.

---

## 12. BUY / ADAPT / DESIGN verdict

| Part | Current verdict |
|---|---|
| Hand lever / ratchet | **DONOR / BUY common assembly** |
| Lever mounting bracket | **DESIGN / local fabrication** |
| Equalizer | **DONOR / BUY / simple drawing-based fabrication** |
| Left/right Bowden cables | **BUY to geometry/performance specification** |
| Cable supplier | **SumHo first Chinese lead; Hebei Junxiang alternate** |
| Rear caliper mechanical lever | **BUY as part of selected rear brake family** |
| Drum-in-hat mechanism | **ADAPT only if final rear brake family makes it worthwhile** |
| Parking-brake switch | **BUY common mechanical switch** |
| EPB motor/control ECU | **NOT BASELINE** |

---

## 13. Exact-selection blockers

Do not freeze cable or lever part numbers until we know:

- rear caliper / parking-brake mechanism;
- required force and travel;
- rear corner position;
- rear cradle/body routing;
- lever location relative to seats/cargo platform;
- floor/body bracket structure;
- final grade-hold requirement at working GVWR.

These are geometry/load blockers, not supplier-availability blockers.

---

## 14. Current conclusion

The parking brake does not need to become an electronic subsystem.

The preferred Prototype-1 architecture is:

> **common mechanical hand lever + visible equalizer/adjustment + two ordinary Bowden cables + mechanical rear-brake actuation.**

SumHo is the strongest current custom-cable supplier lead; Hebei Junxiang is a credible Alibaba-direct alternate once geometry is stable.

For Mule #1, the lever and possibly the first cables may still be sourced from a common donor/local application because iteration speed matters more than production price.

That is not a compromise. It is the correct prototype use of a mature mechanical system.
