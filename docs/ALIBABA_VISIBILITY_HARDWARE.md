# Alibaba visibility / glass / lighting / wiper sourcing screen

This document continues the VolksMule Alibaba sourcing mission for Prototype 1.

The existing architecture says that glass, lamps, mirrors and wipers are areas where **suppliers have already solved regulated hardware** and the body should adapt to proven equipment when the compromise is small.

This screen reinforces that philosophy strongly.

The systems covered here are:

- windshield and other glazing;
- headlamps;
- tail / stop / turn / marker / reverse lamps;
- physical mirrors;
- rear-visibility camera/display;
- windshield wiper motor/linkage/arms/blades;
- washer pump/reservoir/nozzles.

The rule is:

> **Buy certified/validated visibility hardware; design the body and controls around it; do not casually redesign optics, glazing chemistry or wipe geometry.**

---

## 1. Regulatory baseline

Prototype 1's working U.S. MPV classification makes several visibility standards directly relevant.

### FMVSS 205 — glazing

FMVSS 205 specifies motor-vehicle glazing requirements intended to address impact injury, transparency/driver visibility and occupant retention.

NHTSA's glazing interpretations explain that safety glazing carries location/type markings such as AS1/AS2 and a DOT manufacturer code; the manufacturer is self-certifying compliance rather than receiving a product approval from NHTSA.

Current rule / guidance:

- https://www.law.cornell.edu/cfr/text/49/571.205
- https://www.nhtsa.gov/interpretations/04-005893drn1

### FMVSS 108 — lighting

FMVSS 108 applies to required lamps, reflective devices and associated equipment and specifies vehicle-level and lamp-level requirements including photometry, color, location, activation and markings.

Current rule:

- https://www.law.cornell.edu/cfr/text/49/571.108

NHTSA has specifically explained that an LED can be used as part of a compliant **integral-beam headlamp** whose complete optical assembly satisfies FMVSS 108, while a generic LED replacement light source cannot simply be put into a replaceable-bulb headlamp unless the light source itself conforms to the applicable Part 564 requirements.

Source:

- https://www.nhtsa.gov/interpretations/571108-ncc-230201-001-led-headlights-m-baker

### FMVSS 111 — mirrors / rear visibility

For an MPV at Prototype 1's working weight, FMVSS 111 requires compliant rear visibility and a rearview image system. Current requirements include field of view, image size, default behavior and a rearview image displayed within 2 seconds of the start of a backing event.

Current rule:

- https://www.law.cornell.edu/cfr/text/49/571.111

### FMVSS 104 — windshield wiping / washing

FMVSS 104 applies to MPVs and requires a powered windshield wiping system and a windshield washing system. Current text requires at least two wiping speeds/frequencies and establishes test requirements for the system.

Current rule:

- https://www.law.cornell.edu/cfr/text/49/571.104

---

## 2. Central sourcing finding

These systems divide cleanly into two categories.

### Regulated product hardware we should BUY

- windshield / side / rear glazing;
- complete compliant headlamp modules;
- complete compliant rear/signaling lamp modules;
- reflectors / markers;
- mirror glass / housings;
- wiper motors and linkages;
- wiper blades;
- washer pumps/nozzles;
- camera and display hardware where appropriate.

### Vehicle geometry / integration we must DESIGN and VERIFY

- windshield opening and bonding flange;
- driver sightlines;
- wiper pivot locations and wipe pattern;
- lamp mounting locations/aim;
- mirror positions/field of view;
- rear-camera placement;
- rear-camera display location/behavior;
- wiring/control logic;
- service access;
- defrost/washer interactions.

A compliant component can still produce a noncompliant vehicle if installed incorrectly.

---

## 3. Windshield strategy — ADAPT a common existing windshield first

This screen produces a strong architectural recommendation:

> **Before commissioning a unique windshield, attempt to design Prototype 1 around a common mass-market laminated AS1 windshield with a durable North American replacement ecosystem.**

Why:

- windshield tooling/curvature is specialized;
- optical quality matters;
- the glass must remain easily replaceable after stone impact/cracking;
- glass dimensions affect roof/A-pillar/cowl structure;
- wiper geometry follows windshield shape;
- an existing high-volume windshield may have many independent replacement manufacturers;
- a unique low-volume windshield can immobilize a vehicle years later.

This is one of the rare cases where it can be smarter to adapt body sheet metal to an existing regulated commodity than to optimize the body around a blank sheet of paper.

### Selection criteria for a donor/common windshield family

Prefer:

- laminated AS1 windshield;
- active U.S. replacement availability from multiple manufacturers/distributors;
- simple curvature;
- no dependency on an embedded proprietary display or electronics;
- camera/sensor bracket either absent, removable, or harmless if unused;
- reasonable width/height for the Prototype 1 occupant package;
- favorable A-pillar visibility;
- wiper system with easy-to-source arms/blades;
- no giant panoramic extension into the roof.

Do **not** freeze an exact donor windshield until body/occupant packaging work compares candidates.

---

## 4. Shanghai Yaohua Pilkington (SYP) — strongest Alibaba-direct glass lead

Alibaba currently lists Shanghai Yaohua Pilkington Glass Group directly for automotive laminated windshields.

Alibaba market source:

- https://www.alibaba.com/countrysearch/CN/laminated-auto-glass.html

SYP's own current material states that it:

- was founded in 1983;
- operates a major automotive glazing business;
- produces millions of automotive-glass sets annually;
- offers windshield, backlite, side-window and other automotive glazing;
- produces laminated windshields with options including heat-insulating, acoustic and HUD configurations;
- has extensive automotive/OEM glazing experience.

Sources:

- https://www.sypglass.com/en/about
- https://www.sypglass.com/en/productdetail?id=87
- https://www.sypglass.com/en/product?parentId=13

### Current verdict

**STRONG YELLOW — first Alibaba glass supplier worth an engineering RFQ.**

For VolksMule the initial question is not necessarily "make us a unique windshield." First ask whether SYP can supply a current high-volume existing windshield family suitable for our envelope with the required U.S. markings and long-term replacement path.

Only then investigate custom tooling.

---

## 5. Xinyi / XYG — strongest U.S.-traceability benchmark

Xinyi is a major global automotive-glass supplier. Its current product material states that its automotive glazing holds U.S. DOT, European ECE, Chinese CCC and other certifications and includes windshields, side/rear glass, HUD, acoustic and ADAS-compatible products.

Source:

- https://www.xinyiglass.com/CarGlass/index.aspx

More importantly for U.S. traceability, NHTSA's current Manufacturer Information Database lists active Xinyi automotive-glass manufacturing entities and plants as glazing manufacturers. One active Beihai plant is recorded with **DOT glazing code 1134**, and the Shenzhen plant is recorded with **DOT code 563**.

Sources:

- https://vpic.nhtsa.dot.gov/mid/equipplant/details/20652
- https://vpic.nhtsa.dot.gov/mid/equipplant/details/19222
- https://vpic.nhtsa.dot.gov/mid/manufacturer/details/25614

### Current verdict

**BENCHMARK / strong sourcing target even if the exact transaction is not through Alibaba.**

This is the level of traceability we want from any Alibaba glass supplier: exact manufacturing plant and exact DOT code, not just a photo of "DOT" etched into glass.

---

## 6. Fuyao — North American replacement benchmark

Fuyao operates automotive-glass facilities in North America, including Ohio, and describes its products as OEM-quality automotive glass for the North American market.

Sources:

- https://fuyaousa.com/contact/
- https://www.fuyaona.com/

NHTSA's manufacturer database also contains current Fuyao glazing manufacturing entities.

Source:

- https://vpic.nhtsa.dot.gov/mid/manufacturer/details/24520

### Current verdict

**BENCHMARK / possible direct North-American supply path.**

Fuyao demonstrates why Volkswagen-style commodity glass sourcing need not mean importing every pane from an Alibaba storefront. Alibaba is discovery; final sourcing should use the strongest accessible supply route.

---

## 7. Generic Alibaba windshield suppliers — useful only after code verification

Alibaba currently lists thousands of laminated automotive-glass products and suppliers advertising DOT/E-mark windshields, including:

- Shandong Seto;
- Heshan Zhengda;
- Shandong Hengbang;
- Hunan Cang Mao Te;
- Changchun Sunshine;
- other vehicle-specific glass traders/manufacturers.

Sources:

- https://www.alibaba.com/countrysearch/CN/front-windshield-glass.html
- https://www.alibaba.com/countrysearch/CN/laminated-auto-glass.html
- https://www.alibaba.com/supplier/dot-windshield-codes.html

### Current verdict

**YELLOW until exact plant/DOT-code/test evidence is verified.**

The seller must provide:

- actual prime glazing manufacturer;
- DOT code;
- AS marking;
- exact glass construction;
- traceable manufacturing plant;
- drawing/tolerance data;
- compliance/test evidence appropriate to the product.

NHTSA explicitly states that the DOT code and glazing markings indicate manufacturer certification; NHTSA does not pre-approve the glass.

---

## 8. Side and rear glazing — BUY common/simple safety glazing

Prototype 1 should avoid stylistic shapes that make side/rear glass expensive or irreplaceable.

Prefer:

- simple conventional door-glass shapes;
- fixed quarter glass only where it materially improves visibility;
- ordinary tempered or laminated safety glazing as permitted by location/requirements;
- large useful rear window;
- no panoramic roof;
- no electrochromic roof or roof glass as a base requirement.

Body styling should keep glass curvature modest where practical.

### Service philosophy

A broken side window should be a glass-shop problem, not a body-shell redesign.

---

## 9. Headlamp architecture — use complete standardized optical modules

Do not source "LED bulbs" and invent a reflector around them.

The preferred architecture is:

**complete integral optical headlamp module -> simple body mounting/aiming bracket -> ordinary wiring/control.**

This makes the supplier responsible for the lamp optics while VolksMule is responsible for correct installation, aim, activation and vehicle-level compliance.

### Why complete modules matter

NHTSA's current interpretation makes clear that LED light sources can form part of an integral-beam headlamp when the **complete headlamp** satisfies the required performance. Generic LED replacements for a replaceable-bulb headlamp are a different regulatory problem.

Source:

- https://www.nhtsa.gov/interpretations/571108-ncc-230201-001-led-headlights-m-baker

### Preferred style of component

Investigate:

- standardized round/rectangular integral LED high/low modules;
- 90-mm-class modular lamps;
- 7-inch round integral modules where packaging/style works;
- separate simple DRL/parking/turn modules if needed.

A visible standardized lamp may look less fashionable than a giant sculpted headlamp housing, but it is vastly easier to replace.

---

## 10. Alibaba headlamp market — GREEN category, exact product YELLOW

Alibaba directly lists complete headlamp modules advertised with DOT/SAE/E-mark compliance.

### Guangzhou Funing — useful evidence-rich Alibaba supplier

Alibaba's current verified supplier profile for Guangzhou Funing includes third-party-recorded certification entries for automotive headlamps, including DOT and E-mark certificate records with product coverage and validity periods.

Source:

- https://suppliers.alibaba.com/guangzhou-funing-automotive-technology-co-ltd_2206878986005

### Guangzhou Yuguang — another evidence-rich supplier

Alibaba's verified profile for Guangzhou Yuguang Automotive Lighting includes current third-party certification entries for headlamp functions and DOT records.

Source:

- https://suppliers.alibaba.com/guangzhou-yuguang-automotive-lighting-co-ltd_2210870223080

### G-View — manufacturing/certification lead

Alibaba's verified G-View profile includes manufacturing inspection information plus DOT/E-mark certificate entries for lighting products.

Source:

- https://suppliers.alibaba.com/dongguan-g-view-lighting-technology-co-limited_17380530021

### Current verdict

**GREEN supplier ecosystem / YELLOW exact lamp.**

Before selection, obtain the exact FMVSS 108 photometric/test documentation for the exact complete lamp assembly—not a general company certificate and not a certificate for a different lamp.

---

## 11. Headlamp marking / photometry gate

NHTSA test-procedure material identifies DOT marking requirements for headlamps as the manufacturer's certification indication, while FMVSS 108 sets the underlying performance requirements.

Source:

- https://www.nhtsa.gov/sites/nhtsa.gov/files/tp-108-13.pdf

For each exact candidate require:

- manufacturer/trademark marking;
- DOT marking applicable to exact lamp;
- exact model/part number;
- photometric report;
- beam pattern/test points;
- color compliance;
- environmental/temperature testing;
- vibration;
- water/dust ingress;
- aim mechanism;
- mounting orientation tolerance;
- EMC evidence as appropriate;
- replacement availability.

Do not accept a generic supplier statement that a whole product family is "DOT approved."

---

## 12. Tail / stop / turn / reverse lamps — standard modular lamps preferred

Rear lighting is an especially good place to refuse styling-driven complexity.

Prefer separate or simple combination modules using standardized mounting geometry where possible for:

- tail/position;
- stop;
- turn;
- reverse;
- side marker;
- license plate illumination;
- center high-mounted stop lamp.

Benefits:

- inexpensive replacement;
- individual failure does not require replacing a giant body-wide lamp;
- easier wiring diagnosis;
- body design does not need to carry a complex illuminated styling element.

A standardized truck/trailer-style lamp family may be worth evaluating if exact photometric/location requirements for the MPV are satisfied.

### Current verdict

**GREEN category.** Exact modules require FMVSS 108 evidence and vehicle-location verification.

---

## 13. Mirrors — conventional physical mirrors remain the baseline

Prototype 1 already rejects camera-only mirrors absent a compelling reason.

That remains the right decision.

Physical outside mirrors are:

- cheap;
- immediately understandable;
- functional with the vehicle powered down;
- easy to replace;
- legally straightforward;
- less dependent on screens/cameras/software.

### Shanghai Xinmao — supplier reference

Shanghai Xinmao states that it manufactures automotive rearview mirrors, is IATF 16949 certified and supplies vehicle manufacturers including bus OEMs.

Source:

- https://www.xinmaoauto.com/

### JDONG — Tier-1 vision-system benchmark

JDONG states that it has produced vehicle mirrors since 1985, operates under IATF 16949 and supplies 24 vehicle manufacturers including Ford.

Source:

- https://jdong-group.com/

### Current verdict

**GREEN category / supplier choice later.**

We do not need power folding, memory, cameras, puddle lamps or blind-spot LEDs in the base mirror unless a real requirement justifies them.

Simple electric adjustment and heat may be reasonable convenience/safety features if they remain serviceable.

---

## 14. Rear visibility camera — required system, but keep it independent and boring

FMVSS 111 requires the rearview image system for the working MPV class/weight and includes vehicle-level requirements such as field of view, image size, default view and response within 2 seconds of backing initiation.

Source:

- https://www.law.cornell.edu/cfr/text/49/571.111

### Architecture

Prefer:

**rear camera -> safety-related local video path -> display available immediately in Reverse**

The display may be shared with another instrument/display surface if the architecture guarantees the required rear image even when entertainment/navigation/general-purpose software is unavailable or rebooting.

### Durable principle

**The reverse camera is not an infotainment feature.**

It must not depend on:

- cloud login;
- phone pairing;
- internet connection;
- navigation application;
- a slow booting consumer OS;
- subscription service.

### Supplier search

Alibaba contains enormous numbers of automotive cameras and displays. At this stage the exact camera is less important than verifying the final vehicle's field of view and timing. Treat generic cameras as development hardware until environmental/durability and image-performance testing is complete.

---

## 15. Windshield wipers — BUY motor/linkage/blades; VERIFY the wipe envelope

Wiper motors, linkages, arms and blades are ordinary automotive commodities.

Alibaba has extensive supplier listings for complete wiper systems and linkages.

Examples:

- https://www.alibaba.com/wiper-linkage-assembly-suppliers.html
- https://www.alibaba.com/supplier/drive-wiper.html

### Preferred strategy

If Prototype 1 adapts a common existing windshield, strongly consider adapting its **wiper geometry** as a package:

- pivot spacing/location;
- arm lengths;
- blade lengths;
- linkage stroke;
- motor park logic.

We do not necessarily need to use the exact donor motor, but starting from a known windshield/wipe geometry dramatically reduces iteration.

### Do not assume donor compliance transfers automatically

The final body/windshield installation changes the driver's eye reference, daylight opening and wiped field.

We still verify the actual finished vehicle against FMVSS 104.

---

## 16. Wiper motor / linkage supplier ecosystem

Alibaba listings include manufacturers and suppliers of:

- wiper motors;
- wiper transmissions/linkages;
- complete front-wiper mechanisms;
- rear wiper mechanisms;
- washer pumps/nozzles.

One current Alibaba category includes IATF-16949-labeled wiper suppliers, while Ruian Jixiang lists wiper motor/linkage assemblies across production vehicle families.

Sources:

- https://www.alibaba.com/supplier/drive-wiper.html
- https://www.alibaba.com/wiper-linkage-assembly-suppliers.html

### Current verdict

**GREEN commodity.**

Exact selection should follow the windshield geometry and required torque/wipe rate.

---

## 17. Wiper system requirements

FMVSS 104 current text requires a powered wiping system with required frequency behavior and a washing system for the working vehicle class.

Source:

- https://www.law.cornell.edu/cfr/text/49/571.104

The final wiper system must be tested for:

- high speed;
- lower speed;
- speed separation;
- wet-wipe coverage;
- motor torque under wet/heavy conditions;
- park repeatability;
- icing/load protection;
- blade lift at road speed;
- no contact with windshield trim/body;
- washer coverage.

---

## 18. Wiper controls — physical switch

The existing controls canon remains correct:

- wipers/washers get a dedicated physical control;
- no touchscreen dependency;
- intermittent logic may be electronic but ordinary low/high operation must remain immediately accessible.

Rain sensing is not required for Prototype 1.

---

## 19. Washer system — extremely boring on purpose

BUY:

- ordinary 12-V washer pump;
- simple reservoir;
- replaceable hose;
- ordinary check valve;
- serviceable nozzles.

DESIGN:

- reservoir location/fill access;
- hose routing;
- nozzle aiming/location;
- freeze protection and body integration.

Do not integrate the washer reservoir into an expensive unrelated thermal/body module just to save one bracket.

---

## 20. Exterior lighting controls remain simple

Required lamps should be controlled through ordinary vehicle electronics with deterministic local behavior.

Basic lighting must remain functional without:

- infotainment;
- phone;
- cloud;
- remote account.

Physical controls remain required for headlights, turn signals and hazards.

A body controller may supervise the circuits, but documented fusing, connectors and diagnostics are required.

---

## 21. Lighting serviceability rule

Avoid the modern failure mode where a minor LED or lens failure requires a $1,500–$4,000 sculpted lamp assembly.

Prefer:

- standardized replaceable modules;
- accessible mounting screws;
- separate lamp from body trim;
- documented connector pinout;
- no coded/pairing requirement for ordinary replacement;
- no body disassembly beyond reasonable trim removal.

If a lamp includes electronics, replacement should not require manufacturer online authorization.

---

## 22. Candidate ranking

| Function | Candidate / family | Status | Why |
|---|---|---:|---|
| Windshield architecture | Common existing mass-market AS1 windshield | **PREFERRED FIRST PATH** | Replacement ecosystem + proven optics + reusable wiper geometry |
| Automotive glass supplier | SYP / Shanghai Yaohua Pilkington | **STRONG YELLOW** | Alibaba-direct major automotive-glass manufacturer |
| Automotive glass benchmark/supply | Xinyi / XYG | **STRONG BENCHMARK** | Active NHTSA glazing plants/DOT codes, global auto-glass supplier |
| North American glass benchmark | Fuyao | **STRONG BENCHMARK** | U.S. production/supply footprint and OEM-grade glass |
| Generic Alibaba custom windshield | Various | **YELLOW** | Possible but exact prime manufacturer/DOT code/test evidence mandatory |
| Headlamp architecture | Complete integral optical module | **GREEN CATEGORY** | Lets specialist own optics; body owns mounting/aim |
| Alibaba lighting supplier | Funing / Yuguang / G-View | **YELLOW exact product** | Verified supplier/certification evidence exists; exact photometry still required |
| Tail/turn/stop lamps | Standard modular lamp family | **GREEN CATEGORY** | Simple, replaceable, broad supplier ecosystem |
| Outside mirrors | Conventional physical mirrors | **GREEN CATEGORY** | Cheap, robust, no software dependency |
| Rear camera | Dedicated/local compliance path | **REQUIRED / YELLOW exact hardware** | Vehicle-level field/timing/durability must be validated |
| Wiper motor/linkage | Common automotive system | **GREEN** | Mature commodity; wipe geometry remains vehicle-level |
| Washer pump/nozzles | Ordinary 12-V hardware | **GREEN** | Solved commodity |
| Camera-only mirrors | — | **RED for Prototype 1** | Adds failure/software dependence without sufficient benefit |
| Giant sculpted proprietary lamps | — | **RED** | Costly, fragile, single-source styling complexity |
| Generic LED bulb in halogen optics | — | **RED** | Wrong regulatory/optical architecture |

---

## 23. New durable requirements produced by this screen

### VIS-001 — Common windshield first

Prototype 1 must evaluate common existing AS1 windshield families before commissioning a unique windshield. Unique glazing requires a concrete packaging/safety reason.

### VIS-002 — Glazing traceability

Road-intent glazing requires the actual prime glazing manufacturer, permanent required markings, exact DOT manufacturer code where applicable, part/drawing traceability and product-specific compliance evidence.

### VIS-003 — Windshield and wiper are a package

Windshield selection and wiper geometry must be developed together. Reusing a proven windshield/wiper envelope is preferred when it fits the vehicle.

### VIS-004 — Complete headlamp optics

Prototype 1 uses complete compliant optical headlamp modules. Generic LED retrofit bulbs do not define the base headlighting architecture.

### VIS-005 — Lighting remains modular

Required lighting should use individually replaceable modules rather than a body-wide proprietary lamp assembly wherever practical.

### VIS-006 — Physical mirrors remain primary

Conventional physical outside mirrors remain the Prototype 1 baseline. Camera-only mirrors are not required.

### VIS-007 — Reverse camera is safety-related

The required rearview image path must not depend on cloud, phone pairing or general-purpose infotainment availability.

### VIS-008 — Wiper compliance is vehicle-level

A compliant/known motor or donor linkage does not prove the final vehicle wipe pattern. The completed vehicle must be tested against its applicable FMVSS 104 requirements.

### VIS-009 — Visibility beats styling

A-pillar, glazing, mirror and lamp styling choices must not materially degrade natural visibility or force bespoke replacement hardware without a compensating engineering benefit.

---

## 24. First RFQ — automotive glass

Ask SYP and/or other prime automotive glazing manufacturers for two paths.

### Path A — existing high-volume windshield

Request candidate current passenger-SUV windshields approximately compatible with the Prototype 1 width/height envelope and provide:

1. exact dimensions and curvature/CAD;
2. daylight opening / frit geometry;
3. AS and DOT markings;
4. prime manufacturing plant and DOT code;
5. glass/PVB construction;
6. optical test data;
7. acoustic/solar options;
8. camera/sensor bracket options;
9. part availability history;
10. North American replacement/distributor availability;
11. sample price/MOQ.

### Path B — custom windshield

If necessary request:

1. tooling/NRE cost;
2. minimum annual volume;
3. prototype process;
4. curvature/manufacturing limits;
5. tolerance stack;
6. optical-distortion analysis;
7. FMVSS 205 test/certification responsibility;
8. permanent marking process;
9. mold/tool ownership;
10. replacement lifetime / minimum reorder conditions.

---

## 25. First RFQ — headlamp module

Ask candidate lighting suppliers for a **complete integral headlamp**, not a retrofit bulb.

Require:

1. exact model number;
2. high/low beam functions;
3. 12-V electrical range and power;
4. exact DOT/manufacturer markings;
5. FMVSS 108 photometric test report for the exact part;
6. beam-pattern plots/test points;
7. aiming method;
8. permitted mounting orientation;
9. operating temperature;
10. ingress rating/testing;
11. vibration testing;
12. EMC testing;
13. connector/pinout;
14. CAD;
15. replacement availability;
16. MOQ/sample pricing;
17. lifecycle/change-notification policy.

---

## 26. Rear camera/display RFQ

Require:

1. automotive temperature range;
2. ingress rating;
3. field of view/lens distortion data;
4. low-light performance;
5. boot/wake time;
6. video interface;
7. display compatibility;
8. diagnostics/fault reporting;
9. reverse-trigger architecture;
10. durability testing;
11. CAD/connector;
12. long-term replacement support.

System-level FMVSS 111 compliance remains VolksMule's responsibility.

---

## 27. Wiper system RFQ

Once the windshield candidate is selected, request:

1. compatible motor/linkage geometry;
2. motor stall/rated torque;
3. low/high wipe frequency;
4. park switch/interface;
5. arm spline geometry;
6. available blade lengths;
7. operating voltage/current;
8. stall/ice protection;
9. temperature and endurance tests;
10. corrosion testing;
11. CAD;
12. service parts;
13. sample price/MOQ.

---

## 28. Validation plan

### Glazing

- verify markings/manufacturer code;
- dimensional fit;
- optical distortion;
- visibility from driver eye points;
- bonding/flange fit;
- water leak;
- defrost/defog interaction;
- stone/impact qualification through supplier evidence and applicable testing.

### Lighting

- inspect markings;
- bench electrical/thermal test;
- aim range;
- verify photometric documentation;
- vehicle mounting height/location/visibility;
- low/high/turn/hazard/brake/reverse logic;
- water/vibration exposure;
- replacement procedure.

### Rear visibility

- required field-of-view test targets;
- image size;
- reverse-start response time;
- default view;
- camera dirt/water exposure;
- display boot/restart behavior;
- fault reporting.

### Wipers/washers

- sweep geometry against final windshield/driver reference;
- low/high frequency;
- wet clearing;
- washer coverage;
- heavy-water/drag torque;
- park consistency;
- icing protection strategy;
- blade replacement/access.

---

## 29. What remains open

Do not freeze yet:

- exact windshield donor family;
- custom vs donor side glass;
- exact headlamp module;
- lamp styling/placement within regulatory envelope;
- mirror size/housing;
- rear camera/display part number;
- wiper motor/linkage/blade geometry;
- washer reservoir/nozzle placement.

These converge with body CAD, occupant sightlines, crash structure and electrical architecture.

---

## 30. Mission verdict

Alibaba is **extremely useful for the visibility hardware**, but the strongest lesson is not "customize everything cheaply."

It is nearly the opposite:

**Use the global supplier ecosystem to avoid custom things.**

A common windshield, standardized complete lamp modules, conventional mirrors, a simple locally wired rear camera and commodity wiper hardware can make VolksMule easier to certify, easier to build and dramatically easier to keep alive decades later.

The vehicle body should accommodate those solved components whenever the compromise is small.
