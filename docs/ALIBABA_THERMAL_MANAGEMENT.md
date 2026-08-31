# Alibaba thermal-management screen

This document continues the VolksMule Alibaba sourcing mission for Prototype 1. It treats thermal management as a system, not a pile of unrelated parts.

The existing architecture requires:

- a 400-V-class LFP traction battery with liquid cooling/heating;
- heat-pump HVAC for efficient cabin heating/cooling;
- positive windshield defrost/defog performance;
- resistive/PTC backup heat;
- replaceable pumps, valves, sensors and service ports;
- ordinary, understandable hose routing rather than a proprietary all-in-one thermal maze unless the whole-vehicle benefit is compelling.

The rule remains:

> **Source solved hardware, but keep the vehicle thermal architecture and control logic ours.**

---

## 1. Working thermal architecture

Prototype 1 should begin with a modular architecture that can be bench-tested as separate loops and later coupled where useful.

### Battery / power-electronics coolant loop

Primary responsibilities:

- battery cold plates;
- front and rear inverter/e-axle thermal loads as required by the selected units;
- OBC/DC-DC/PDU thermal loads where the chosen hardware is liquid-cooled;
- coolant pump(s);
- radiator / low-temperature heat exchanger;
- expansion/degas provision;
- service fill/drain/bleed points;
- temperature and pressure/flow sensing where useful;
- coolant heater path for cold battery conditioning;
- chiller interface to the refrigerant system when active cooling below ambient is required.

### Cabin refrigerant / heat-pump loop

Primary responsibilities:

- high-voltage electric compressor;
- cabin evaporator;
- cabin condenser / heater core path as selected by the final heat-pump architecture;
- front condenser / ambient heat exchanger;
- expansion device(s);
- refrigerant valves;
- chiller for battery-loop coupling;
- defrost/defog capability;
- PTC/resistive backup through coolant or direct-air heating.

### Architectural preference

Prefer a small number of understandable pumps and valves with documented electrical control, documented default/fail states, and ordinary hose fittings over an integrated thermal octopus whose internal routing and control cannot be serviced without one supplier.

A factory integrated module may still win if it provides:

- clear schematics and ports;
- documented control interfaces;
- field-replaceable pumps/valves/sensors;
- service parts;
- acceptable packaging and mass;
- no cloud dependency;
- no supplier-only calibration lock.

---

## 2. High-voltage electric compressor — GREEN / strong supplier family

### Aotecar E-series

Aotecar is the strongest current Chinese supplier lead found in this pass.

Manufacturer material identifies:

- 400-V and 800-V electric-compressor platforms;
- E26, E34, E40 and E45 electric-compressor families;
- integrated inverter electronics;
- CAN/LIN communication;
- heat-pump suitability;
- automotive OEM activity rather than only aftermarket/retrofit sales.

Aotecar also presents itself as a publicly listed automotive thermal-management company with multiple global manufacturing bases, IATF 16949 certification and OEM serial-production experience.

**Current verdict: STRONG YELLOW approaching GREEN.**

The component family is clearly the right kind of hardware. Exact compressor selection remains open until we obtain:

- exact HV operating range;
- compressor displacement/speed map;
- cooling/heating capacity versus ambient/refrigerant condition;
- electrical power map;
- CAN/LIN message documentation;
- oil/refrigerant compatibility;
- R1234yf and/or R290 support by exact model;
- inlet/outlet fitting geometry;
- mass and CAD;
- NVH data;
- diagnostic/fault behavior;
- prototype pricing and replacement availability.

Sources:

- https://www.aotecarac.com/products-category/electric-compressor/
- https://www.aotecarac.com/product/
- https://www.aotecar.com/

---

## 3. Integrated thermal modules — YELLOW / benchmark and possible supplier path

Aotecar also publishes an integrated new-energy-vehicle thermal-management module containing:

- refrigerant sub-module;
- coolant sub-module;
- up to 10 kW cooling capacity;
- up to 8 kW heating capacity;
- a 20 kW water-cooled condenser;
- a 10 kW chiller;
- three integrated pumps in the 60–150 W range;
- three-way and ten-way coolant valves;
- compatibility claims for R134a, R1234yf and R290.

This proves that Alibaba-accessible / Chinese automotive supply can provide complete vehicle thermal modules at roughly the performance scale Prototype 1 is likely to need.

**Do not select the integrated module merely because it exists.**

It becomes attractive only if Aotecar supplies:

- internal hydraulic and refrigerant schematics;
- valve truth tables / control maps;
- pump serviceability;
- connector pinouts;
- CAN/LIN documentation;
- default/failsafe routing;
- CAD;
- replacement subcomponents;
- service instructions.

Otherwise, use the module as a packaging/performance benchmark and buy the compressor/chiller/pumps/valves separately.

Source:

- https://www.aotecarac.com/products/page/13/

---

## 4. High-voltage coolant / PTC heater — GREEN family, exact part still open

Alibaba directly exposes NF high-voltage coolant-heater families suitable for EV battery and cabin heating.

Current listing evidence includes:

- 200–440 VDC compatibility on one family;
- selectable 3 kW / 5 kW / 7 kW power classes;
- liquid-coolant architecture;
- EV application;
- -40 C-class environmental claims on related NF products.

Alibaba also surfaces a 5 kW NF automotive coolant heater marketed for 200–400 V-class EV applications.

These products fit the VolksMule requirement for a boring backup heat source that can preserve battery warming and windshield/cabin safety even when the heat-pump system cannot deliver adequate heat.

**Current verdict: GREEN family / YELLOW exact part.**

Before selection require:

- exact operating voltage range;
- continuous/peak current;
- CAN/LIN/PWM command interface;
- watchdog/failsafe behavior;
- dry-run and no-flow protection;
- outlet temperature limiting;
- overtemperature redundancy;
- coolant compatibility;
- pressure drop versus flow;
- environmental and vibration qualification;
- isolation resistance requirements;
- CAD/connectors;
- prototype availability.

Alibaba source examples:

- https://www.alibaba.com/product-introduction/NF-ptc-battery-cabin-heater-high_1600941005918.html
- https://www.alibaba.com/product-introduction/Popular-Model-5KW-PTC-Heater-Automotive_1600927237767.html

### Benchmark

BorgWarner's current automotive high-voltage coolant-heater portfolio provides a useful engineering benchmark:

- 400-V and 800-V families;
- approximately 3–10 kW range;
- battery and cabin heating applications;
- self-protection for dry-run / low-flow misuse on current portfolio material;
- use in production EV/SUV/light-truck programs.

This confirms that a roughly 5–7 kW 400-V coolant heater is a normal automotive solution class, not an unusual VolksMule requirement.

Sources:

- https://www.borgwarner.com/technologies/thermal-management
- https://www.borgwarner.com/newsroom/press-releases/2024/02/08/borgwarner-secures-contract-extending-high-voltage-coolant-heater-business-with-global-oem

---

## 5. Battery cold plates — GREEN fabrication commodity

Alibaba currently exposes more than one thousand EV-battery cooling-plate listings and multiple manufacturing processes:

- friction-stir-welded aluminum;
- vacuum-brazed aluminum;
- aluminum plate with embedded copper tube;
- stamped / roll-bonded solutions;
- custom CNC and drawing-based fabrication.

This is exactly the sort of subsystem VolksMule should **DESIGN geometrically and BUY as fabrication**.

The plate should conform to our final cell/module arrangement, serviceability needs, crash protection and pack removal strategy. We should not adopt a cell/module layout merely because a convenient off-the-shelf plate exists.

Useful current Alibaba examples include:

### Guangzhou Chase Auto Parts

A current EV battery heat-exchanger plate listing publishes:

- 1148 x 792 mm nominal plate size;
- 6–8 L/min flow;
- 15.5–23.4 kPa pressure drop;
- CQC14/CQC18 connector options;
- MOQ 1 set.

The listing is useful because it exposes flow and pressure-drop numbers rather than only dimensions.

Source:

- https://www.alibaba.com/product-detail/EV-Battery-Heat-Exchanger-Aluminum-Alloy_1601338624699.html

### ZANtherm

A current custom cold-plate listing offers vacuum brazing and publishes working-pressure information, with EV traction batteries listed as an application.

Source:

- https://www.alibaba.com/product-detail/High-Quality-Custom-Vacuum-Brazed-Battery_1600378375300.html

### General Alibaba market

Alibaba's current EV battery cooling-plate category shows 1,146+ products and a large range of custom one-off through production-volume suppliers.

Source:

- https://www.alibaba.com/showroom/ev-battery-cooling-plate_2.html

**Current verdict: GREEN — design the plate, competitively source fabrication.**

### Cold-plate RFQ requirements

Require:

1. exact alloy and temper;
2. joining process;
3. coolant compatibility;
4. burst pressure;
5. proof pressure;
6. leak-rate specification;
7. pressure-drop curve versus flow;
8. thermal-resistance or heat-flux validation data;
9. flatness tolerance;
10. dimensional tolerance;
11. corrosion testing;
12. port/fitting standard;
13. traceability;
14. sample capability before production tooling;
15. destructive-test coupons or validation samples if practical.

---

## 6. Coolant pumps — GREEN commodity family

Hebei Shenhai is a useful Alibaba-accessible pump lead. One current BEV coolant-pump listing publishes:

- 12-V nominal operation;
- 9–16 V operating range;
- 30 / 50 / 80 W variants;
- PWM control;
- -40 to +100 C ambient range;
- coolant up to 90 C;
- IP68;
- claimed service life >=15,000 hours;
- new-energy-vehicle application.

Source:

- https://www.alibaba.com/product-detail/PWM-control-brushless-water-pump-12v_62092478431.html

**Current verdict: GREEN family.**

This fits VolksMule's existing 12-V low-voltage philosophy and is a better starting point than adding a 48-V coolant-pump subsystem without a proven need.

Before exact selection require:

- pump head versus flow curve;
- electrical consumption versus load;
- PWM command definition;
- tach/fault feedback if available;
- dry-run tolerance;
- coolant chemistry limits;
- lifetime test basis;
- connector family;
- mounting orientation limits;
- vibration qualification;
- replacement availability.

### Pump architecture preference

Do not make one single pump a total-vehicle single point of failure if loop topology can avoid it economically.

At minimum, the thermal architecture should make it practical to replace an individual pump without opening the refrigerant system or removing the traction battery.

---

## 7. Valves — YELLOW / commodity hardware, documentation gate

The integrated Aotecar module proves that ordinary three-way and higher-port coolant valves are standard pieces of modern EV thermal architecture.

For VolksMule we should strongly prefer:

- discrete replaceable valves;
- known normal/de-energized position;
- local electrical control;
- position feedback where useful;
- documented flow coefficient / pressure drop;
- ordinary hose/fitting interfaces;
- fail positions that do not silently overheat the battery.

Avoid a ten-way smart manifold unless its total package, documentation and serviceability clearly beat several simple valves.

**Current verdict: YELLOW.** The product category is obviously sourceable; exact supplier work remains to be done.

---

## 8. Chiller and refrigerant-to-coolant coupling — YELLOW

Aotecar's integrated module includes a 10 kW chiller, demonstrating a commercially available scale that is more than sufficient as a benchmark for a compact two-seat EV.

VolksMule needs the chiller only if pack heat rejection cannot be met by ambient coolant/radiator paths under charging and high-load conditions, or when active cooling below ambient is required.

The chiller should remain a replaceable heat exchanger, not a sealed proprietary thermal controller.

Require:

- refrigerant type;
- coolant type;
- heat-transfer map;
- pressure drop on both sides;
- pressure ratings;
- mass/CAD;
- fittings;
- corrosion compatibility;
- service procedures.

---

## 9. Refrigerant choice stays open

Aotecar's integrated-module material lists compatibility across R134a, R1234yf and R290 depending on system configuration.

Prototype 1 should **not freeze refrigerant yet** merely because a compressor listing mentions one.

The decision must consider:

- U.S. regulatory requirements at the time of build;
- component availability;
- heat-pump low-temperature performance;
- service ecosystem;
- flammability and crash implications;
- global warming potential;
- owner-service practicality.

The thermal packaging should avoid unnecessarily trapping us into one vendor-specific refrigerant circuit before this decision is made.

---

## 10. Defrost is a safety function, not comfort equipment

Heat-pump efficiency must never be allowed to compromise windshield clearing.

Prototype 1 should retain enough independent heat capability to perform safe windshield defrost/defog when:

- ambient temperature is very low;
- the heat pump is unavailable;
- refrigerant charge is lost;
- the battery is cold;
- the vehicle is charging/preconditioning;
- heat-pump control electronics fault.

A high-voltage coolant heater feeding a conventional cabin heater core is currently the preferred simple fallback because the same hardware can also support battery preheating.

---

## 11. Working architecture recommendation

At this stage, the strongest Prototype 1 thermal direction is:

### BUY

- high-voltage electric scroll compressor;
- HV coolant/PTC heater;
- 12-V electric coolant pumps;
- ordinary coolant valves;
- radiator / condenser cores;
- refrigerant chiller;
- temperature/pressure sensors;
- expansion tank/degas hardware;
- HVAC evaporator/blower/air doors;
- conventional hoses, service ports and fittings.

### DESIGN

- overall loop topology;
- battery cold-plate geometry and mounting;
- hose routing and service access;
- control logic;
- fail/degraded modes;
- thermal set points;
- physical protection;
- diagnostics integration.

### BUY-FABRICATED-TO-OUR-DRAWING

- battery cold plates;
- custom brackets;
- simple manifolds where necessary.

### CONDITIONAL

- Aotecar or similar integrated thermal module, but only if documentation/serviceability make it genuinely simpler than discrete components.

---

## 12. Candidate ranking

| Function | Candidate / family | Current status | Why |
|---|---|---:|---|
| HV electric compressor | Aotecar E-series | **STRONG YELLOW** | Real automotive supplier; 400/800 V; CAN/LIN; heat-pump oriented |
| Integrated thermal module | Aotecar NEV module | **YELLOW** | Excellent benchmark; may be useful if internal interfaces are documented |
| HV coolant heater | NF 200–440 V 3/5/7 kW family | **GREEN FAMILY** | Correct voltage/power class; Alibaba-accessible; exact qualification still required |
| Battery cold plates | Custom FSW/vacuum-brazed Alibaba suppliers | **GREEN** | Commodity fabrication; geometry should belong to VolksMule |
| Coolant pump | Hebei Shenhai 12-V PWM BEV family | **GREEN FAMILY** | Conventional 12 V, PWM, IP68, automotive-use listing |
| Coolant valves | Discrete 3-way / multi-way automotive valves | **YELLOW** | Easy category; supplier/control details still need screening |
| Chiller | Automotive plate / integrated chiller family | **YELLOW** | Correct concept established; exact performance data needed |
| Thermal octopus | Undocumented integrated manifold | **RED** | Too much hidden routing/control/service dependency |

---

## 13. New durable requirements produced by this screen

### THERM-001 — Thermal architecture sovereignty

VolksMule must own the thermal-system topology and supervisory logic. A supplier module may implement functions, but basic battery/cabin thermal operation must remain understandable without a supplier cloud or inaccessible calibration service.

### THERM-002 — Serviceable discrete hardware

Pumps, valves, heaters and sensors should be individually replaceable where packaging permits.

### THERM-003 — Defrost independent of heat-pump health

The vehicle must retain sufficient backup heat to provide safe windshield clearing when the heat-pump subsystem is degraded or unavailable.

### THERM-004 — Cold plate follows the battery

Battery cell/module layout and crash/service architecture determine cold-plate geometry. An available supplier plate must not dictate the battery architecture.

### THERM-005 — Freeze protection and local recovery

Thermal failures must produce diagnosable local fault states and safe degraded behavior. Basic recovery must not require internet access or supplier authorization.

### THERM-006 — Ordinary service access

Routine thermal service should not require traction-pack removal or opening the high-voltage battery enclosure unless the failed component is actually inside the pack.

---

## 14. Supplier RFQ — compressor

Request from Aotecar or comparable suppliers:

1. recommended 400-V heat-pump compressor models for a compact ~4,000-lb BEV;
2. complete operating-voltage/current limits;
3. cooling/heating performance maps;
4. compressor RPM limits and control method;
5. CAN/LIN documentation or integration guide;
6. fault codes and limp behavior;
7. R1234yf/R290 support by model;
8. oil type/charge requirements;
9. CAD and mounting drawing;
10. connector and refrigerant fitting specifications;
11. environmental/vibration validation;
12. IATF / PPAP capability and exact product traceability;
13. prototype MOQ and sample pricing;
14. replacement/service availability.

---

## 15. Supplier RFQ — coolant heater

Request:

1. exact model for 300–450 V battery systems;
2. 5–7 kW power recommendation;
3. CAN/LIN/PWM protocol;
4. current limits and insulation requirements;
5. dry/no-flow protections;
6. outlet-temperature control and independent overtemp cutoff;
7. coolant type and flow range;
8. pressure-drop curve;
9. IP rating;
10. vibration/environmental qualification;
11. CAD/connectors;
12. prototype MOQ and replacement availability.

---

## 16. Supplier RFQ — battery cold plate

Send our eventual drawing and require:

1. proposed joining/manufacturing process;
2. alloy/temper;
3. prototype tooling cost;
4. proof/burst pressure;
5. leak specification;
6. pressure-drop and thermal model;
7. flatness tolerance;
8. coolant compatibility;
9. corrosion testing;
10. port options;
11. sample lead time;
12. production repeatability and traceability.

---

## 17. What remains open

Do not freeze yet:

- exact compressor model;
- refrigerant;
- exact PTC/heater power;
- number of coolant loops;
- whether battery and power electronics share one loop under all conditions;
- number of coolant pumps;
- valve topology;
- radiator/condenser size;
- chiller capacity;
- exact cabin HVAC module;
- integrated versus discrete thermal module.

These become packaging decisions once the e-axles, pack energy/cell arrangement, OBC/DC-DC cooling loads and cabin envelope are further defined.

---

## 18. Mission verdict

Alibaba and its reachable Chinese automotive-supplier ecosystem are **strong for VolksMule thermal hardware**.

The strongest outcome is not a complete mystery HVAC box. It is the ability to source mature automotive building blocks while keeping the system understandable:

**Aotecar compressor + commodity pumps/valves + automotive coolant heater + custom cold plates + ordinary heat exchangers/chiller + VolksMule-owned topology/control.**

That is aligned with the project's architecture: proven components orchestrated into a repairable vehicle rather than gratuitous reinvention or supplier lock-in.
