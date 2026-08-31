# Alibaba suspension corners / hubs / dampers sourcing screen

This document continues the VolksMule Alibaba sourcing mission for Prototype 1.

The existing architecture requires:

- independent suspension at all four wheels;
- conventional coil springs;
- conventional replaceable dampers;
- ordinary bushings and ball joints where practical;
- replaceable hubs/bearings;
- bolt-on front and rear suspension cradles;
- enough travel for genuine rough-road use;
- anti-roll bars only as required by handling/ESC development;
- no air suspension, adaptive dampers or active anti-roll hardware as base requirements;
- the smallest common wheel diameter that safely clears the final brakes and preserves useful tire sidewall.

The sourcing question is therefore not "can Alibaba sell us a suspension?" It obviously can.

The real question is:

> **Which suspension pieces should be common bought hardware, which should be fabricated to our drawings, and which geometry must remain owned by VolksMule?**

---

## 1. Central finding

Alibaba and the broader Chinese automotive supplier ecosystem are exceptionally strong for:

- control arms;
- ball joints;
- bushings;
- tie rods and stabilizer links;
- wheel hubs and hub-bearing units;
- steering knuckles / hub carriers;
- dampers and complete struts;
- coil springs;
- forged, cast, stamped and machined chassis parts.

But the following are **whole-vehicle geometry**, not catalog commodities:

- suspension hard-point locations;
- control-arm lengths and angles;
- knuckle steering-arm location;
- rack position relative to the inner tie rods;
- kingpin / steering-axis geometry;
- caster;
- camber and camber gain;
- scrub radius;
- bump steer;
- roll-center location/migration;
- anti-dive / anti-lift / anti-squat geometry;
- wheel travel;
- jounce/rebound clearances;
- CV-joint angles and plunge;
- tire clearance;
- spring and damper motion ratios;
- turning circle.

Therefore the correct Alibaba strategy is:

**DESIGN hard points and interface geometry -> BUY common bearing/joint/damper families -> BUY or ADAPT proven arms where geometry fits -> BUY-FABRICATED-TO-DRAWING custom arms/knuckles/subframes where necessary.**

---

## 2. Front suspension architecture — MacPherson strut is the first architecture to package

Do not freeze the final geometry yet, but Prototype 1 should package a **conventional MacPherson-strut front suspension first**.

Why it deserves first position:

- compact transverse packaging around a front e-axle;
- few links and ball joints;
- huge global component ecosystem;
- ordinary service procedures;
- modest unsprung-part count;
- easy use of conventional coil-over-strut dampers;
- well understood by alignment shops and parts suppliers;
- compatible with bolt-on front cradle architecture;
- appropriate to a compact utility vehicle where simplicity matters more than maximum cornering sophistication.

This is not a final freeze.

A different geometry may win if packaging studies show that MacPherson towers damage:

- crash structure;
- underhood utility space;
- suspension travel;
- steering geometry;
- e-axle / halfshaft geometry;
- tire clearance.

A double-wishbone or multi-link front end remains an alternative if it produces a clear whole-vehicle benefit large enough to justify the extra joints and hard points.

### Avoid complexity by default

Do not start with:

- multi-link front suspension simply for marketing sophistication;
- electronically adjustable dampers;
- air springs;
- hydraulic cross-link systems;
- active camber/toe devices;
- giant aluminum castings combining several otherwise replaceable functions.

---

## 3. Rear suspension architecture — independent e-axle-compatible geometry remains open

The rear suspension has different constraints because the secondary e-axle must fit between the wheels while preserving:

- CV halfshaft articulation;
- cargo-floor height;
- battery protection;
- ground clearance;
- rear crash structure;
- useful suspension travel;
- service access to the e-axle.

The first packaging study should compare two simple families:

### A. Compact multi-link / trailing-link family

Potential advantages:

- good packaging around an electric drive unit;
- toe/camber behavior can be tuned independently;
- spring and damper can be separated if useful for cargo-floor packaging;
- many modern EV/compact-SUV donor references exist.

Potential disadvantages:

- more bushings and links;
- more alignment variables;
- more opportunities for proprietary link shapes.

### B. Double-wishbone / unequal-length-arm family

Potential advantages:

- clear geometry;
- straightforward camber control;
- robust rough-road potential;
- easy to reason about and document.

Potential disadvantages:

- more vertical/lateral packaging space;
- upper-arm hard points may intrude into cargo area;
- packaging around the e-axle can become less convenient.

### Current decision

**OPEN — compare both in CAD before freezing.**

The Alibaba market strongly supports either with commodity arms/joints and custom fabrication capability. Supplier abundance therefore does not need to decide the geometry.

---

## 4. Control arms — GREEN manufacturing ecosystem

Alibaba has a large ecosystem of replacement and custom control-arm suppliers. The useful discovery is not that inexpensive arms exist; it is that multiple manufacturers can forge, stamp, weld and machine arms to automotive processes.

### Jinjiang Automotive Group — strong OEM supplier reference

Jinjiang states that it has more than 30 years in automotive suspension/steering and supplies OEM suspension/steering products to manufacturers including IVECO, Dongfeng, Mercedes, Yutong, Geely and others. Its product families include control arms, stabilizer links, tie rods, steering arms and chassis components, and it states use of TS/IATF automotive quality systems since 2006.

Source:

- https://www.jinjianggroup.cn/

**Verdict: STRONG YELLOW supplier/fabrication lead.**

Why useful:

- real automotive manufacturing background;
- broad suspension/steering portfolio;
- likely capable of working from controlled drawings rather than only reproducing aftermarket parts.

Open questions:

- prototype MOQ;
- custom geometry capability;
- material/process options;
- fatigue validation;
- PPAP/APQP support;
- willingness to support low-volume open development.

### Zhejiang MingTu — forged aluminum customization lead

MingTu states it is an IATF 16949 manufacturer of forged aluminum control arms and related steering/suspension parts. It advertises 6061-T6/7075-class material options, forging/CNC capability and development from samples or 3D drawings.

Sources:

- https://www.controlarmcn.com/
- https://www.controlarmcn.com/faqs

**Verdict: YELLOW / custom-control-arm fabrication lead.**

This is especially relevant if Prototype 1 eventually needs a custom arm after common donor geometries fail packaging.

### DLZ — broad manufacturing benchmark

DLZ publishes in-house capability for:

- forged aluminum control arms;
- forged steel arms;
- stamped/welded arms;
- plating;
- ball-joint body forging;
- material/product testing;
- IATF 16949 manufacturing.

Source:

- https://www.dlz.com.cn/manufacture/en.aspx

**Verdict: YELLOW / process benchmark and potential supplier.**

---

## 5. Control-arm material — do not equate aluminum with better

Both stamped/forged steel and forged/cast aluminum can be appropriate.

Selection criteria should include:

- mass;
- fatigue life;
- stone/salt corrosion;
- bend-versus-fracture behavior;
- cost;
- repair/replacement availability;
- bushing retention;
- ball-joint interface;
- local manufacturing/replacement potential.

Prototype 1 should not spend money and supplier complexity merely to advertise aluminum suspension.

A well-designed stamped or forged steel arm can be exactly the right VolksMule answer.

---

## 6. Ball joints — BUY a common serviceable family

Ball joints are solved hardware and should not be custom-designed unless packaging absolutely forces it.

Prefer:

- a common automotive taper and stud size;
- replaceable joint rather than arm replacement where practical;
- mechanical retention that can be inspected;
- multiple aftermarket manufacturers;
- boots available as service parts where practical;
- grease-for-life conventional automotive design unless harsh-service testing proves a grease fitting is beneficial.

The ball-joint family should be selected from verified load requirements, not by finding the cheapest Alibaba catalog item.

### Durable preference

If a common bolt-in or press-in joint can meet the load and geometry requirements, design the control arm/knuckle around that joint instead of inventing a proprietary spherical joint.

---

## 7. Bushings — GREEN commodity / tune after geometry is stable

Hetian Automotive is a useful Chinese chassis/NVH supplier reference. It states:

- IATF 16949 certification;
- a 160,000-square-meter automotive chassis/NVH manufacturing base;
- 100+ patents;
- approvals/audits by 30+ global Tier-1/automaker supply chains;
- production of suspension and vibration-damping components across global platform families.

Source:

- https://www.hetianauto.com/

**Verdict: STRONG YELLOW bushing/NVH supplier lead.**

Bushing rate is a tuning parameter, not merely a dimension.

Final bushing choices should consider:

- longitudinal compliance;
- lateral stiffness;
- toe compliance under braking/drive torque;
- impact isolation;
- temperature;
- salt/water exposure;
- lifetime;
- press-fit/service method.

Avoid solid/spherical joints everywhere merely because they make prototype geometry precise. Prototype 1 is a road utility vehicle, not a race car.

---

## 8. Wheel hubs / bearings — GREEN, and one of the best standardization opportunities

Wheel hub units are a mature commodity and should be one of the first suspension interfaces we deliberately standardize.

### Zhejiang Xingjie — strong hub-unit supplier lead

Xingjie states that it manufactures:

- Gen I wheel bearings;
- Gen II hub bearings;
- Gen III integrated hub units;
- ABS-sensor-equipped hub units;
- nearly 1,000 product types;
- approximately 1 million hub-unit sets annual capacity plus millions of forgings/finished parts;
- ISO 9001 and IATF 16949 certified production;
- CAD/FEA and validation capability.

Source:

- https://www.zjxingjie.com/

**Verdict: STRONG YELLOW supplier lead.**

### Haining Automann / ATM — EV application reference

ATM specializes in automotive hub-bearing assemblies and lists new-energy applications including BYD Han/Song Pro and other EV models. It describes Gen I/II/III integrated designs and historical TS/IATF automotive quality certification.

Source:

- https://www.atmgroup.com.cn/en/

**Verdict: YELLOW supplier/EV reference.**

### Trans Power — alternate / documentation benchmark

Trans Power publishes hub-unit and bearing manufacturing in China and Thailand, OEM/ODM support, drawing review/application verification, and IATF 16949 production. Current trade-show material specifically describes hub units integrating bearing, hub, ABS sensor and seals for passenger cars and EVs.

Sources:

- https://www.sk.tp-sh.com/wheel-hub-assembly/
- https://automechanika.messefrankfurt.com/frankfurt/en/exhibitor-search.detail.html/shanghai-trans-power-co-ltd/mf_1_0012163879_5317377_10000007202601.html

**Verdict: YELLOW alternate.**

---

## 9. Hub-unit strategy — prefer common Gen III integrated hubs

A Gen III-style bolt-on hub/bearing assembly is currently the preferred direction because it can package:

- bearing races;
- wheel flange;
- wheel studs/bolt interface;
- seal package;
- ABS encoder/sensor interface;

into a replaceable service unit.

Benefits:

- no field bearing press required for ordinary replacement;
- predictable bearing preload;
- huge existing parts ecosystem;
- easier roadside/independent-shop service;
- cleaner knuckle interface.

### Do not freeze bolt pattern yet

A common passenger-SUV pattern such as **5x114.3** is attractive because of wheel/hub availability, but the pattern must be selected together with:

- hub load rating;
- brake rotor interface;
- wheel offset;
- tire choices;
- donor/alternate sources.

Alibaba currently lists many 5x114.3 hub units, which confirms ecosystem abundance but does not itself justify a freeze.

Example market evidence:

- https://www.alibaba.com/search/page?SearchScene=imageTextSearch&productId=1600238612683

---

## 10. Hub load rating is more important than nominal vehicle fitment

The selected hub must be validated against actual corner loads including:

- static axle load;
- payload;
- braking;
- cornering;
- pothole/curb impact;
- rough-road vertical acceleration;
- wheel offset leverage;
- tire grip;
- towing/recovery loads if those create relevant wheel loads.

Do not accept "fits SUV" as engineering evidence.

RFQs need dynamic/radial/axial load data or the test basis used for the proposed hub family.

---

## 11. Steering knuckles / hub carriers — geometry owned by VolksMule

Alibaba has custom steering-knuckle machining/forging/casting suppliers, including listings advertising IATF 16949 and 5-axis custom aluminum machining.

Sources:

- https://www.alibaba.com/countrysearch/CN/knuckles-manufacturers.html
- https://www.alibaba.com/steering-knuckle-arm-suppliers.html

This manufacturing abundance is useful—but **the knuckle itself is one of the worst places to accept random catalog geometry**.

The knuckle establishes or strongly influences:

- hub center;
- strut or upper/lower ball-joint location;
- steering axis inclination;
- trail;
- steering-arm length/location;
- tie-rod pickup;
- brake caliper mount;
- CV spline/clearance;
- wheel offset clearance;
- ABS sensor location.

### Current strategy

1. Search for a common mass-market knuckle/hub/brake family that fits our geometry.
2. If one works with only minor adaptation, **DONOR/ADAPT** it.
3. If none works, **DESIGN the knuckle and BUY-FABRICATED-TO-DRAWING** from an automotive-qualified forging/casting/machining supplier.

### Manufacturing benchmark

Yih Feng publishes IATF 16949 OEM forged steering-knuckle capability for passenger vehicles, SUVs, EVs and commercial vehicles. It is a useful benchmark for the process quality we should demand even if the final supplier is Alibaba-accessible.

Source:

- https://www.yihfeng.com.tw/product/steering-knuckle/

---

## 12. Dampers / struts — GREEN mature hardware

Prototype 1 wants passive conventional dampers.

Alibaba has enormous shock/strut availability, including real automotive manufacturers rather than only trading companies.

### Hubei Dongfeng JC — strongest current Alibaba-accessible damper lead

Alibaba directly lists Hubei Dongfeng JC Auto Shock Absorber as a manufacturer of:

- suspension shock absorbers;
- tube dampers;
- cartridge dampers;
- complete strut assemblies.

Alibaba source:

- https://www.alibaba.com/china-car-absorber-suppliers.html

The China Chamber of Commerce for Import and Export of Machinery and Electronic Products describes Dongfeng JC as:

- a major Hubei automotive shock-absorber factory;
- more than 3 million units annual production;
- IATF/TS 16949 quality-system certified;
- an appointed supplier to Dongfeng Motor Group;
- experienced in North American/European and other export markets.

Sources:

- https://www.cccme.cn/catalogs/detail-1632.aspx
- https://www.cccme.cn/products/detail-8076722.aspx

**Verdict: STRONG YELLOW supplier lead.**

### Why this is promising

A passive damper supplier does not need to own VolksMule's suspension geometry. We can specify:

- stroke;
- extended/compressed length;
- mounting interfaces;
- piston/rod size;
- force-velocity target curves;
- gas pressure;
- temperature/fade targets;
- durability requirements.

That is exactly the kind of mature component we should buy.

---

## 13. Damper tuning belongs to the vehicle

Do not select a shock merely because its dimensions fit.

The final force-velocity curves must match:

- sprung/unsprung mass;
- spring rate;
- motion ratio;
- tire stiffness;
- target body-control frequency;
- rough-road impact performance;
- rebound travel;
- payload range.

Request dyno plots at multiple temperatures and velocities.

A supplier should be able to valve a conventional passive damper to our target curve without requiring an electronic controller.

---

## 14. Coil springs — GREEN, ideally made to our rate/length requirement

Springs are another excellent buy-to-spec category.

### Zhejiang Meili High Technology — OEM/Tier-1 benchmark

Meili states that it:

- has manufactured automotive springs since 1990;
- supplies global OEMs and Tier-1s;
- produces suspension-system springs and other automotive springs;
- participates in 20+ industry/national standards;
- holds 100+ patents;
- is IATF 16949 certified.

Source:

- https://www.china-springs.com/en/

**Verdict: STRONG supplier benchmark.**

### Zhejiang Zongheng Spring — custom spring lead

Zongheng states it specializes in automotive suspension and brake springs with IATF/TS16949-based manufacturing, heat treatment, shot blasting and test-lab capability.

Source:

- https://www.bestsprings.cn/

Alibaba also directly exposes many automotive coil-spring suppliers and custom spring manufacturing.

Sources:

- https://www.alibaba.com/auto-suspension-coil-springs-suppliers.html
- https://autopart.alibaba.com/product/coil-springs-for-sale

**Verdict: GREEN category.**

### Strategy

Specify the spring after vehicle mass and motion ratio are known:

- installed load;
- free length;
- spring rate;
- jounce/rebound travel;
- block height;
- end shape;
- wire/material/process;
- fatigue requirement;
- corrosion coating.

A standard off-the-shelf spring may win, but custom coil spring manufacture is sufficiently ordinary that we should not compromise vehicle ride height/rate merely to use a catalog spring.

---

## 15. Strut mounts / bump stops / dust boots — GREEN commodity

These are ordinary rubber-metal suspension components with broad Chinese manufacturing support.

Huami / Ningbo Chilong, for example, states IATF 16949 manufacturing for strut mounts, strut bearings, dust covers, bump stops and bushings across global passenger/light-truck platforms.

Source:

- https://www.nbclzc.com/

**Verdict: GREEN category.**

Prefer standard families whenever possible, especially for:

- top bearings;
- bump stops;
- dust boots;
- spring isolators.

Do not turn a consumable rubber piece into a single-source custom component without good reason.

---

## 16. Anti-roll bars — DESIGN rate/geometry, BUY fabrication

Anti-roll bars are intentionally not a base philosophical requirement. They should exist only if handling/ESC testing shows they improve the whole vehicle.

If required:

- bar diameter/material/rate follows roll stiffness targets;
- use replaceable commodity bushings and links;
- design mounts to permit bar-rate changes during development;
- avoid active anti-roll hardware.

Alibaba/spring suppliers can readily manufacture bars once geometry/rate is defined.

---

## 17. Front/rear subframes — DESIGN around chosen systems, fabricate conventionally

The roadmap already assigns the front/rear cradles to **ADAPT or DESIGN**.

This suspension research reinforces that choice.

The subframe must position:

- suspension pivots;
- steering rack;
- e-axle mounts;
- anti-roll bar if used;
- recovery/load paths as appropriate;
- crash attachments;
- service/removal paths.

Generic Alibaba subframes are useful for:

- manufacturing references;
- donor measurements;
- stamped/welded/cast process comparison.

They should not dictate Prototype 1 hard points.

### Fabrication approach

Prototype 1 should initially favor a **welded/formed steel bolt-on cradle** because it is:

- locally inspectable;
- repairable;
- easy to prototype/revise;
- compatible with ordinary fixture welding;
- not dependent on giant castings.

A later production design can optimize material/process after geometry is proven.

---

## 18. CV joint / hub spline coordination

Because Prototype 1 uses front and rear e-axles, driven-wheel hubs/knuckles must be coordinated with:

- outer CV spline;
- hub/bearing unit;
- axle nut/retention;
- CV plunge and articulation;
- steering angle at front;
- jounce/rebound travel;
- wheel offset.

Do not select the hub independently from the e-axle output/halfshaft strategy.

Where practical, use a **common mass-market outer CV spline/hub interface** and adapt the inboard shaft to the selected e-axle, rather than creating a proprietary wheel-end spline.

---

## 19. Wheel-speed sensing should follow the hub family

The brake/ESC screen requires reliable wheel-speed data.

Gen III hub families with integrated magnetic encoders are attractive because they simplify packaging.

Requirements:

- accessible replaceable sensor where practical;
- documented pole count/signal type;
- common connector;
- known air gap;
- signal usable by the chosen ABS/ESC supplier;
- no dependence on encrypted/proprietary wheel-bearing electronics.

The ABS/ESC supplier must approve the sensor/encoder combination before vehicle calibration.

---

## 20. Do not freeze wheel bolt pattern before hub + brake + tire convergence

A common pattern is strongly preferred, but exact choice should follow:

- hub bearing load capacity;
- available wheel sizes/offsets;
- brake clearance;
- tire ecosystem;
- spare-wheel interchangeability;
- donor availability.

Candidate common patterns should be compared quantitatively rather than chosen aesthetically.

---

## 21. Rough-road geometry requirements

VolksMule should be an actual utility vehicle, not a low-clearance crossover with rugged styling.

Suspension packaging must explicitly evaluate:

- static ground clearance;
- lower control-arm clearance;
- subframe clearance;
- e-axle clearance;
- battery protection;
- jounce travel before hard contact;
- rebound travel;
- CV angles at full droop/jounce;
- tire-to-body clearance at steering lock and full travel;
- approach/departure/breakover interactions;
- shock bottoming and bump-stop energy.

A suspension component that is cheap but forces vulnerable low hard points fails the whole-vehicle test.

---

## 22. Durability / fatigue evidence gate

Suspension hardware is safety-critical structural hardware.

For custom or alternate-source arms/knuckles/hubs, require more than material certificates.

Evidence should include as appropriate:

- static ultimate load tests;
- fatigue-cycle tests;
- ball-joint pull-out/push-out tests;
- bushing retention;
- impact tests;
- hub radial/axial fatigue;
- cornering fatigue;
- corrosion/salt exposure;
- weld process qualification;
- forging/casting NDT;
- dimensional CMM reports;
- material heat-treatment traceability.

IATF 16949 is useful evidence of manufacturing quality systems, but it is **not itself proof that our exact component geometry has adequate strength.**

The IATF itself maintains OEM customer-specific requirements for major manufacturers, reinforcing that automotive quality systems are only one part of actual customer/product validation.

Source:

- https://www.iatfglobaloversight.org/oem-requirements/customer-specific-requirements/

---

## 23. Candidate ranking

| Function | Candidate / family | Status | Why |
|---|---|---:|---|
| Front geometry | Conventional MacPherson first packaging study | **PREFERRED FIRST STUDY** | Simple, compact, huge ecosystem; not yet frozen |
| Rear geometry | Multi-link/trailing-link vs double wishbone | **OPEN** | Must converge with rear e-axle/cargo/battery packaging |
| Control arms | Jinjiang OEM suspension family | **STRONG YELLOW** | Long OEM history, broad chassis manufacturing |
| Custom forged arms | Zhejiang MingTu / DLZ | **YELLOW** | IATF/custom forging/machining capability |
| Bushings/NVH | Hetian | **STRONG YELLOW** | IATF, major chassis/NVH supplier evidence |
| Hub/bearing | Zhejiang Xingjie Gen III family | **STRONG YELLOW** | IATF, integrated ABS-sensor hubs, high production capacity |
| Hub/bearing alternate | ATM / Trans Power | **YELLOW** | EV applications and documented hub manufacturing ecosystem |
| Steering knuckle | Common donor geometry if it works | **ADAPT first** | Maximum parts-store replacement ecosystem |
| Custom steering knuckle | Automotive-qualified forging/casting to our drawing | **DESIGN + BUY FABRICATION** | Geometry is vehicle-specific; supply ecosystem exists |
| Passive strut/damper | Hubei Dongfeng JC | **STRONG YELLOW** | Alibaba-accessible real manufacturer, IATF, Dongfeng supplier |
| Coil spring | Meili / Zongheng / qualified custom spring maker | **GREEN** | Mature buy-to-rate/length commodity |
| Strut mounts/bump stops | common IATF rubber-metal family | **GREEN** | Commodity consumables |
| Front/rear subframes | welded steel cradle | **DESIGN** | Must own hard points, e-axle/rack/crash interfaces |
| Air/adaptive suspension | — | **RED for Prototype 1** | Complexity without required job |

---

## 24. New durable requirements produced by this screen

### SUSP-001 — Hard-point sovereignty

VolksMule owns suspension hard points and kinematic targets. Supplier catalog geometry is evidence and reference, not authority.

### SUSP-002 — Rack and suspension geometry converge together

Steering rack inner-joint position, knuckle steering arm and control-arm geometry must be designed together to control bump steer.

### SUSP-003 — Common wheel-end service family

Prefer a common bolt-on hub/bearing, ball-joint, brake and wheel interface with multiple replacement suppliers.

### SUSP-004 — Knuckle geometry is controlled

A custom steering knuckle may be bought from a qualified fabricator, but its critical geometry must remain under VolksMule drawing/configuration control.

### SUSP-005 — Passive suspension baseline

Prototype 1 uses conventional passive dampers and coil springs unless measured vehicle performance demonstrates a real need for greater complexity.

### SUSP-006 — Rough-road travel is functional

Suspension travel and hard-point clearance must support actual occasional rough-road use, not merely visual ride height.

### SUSP-007 — CV angles are a suspension constraint

Front and rear suspension travel/steering geometry must remain within validated CV-joint articulation/plunge limits for the selected e-axle/halfshaft system.

### SUSP-008 — Consumables remain ordinary

Bushings, ball joints, bearings, links, mounts, bump stops and similar wear items should use broadly replaceable families wherever practical.

### SUSP-009 — Quality-system certification is not part validation

IATF/ISO supplier certification does not replace component-specific structural, fatigue, dimensional and corrosion validation.

### SUSP-010 — Subframes remain replaceable structures

Front and rear suspension/e-axle cradles remain bolt-on modules and must not become giant irreplaceable structural castings.

---

## 25. First RFQ — hub/bearing supplier

Request from Zhejiang Xingjie, ATM and/or Trans Power:

1. recommended Gen III hub family for a compact BEV/SUV in the ~5,500-lb GVWR class;
2. driven front/rear hub options;
3. hub flange / bolt-pattern options;
4. outer CV spline options;
5. static radial/axial load ratings;
6. dynamic fatigue test basis;
7. cornering fatigue test basis;
8. ABS encoder type/pole count;
9. compatible wheel-speed sensor;
10. bearing/seal temperature range;
11. salt/corrosion validation;
12. CAD/2D drawings;
13. mounting pilot/bolt pattern;
14. brake rotor pilot/interface;
15. wheel stud/bolt specs;
16. mass;
17. IATF certificate and PPAP capability;
18. sample MOQ/pricing;
19. production MOQ;
20. alternate/replacement cross references.

---

## 26. First RFQ — control-arm / knuckle fabricator

Ask Jinjiang, MingTu/DLZ or comparable automotive fabricators whether they can support prototype parts from controlled CAD/drawings.

Request:

1. steel stamping/welded, forged steel, forged aluminum and cast-aluminum capabilities;
2. recommended process by projected load/volume;
3. prototype tooling options;
4. minimum prototype quantity;
5. CMM inspection capability;
6. forging/casting NDT;
7. material/heat-treatment traceability;
8. fatigue test capability;
9. ball-joint/bushing assembly capability;
10. PPAP/APQP capability;
11. CAD formats;
12. engineering change control;
13. prototype and low-volume lead times;
14. production tooling amortization;
15. whether tooling/drawings can remain under VolksMule control.

---

## 27. First RFQ — passive damper

Ask Hubei Dongfeng JC or comparable IATF damper suppliers for a conventional passive strut/shock development path.

Provide final geometry/mass targets later; initially request:

1. supported custom strut/shock development;
2. piston/rod diameter families;
3. stroke range;
4. mounting interface options;
5. twin-tube vs monotube recommendations for compact rough-road BEV;
6. force-velocity dyno capability;
7. custom valving capability;
8. temperature/fade data;
9. gas pressure options;
10. seal/rod corrosion testing;
11. side-load limits for strut use;
12. durability-cycle tests;
13. prototype MOQ;
14. CAD drawings;
15. service/replacement support.

---

## 28. First RFQ — coil spring

Request from a qualified automotive spring manufacturer:

1. custom spring from load/rate/free-length targets;
2. available wire/material grades;
3. shot peening/preset/scragging process;
4. heat treatment;
5. corrosion coating;
6. load tolerance;
7. rate tolerance;
8. fatigue-cycle test basis;
9. block-height testing;
10. prototype MOQ;
11. production traceability;
12. CAD/drawing control.

---

## 29. Suspension development / validation plan

Before road testing, the selected geometry and hardware should pass staged validation.

### Kinematic bench/CAD

Evaluate through full jounce/rebound and steering travel:

- camber;
- toe/bump steer;
- caster/trail where relevant;
- roll center;
- tire clearance;
- CV joint angle/plunge;
- spring/damper travel;
- anti-roll-bar travel if installed.

### Structural component validation

- control-arm proof/ultimate/fatigue;
- knuckle proof/fatigue;
- hub bearing fatigue;
- ball-joint retention;
- bushing retention;
- subframe proof/fatigue;
- damper side-load/stroke/end-stop;
- spring fatigue/block height.

### Corner rig

Build a front and rear suspension corner rig before full vehicle use to verify:

- full travel without binding;
- steering travel;
- CV articulation;
- brake hose and ABS harness routing;
- damper/spring clearances;
- bump-stop engagement;
- wheel/tire clearance;
- service removal sequence.

### Vehicle progression

Only after the corner/structure gates:

- low-speed ride/steer tests;
- alignment sensitivity;
- controlled braking;
- controlled low-friction handling;
- rough-road travel testing;
- payload testing;
- progressive speed increase.

---

## 30. What remains open

Do not freeze yet:

- exact front geometry despite MacPherson being first to package;
- rear geometry;
- track width;
- wheelbase interactions;
- hub bolt pattern;
- hub spline;
- hub part number;
- control-arm material/process;
- knuckle material/process;
- spring rates;
- damper curves;
- anti-roll bars;
- alignment targets;
- wheel/tire size;
- exact ride height/travel.

These must converge in packaging CAD with e-axles, brakes, steering, battery protection and body/crash structure.

---

## 31. Mission verdict

The Alibaba suspension market is **excellent for VolksMule once we refuse to buy somebody else's geometry by accident.**

The likely path is:

**VolksMule hard points + common Gen III hubs/ball joints/bushings + ordinary passive dampers and coil springs + proven or drawing-controlled arms/knuckles + welded bolt-on subframes.**

This is exactly the systems-orchestration model the project was built around.

We do not need to invent wheel bearings, springs or shock absorbers. We do need to decide where the wheels move, where the steering pivots, how the halfshafts articulate and how all of those solved components coexist.
