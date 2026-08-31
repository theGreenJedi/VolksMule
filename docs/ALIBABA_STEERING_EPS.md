# Alibaba steering / EPS candidate screen

This document continues the VolksMule Alibaba sourcing mission for Prototype 1.

The existing steering architecture is deliberately conservative:

- rack-and-pinion road-wheel steering;
- collapsible steering column;
- electric power assist;
- a continuous mechanical steering path from steering wheel to road wheels;
- steering-angle sensing for ESC/AEB integration;
- local diagnosis and replacement without vendor cloud authorization;
- no steer-by-wire as Prototype 1's primary steering architecture.

The design question is therefore not whether VolksMule should have EPS. It is **which EPS architecture gives adequate assist, packaging, steering feel, local serviceability and supplier openness without weakening the mechanical steering path.**

---

## 1. EPS architecture families

Current automotive supplier literature confirms four useful conventional EPS families:

### C-EPS — column assist

The assist motor/reduction unit is mounted on the steering column, generally inside the cabin.

Advantages:

- keeps assist hardware away from wheel spray and road debris;
- can simplify underhood packaging;
- suitable for compact and medium vehicles;
- mechanically simple rack can remain a commodity steering gear;
- potentially easier to replace the assist unit without disturbing wheel alignment.

Disadvantages:

- column packaging and crash-collapse integration become more demanding;
- assist torque must pass through more of the column/intermediate shaft system;
- may offer less ultimate assist capability than rack-assist architectures for heavier front axle loads.

JTEKT describes column EPS as especially suitable for compact vehicles with limited engine-bay space and widely used in light/compact/medium cars.

Reference:

- https://www.jtekt.co.jp/e/products/automotive/steering/eps01.html

### P-EPS — pinion assist

The assist motor acts at the steering pinion.

Advantages:

- conventional rack-and-pinion relationship;
- motor/noise package outside the cabin;
- potentially strong fit for compact passenger vehicles;
- fewer cabin-column packaging compromises than C-EPS.

JTEKT describes pinion EPS as placing the assist unit on the pinion shaft and notes lower cabin noise than column assist.

Reference:

- https://www.jtekt.co.jp/products/automotive/steering/eps02.html

### DP-EPS — dual pinion

One pinion carries the driver's mechanical input and a second pinion provides assist.

Advantages:

- separates the assist mechanism from the steering-wheel shaft;
- greater packaging freedom;
- potentially higher assist output;
- preserves a straightforward mechanical steering path.

JTEKT specifically identifies installation freedom and higher output as benefits.

Reference:

- https://www.jtekt.co.jp/e/products/automotive/steering/eps03.html

### R-EPS / rack assist

The electric motor assists the rack directly, generally through a belt/ball-screw or related mechanism.

Advantages:

- high assist capability;
- high rigidity;
- strong steering feel potential;
- good fit for larger/heavier front axle loads.

Disadvantages:

- larger/more integrated steering gear;
- underbody exposure;
- more expensive entire assembly to replace;
- greater risk that one supplier-specific rack geometry dictates suspension/subframe packaging.

JTEKT's rack-direct and rack-parallel systems are useful benchmarks for these architectures.

References:

- https://www.jtekt.co.jp/e/products/automotive/steering/eps04.html
- https://www.jtekt.co.jp/products/automotive/steering/eps05.html

---

## 2. Current architecture recommendation

Do **not** freeze C-EPS versus P-EPS/DP-EPS/R-EPS yet.

For Prototype 1, the preferred investigation order is:

1. **P-EPS / DP-EPS** if a qualified supplier can meet load, packaging and documentation requirements;
2. **C-EPS** if its assist capacity is adequate and column/crash integration remains clean;
3. **R-EPS** if the final front axle load or steering-force requirement makes rack assist materially better.

Why this order:

- Prototype 1 is compact, roughly first-generation-CR-V scale rather than a heavy truck;
- we want a mechanically ordinary rack-and-pinion system;
- steering hardware should not unnecessarily dominate subframe packaging;
- the assist system should remain separately diagnosable and replaceable where possible.

R-EPS is not rejected. It simply should not win by default merely because it is the newest/highest-output architecture.

---

## 3. Zhuzhou Elite Electro Mechanical — STRONGEST CURRENT ROAD-INTENT LEAD

Zhuzhou Elite Electro Mechanical Co., Ltd. is the strongest Alibaba-accessible steering supplier found in this pass.

### Evidence from the manufacturer

The company's current material states that it:

- specializes in EPS R&D, production, sales and service;
- developed an early independently owned Chinese EPS system;
- operates an EPS research institute and Hunan automotive steering engineering center;
- offers C-EPS, P-EPS, DP-EPS and R-EPS platforms plus multiple generations of controllers;
- holds more than 150 patents/software copyrights;
- owns key EPS system/component IP;
- has six EPS assembly lines and controller/component production/testing lines;
- has annual EPS capacity around 1.8 million sets;
- has passed IATF 16949, ISO 14001 and ISO 45001;
- lists major automotive customers including Changan, Changan New Energy, Geely, Chery and others;
- has exported EPS products to the United States and other markets.

Manufacturer sources:

- https://www.nfelite.com/en/aboutInfo.aspx
- https://www.nfelite.com/cn/aboutInfo.aspx
- https://www.nfelite.com/en/ProductList.aspx?TypeId=10160

Alibaba currently lists Zhuzhou Elite products including:

- automobile P-EPS / pinion electric power steering;
- brushless C-EPS;
- customized C-EPS systems for sedan / EV / SUV / MPV applications;
- R-EPS among the supplier's principal product families.

Alibaba sources:

- https://www.alibaba.com/electric-power-steering-system-suppliers.html
- https://www.alibaba.com/a-c-steers-suppliers.html

### Current verdict

**STRONG YELLOW — first road-intent RFQ target.**

The supplier profile is strong enough to justify actual engineering engagement. The unknowns are now project-specific rather than credibility-level:

- exact rack/pinion/column dimensions;
- assist force/torque capability;
- supported front axle load;
- steering ratio and rack stroke options;
- torque and angle sensors;
- CAN protocol openness;
- calibration ownership;
- fail/degraded behavior;
- functional-safety evidence;
- prototype MOQ;
- whether a small open vehicle project can obtain integration documentation.

### Useful controller evidence

One published Elite controller (ECU03G) provides an example of the company's conventional vehicle interface approach:

- 9–16 V operation;
- up to 75 A output;
- -40 C to +85 C range;
- CAN / K-line communication;
- external torque-sensor input.

This exact controller is **not** a VolksMule selection. It is evidence that the supplier works in a conventional 12-V automotive EPS architecture aligned with our low-voltage plan.

Source:

- https://www.nfelite.com/cn/ProductInfo.aspx?Id=10244

---

## 4. Tianjin Deco — useful prototype/custom integration lead, road-intent evidence weaker

Tianjin Deco Automotive Parts Co., Ltd. is directly represented in Alibaba's electric-vehicle steering supplier listings and offers electric vehicle, rack and column steering products.

The company's own/partner material says it:

- has developed EPS since the early 2000s;
- has controller production and testing capability;
- supplies electric vehicle and off-road/utility EPS systems;
- can design mechanical integration from a customer's vehicle 3D drawing;
- can adjust assist behavior by ECU reprogramming;
- offers prototype quantities on some products.

Sources:

- https://www.alibaba.com/electric-vehicle-steering-suppliers.html
- https://decotj.goldsupplier.com/
- https://decotj.goldsupplier.com/664023-Electric-Vehicle-Power-Steering/
- https://www.machineryoffers.com/offer/13114-Brand-New-UTV-power-steering-kit-with-ECE-certificated-for-Polaris-Ranger-XP-900-2012.html

### Current verdict

**YELLOW — development/prototype supplier lead.**

Why below Elite:

- much of its public catalog centers on UTV/ATV/low-speed and utility-vehicle applications;
- current public evidence is weaker for modern passenger-car functional-safety/calibration processes;
- CE/ECE marketing is not sufficient evidence for a U.S. road-vehicle steering system.

Why retain it:

- willingness to customize from 3D vehicle data;
- willingness to recalibrate assist;
- likely low-volume accessibility;
- useful bench and closed-course development path if exact hardware meets our loads.

---

## 5. Shanghai OE Industrial / Brogen — high-force benchmark, likely oversized for Prototype 1

Shanghai OE Industrial (Brogen EV Solution) offers rack-assist electric steering for light commercial vehicles.

A current published R008 specification includes:

- rack-assist EPS;
- 12/24-V operation;
- ±80 mm rack stroke;
- approximately 16 kN assist force at 12 V and 18 kN at 24 V;
- reference front-axle load around 3,000 kg;
- IP67;
- torque/angle sensor architecture.

Source:

- https://brogenevsolution.com/author/brogenevsolution-com/page/11/

Alibaba also lists Shanghai OE Industrial as a supplier of 12/24-V universal electric racks for light-commercial vehicles and SUV/MPV applications.

Source:

- https://www.alibaba.com/universal-power-steering-suppliers.html

### Current verdict

**YELLOW / benchmark, probably oversized.**

This is valuable because it establishes that Chinese supplier ecosystems offer complete high-force R-EPS assemblies with published rack stroke and force numbers.

For a first-generation-CR-V-scale Prototype 1, a rack designed around a 3,000-kg front axle is likely unnecessary and could impose excess mass, current draw and packaging.

Retain as:

- upper-bound steering-force benchmark;
- fallback if Prototype 1 grows materially heavier;
- supplier evidence for custom R-EPS availability.

---

## 6. Replacement/remanufactured EPS racks — DONOR / REFERENCE only

Alibaba has large numbers of replacement and remanufactured EPS racks for production vehicles including Honda CR-V, Toyota RAV4, Ford, Subaru and modern Chinese EVs.

These products are useful for:

- packaging references;
- inexpensive bench teardown;
- learning rack geometry and connector families;
- potential donor development.

They are **not automatically good VolksMule production selections** because:

- rack stroke and steering ratio were designed for another suspension geometry;
- calibration may depend on OEM CAN messages;
- angle/torque sensor zeroing may require proprietary service procedures;
- immobilizer/security pairing may exist;
- firmware behavior may not be documented;
- replacement-unit quality can vary greatly.

Current examples/search surfaces:

- https://www.alibaba.com/premium/electric_steering_rack.html
- https://www.alibaba.com/power-steering-rack-suppliers.html

### Current verdict

**DONOR / REFERENCE.**

A donor EPS only becomes a serious candidate if we can fully document its mechanical geometry, command/fallback behavior, diagnostics and calibration process.

---

## 7. Mechanical steering path remains non-negotiable

EPS failure must remove or reduce assist, not remove the driver's physical steering connection.

Prototype 1 requires:

**steering wheel -> collapsible column -> intermediate shaft / joints -> pinion -> rack -> tie rods -> knuckles**

The electric assist system is layered onto that path.

No supplier proposal should be accepted if normal manual steering cannot remain mechanically possible after loss of EPS power, subject to reasonable steering effort and the final system's safety analysis.

---

## 8. Steering column and crash behavior

Alibaba sourcing cannot reduce the collapsible steering column to a commodity shaft-selection exercise.

The column must be developed together with:

- steering-wheel position;
- occupant package;
- frontal crash structure;
- airbag/restraint strategy;
- knee/leg injury constraints;
- column mounting bracket deformation;
- intermediate-shaft plunge/articulation;
- firewall/bulkhead movement.

If C-EPS is selected, the assist motor/reduction unit's mass and location become part of the column/crash problem.

Therefore:

- **EPS assist hardware may be BUY;**
- **column installation/crash integration remains DESIGN + VALIDATE.**

---

## 9. Rack geometry must follow suspension geometry

Do not choose a steering rack before we know:

- front track width;
- knuckle steering arms;
- lower control-arm geometry;
- strut/upper-link geometry;
- inner tie-rod pickup location;
- rack height/fore-aft location;
- wheel/tire package;
- required turning circle;
- suspension travel.

The wrong rack width or inner-joint location can create unacceptable bump steer even if the rack itself is excellent.

Therefore the Alibaba steering search should identify **configurable supplier families**, not freeze a rack part number before suspension packaging.

---

## 10. Steering ratio / rack travel remain requirements, not vendor defaults

Supplier RFQs must provide:

- rack total travel;
- mm rack travel per steering-wheel revolution;
- pinion ratio;
- maximum input angle;
- mechanical end-stop definition;
- allowable tie-rod loads;
- rack push/pull load capability;
- backlash/compliance limits.

VolksMule must choose steering response and turning circle as whole-vehicle behaviors.

---

## 11. Electrical/control interface requirements

The preferred EPS supplier must provide enough local interface control to support:

- vehicle speed input;
- ignition/wake state;
- assist level versus speed;
- torque sensor status;
- steering angle and/or motor position as required;
- motor current/temperature;
- diagnostic trouble codes;
- overtemperature/overcurrent limiting;
- undervoltage/overvoltage behavior;
- limp/degraded assist state;
- watchdog/reset behavior;
- calibration/zeroing process.

CAN/CAN-FD message documentation is strongly preferred.

A supplier-specific diagnostic application may be accepted as a development convenience, but ordinary replacement/zeroing must eventually be documentable and reproducible offline.

---

## 12. ESC/AEB integration boundary

EPS is not allowed to become the master of vehicle stability control.

Prototype 1 architecture should keep roles clear:

- EPS controls steering assist;
- steering-angle sensing reports driver/road-wheel intent/state;
- ABS/ESC controller controls brake intervention;
- VCU coordinates allowed vehicle-level functions;
- infotainment/cloud systems have no authority over basic steering operation.

If later driver-assistance functions require steering torque overlays, those should be added only through a documented and safety-reviewed interface. They are not needed merely to make Prototype 1 steer safely.

---

## 13. Manual-steering effort gate

A continuous mechanical path is necessary but not sufficient.

A failed EPS system that leaves steering technically connected but practically immovable at low speed is not acceptable.

Bench/vehicle validation must measure steering-wheel torque after assist loss at:

- parking/near-zero speed;
- low-speed maneuvering;
- moderate road speed;
- representative tire pressure and front axle load.

The steering geometry, caster, scrub radius, tire width and rack ratio all influence this failure-state effort.

---

## 14. 12-V power architecture

Current supplier evidence strongly supports keeping EPS inside the existing 12-V architecture for this vehicle size unless load calculations prove otherwise.

Elite publishes conventional 9–16-V EPS controller architecture, while Brogen offers high-force rack EPS at 12/24 V.

The Prototype 1 DC/DC and 12-V battery must therefore be sized for:

- peak EPS current;
- other simultaneous safety-critical loads;
- degraded operation if HV-to-12-V conversion fails;
- transient voltage behavior.

The ordinary 12-V battery remains useful because it can preserve steering assist briefly through some high-voltage faults depending on final EPS current demand and battery state.

---

## 15. Candidate ranking

| Candidate | Role | Current status | Reason |
|---|---|---:|---|
| **Zhuzhou Elite P/DP/R/C-EPS family** | Road-intent supplier | **STRONG YELLOW** | Real automotive EPS producer, IATF 16949, multi-platform product family, major OEM customers, Alibaba-accessible |
| **Tianjin Deco custom EPS** | Prototype / integration supplier | **YELLOW** | Low-volume customization and ECU tuning attractive; passenger-road safety evidence needs deeper qualification |
| **Shanghai OE / Brogen R008** | High-force R-EPS benchmark | **YELLOW** | Published force/stroke/load data; likely oversized for compact Prototype 1 |
| **OEM replacement EPS racks** | Donor / teardown / geometry reference | **DONOR** | Cheap/available but calibration and geometry tied to another vehicle |
| **Generic UTV EPS kits** | Bench mechanism only | **RED for road intent** | Wrong duty/safety evidence for a road-going compact SUV |
| **Steer-by-wire modules** | Not Prototype 1 | **RED** | Contradicts mechanical-path requirement |

---

## 16. New durable requirements produced by this screen

### STEER-001 — Continuous mechanical path

Loss of electrical steering assist must not sever the physical steering connection between driver and road wheels.

### STEER-002 — Failed-assist effort must remain controllable

Mechanical continuity alone is insufficient. Assist-loss steering effort must be measured and kept within a usable safety envelope.

### STEER-003 — Rack geometry follows suspension

Rack width, inner tie-rod locations, height and fore/aft position must be selected with the front suspension to control bump steer and turning geometry. A convenient supplier rack cannot dictate bad suspension geometry.

### STEER-004 — Local calibration and diagnostics

EPS replacement, sensor zeroing, calibration and fault diagnosis must ultimately be possible without supplier cloud authorization.

### STEER-005 — Assist map belongs to VolksMule

Vehicle-speed-dependent assist and steering feel must be controllable/documented at the vehicle integration level. Supplier default calibration is not automatically accepted.

### STEER-006 — Steering remains independent of infotainment

Loss of infotainment, navigation, cellular service or general-purpose compute must not impair basic steering or steering assist.

### STEER-007 — EPS electrical reserve

12-V system design must account for peak EPS demand and define steering-assist behavior during DC/DC or HV faults.

---

## 17. First RFQ — Zhuzhou Elite

Ask for recommended EPS architecture for a compact two-seat BEV/MPV/SUV with approximately:

- first-generation-CR-V-scale exterior;
- expected curb mass under ~4,200 lb, preferably under 4,000 lb;
- working GVWR near or below ~5,500 lb;
- independent front suspension;
- conventional mechanical rack-and-pinion steering;
- 12-V electrical system;
- no steer-by-wire requirement.

Request:

1. recommended C-EPS / P-EPS / DP-EPS / R-EPS platform and engineering reason;
2. supported front axle load range;
3. maximum rack force or assist torque;
4. rack stroke options;
5. steering ratios / rack travel per revolution;
6. mechanical dimensions and CAD;
7. tie-rod interface options;
8. column/intermediate-shaft interface if applicable;
9. 12-V current consumption: standby, typical and peak;
10. torque sensor architecture;
11. steering-angle signal availability;
12. CAN/CAN-FD/K-line diagnostics and integration documentation;
13. assist-map calibration process;
14. local diagnostic/zeroing procedure;
15. fault/degraded modes after sensor, CAN, motor or power loss;
16. thermal derating behavior;
17. ingress, salt, vibration and temperature qualification;
18. functional-safety development evidence applicable to the proposed exact platform;
19. prototype MOQ and engineering sample pricing;
20. production MOQ;
21. PPAP/APQP capability;
22. replacement/service-part support;
23. firmware lifecycle and change-notification process;
24. whether an open-project customer can retain the documentation required for long-term offline service.

---

## 18. Second RFQ — Tianjin Deco

Ask specifically whether they can provide a road-vehicle EPS solution rather than an ATV/UTV system.

Require:

- actual vehicle mass/front-axle load capability;
- rack/column architecture;
- test/qualification evidence;
- 3D/CAD customization process;
- ECU assist calibration access;
- CAN interface;
- diagnostics;
- sample quantity/pricing.

If their strongest offering remains low-speed/UTV grade, retain only for bench/prototype testing.

---

## 19. Bench validation plan

Before road use, candidate EPS hardware should be mounted to a steering test fixture capable of applying repeatable rack load.

Test at least:

1. key-on initialization;
2. torque sensor zero behavior;
3. assist curve versus input torque;
4. assist curve versus simulated vehicle speed;
5. rack force versus current;
6. full-travel end-stop behavior;
7. thermal derating under repeated steering cycles;
8. loss of CAN;
9. loss of vehicle-speed signal;
10. torque-sensor fault;
11. angle-sensor fault if present;
12. undervoltage;
13. overvoltage/transient behavior within validated limits;
14. controller reset while steering;
15. total 12-V power loss;
16. restart/recovery after faults;
17. manual steering torque with assist disabled;
18. diagnostic retrieval and clearing;
19. calibration/zeroing from a clean replacement controller.

No steering candidate graduates to moving-vehicle testing until predictable mechanical steering remains after the assist is disabled.

---

## 20. What remains open

Do not freeze yet:

- C-EPS versus P-EPS versus DP-EPS versus R-EPS;
- exact rack width;
- rack position;
- steering ratio;
- tie-rod length;
- turning circle;
- column geometry;
- universal-joint/intermediate-shaft geometry;
- exact assist map;
- exact supplier/part number.

Those must converge together with front suspension geometry, wheel/tire selection, front axle load and crash/occupant packaging.

---

## 21. Mission verdict

Alibaba is useful for VolksMule steering, but the win is **not** a cheap replacement rack.

The real discovery is that an Alibaba-accessible Chinese supplier ecosystem includes established automotive EPS manufacturers capable of C-EPS, P-EPS, DP-EPS and R-EPS development.

**Zhuzhou Elite is now the first-choice steering supplier to interrogate.**

Prototype 1 should keep the mechanical rack-and-pinion path, choose the least-complex EPS architecture that meets actual steering loads, and insist that assist calibration and diagnostics remain locally understandable.

That keeps the system modern where modernity has a job—efficient electric assist—without surrendering the basic act of turning the wheels to software, cloud services or one irreplaceable black box.
