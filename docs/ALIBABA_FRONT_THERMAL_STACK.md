# Alibaba front thermal stack screen

Research date: **2026-09-01**

This document screens the **front heat-exchanger package** for VolksMule Prototype 1 after the cabin-HVAC-box work.

It is not a frozen radiator, condenser, fan, or heat-pump design. The purpose is to choose the right architecture and identify credible manufacturing paths without letting an attractive catalog part become the vehicle architecture by accident.

> **The front thermal stack is a serviceable system of heat exchangers, airflow hardware and protection. It is not one mysterious black box.**

---

## 1. What the vehicle actually needs

Prototype 1 currently carries:

- a 400-V-class LFP pack;
- front-primary and on-demand-rear electric drive units;
- liquid-cooled battery / power-electronics / drive hardware;
- a high-voltage electric refrigerant compressor;
- heat-pump cabin HVAC as the efficiency direction;
- PTC / coolant backup heat;
- a separate or transparent refrigerant-to-coolant chiller;
- simple physical cabin controls;
- first-generation-CR-V-scale body packaging.

The front of the vehicle therefore needs to reject heat to ambient air from at least two media:

1. **coolant** from the drive / power-electronics / battery thermal system as the final loop architecture requires; and
2. **refrigerant** from the cabin / battery refrigeration system.

The exact heat loads, loop split, coolant temperatures, fan duty and frontal opening are not yet frozen.

That means the correct sourcing task is not “pick a radiator.” It is:

> **Find a credible, modular automotive front heat-exchanger family that can be sized after the vehicle thermal model exists.**

---

## 2. Critical heat-pump distinction

A conventional automotive A/C condenser is normally designed to reject refrigerant heat to ambient air.

A reversible automotive heat pump may require the front refrigerant heat exchanger to operate in the opposite thermodynamic role during heating — absorbing heat from ambient air as an outdoor evaporator.

Therefore:

> **Do not assume that a catalog condenser is automatically suitable as the outdoor heat exchanger for heat-pump heating.**

Before any exact refrigerant-side exchanger becomes a candidate, require:

- explicit suitability for the intended refrigerant;
- working-pressure and proof/burst data;
- flow-direction constraints;
- oil return / distribution expectations;
- heat-transfer map in the intended operating modes;
- confirmation of reverse-flow / heat-pump ambient-evaporator duty if that is how the final cycle uses it;
- frost / condensate behavior and drainage requirements where relevant;
- dimensional drawing and port geometry.

If a supplier can only document condenser duty, then treat the part as **cooling-only condenser hardware**, not as proof of a complete heat-pump architecture.

---

## 3. Architecture verdict — stacked and separately replaceable

The current preferred Prototype-1 arrangement is a **stacked front thermal module** containing separate service parts:

- refrigerant outdoor heat exchanger / condenser as the final heat-pump topology requires;
- one or more low-temperature coolant radiators as the final loop model requires;
- removable fan / shroud assembly;
- removable stone/debris protection;
- simple brackets and isolators;
- accessible hose / refrigerant connections;
- drain paths that do not dump onto HV connectors or trapped body cavities.

This arrangement wins because:

- either heat exchanger can be replaced without replacing the other;
- the fan remains an ordinary service component;
- a supplier change does not require redesigning an integrated proprietary module;
- different frontal cores can be tested during Prototype 1 development;
- airflow restriction and thermal interaction can be measured rather than hidden inside a vendor assembly;
- the body can preserve a common rectangular heat-exchanger interface even if the exact supplier changes.

### Reject for now

Do not freeze:

- a brazed radiator/condenser combination that cannot be separated;
- a proprietary electronic fan/controller that requires a vendor cloud or vehicle authorization;
- decorative grille geometry that starves the heat exchangers;
- a thin condenser or radiator chosen only because its face dimensions happen to fit;
- one supplier's mounting tabs as permanent body hard points before the thermal model exists.

---

## 4. HBS — strongest Alibaba-accessible heat-exchanger manufacturing path

**Guangzhou Huadu Bisheng Automotive Air Conditioner Factory (HBS)** is the strongest current Alibaba-accessible manufacturer found for this row.

Current evidence:

- established in 1993;
- dedicated automotive heat-exchanger manufacturer;
- product families include parallel-flow and serpentine condensers, evaporators and radiators;
- current catalog also explicitly exposes a **Power cell radiator** category;
- IATF 16949:2016 claimed on the company site;
- roughly 24,000 m² facility / 30,000 m² construction area;
- roughly 2 million heat-exchanger pieces annual capacity;
- direct Alibaba supplier presence for condenser / radiator / evaporator products;
- North-American sales exposure in current Alibaba supplier results.

Primary references:

- https://en.gz-hbs.com/
- https://www.hbscoolingparts.com/about-us
- https://www.alibaba.com/ge-condenser-suppliers.html

### What HBS is good for

HBS is a credible candidate to manufacture:

- a coolant radiator to project dimensions;
- a parallel-flow refrigerant exchanger to project dimensions;
- prototype / validation cores if MOQ and engineering support are workable;
- later stable-CAD production heat exchangers.

### What HBS does not yet prove

The public catalog is dominated by application-specific replacement cores.

It does **not** yet prove that a particular current HBS catalog condenser:

- supports R1234yf;
- supports reversible heat-pump duty;
- meets the exact pressure / thermal map VolksMule will need;
- is optimized for the pressure drop created by the final stacked package;
- should dictate Prototype-1 mounting geometry.

So HBS earns:

> **CARRY — manufacturer / custom-heat-exchanger path; exact cores remain OPEN.**

---

## 5. HBS physical benchmark — useful scale, not a selected part

A current HBS condenser reference surfaced as model **HBS-L509** with a published size of approximately:

- **650 × 327 × 22 mm**.

Reference:

- https://global.apsoto.com/inquiry/pro_com_detail.aspx?op=25489

The same reference describes:

- parallel-flow / micro-tube condenser capability;
- 100% leak testing;
- an automotive heat-exchanger manufacturing operation.

This is useful only as a **physical class benchmark**.

It demonstrates that a roughly 650-mm-wide, low-profile automotive refrigerant core is an ordinary industrial object and physically plausible in the vehicle class being studied.

It does **not** become the VolksMule condenser simply because its dimensions are convenient.

---

## 6. Hubei Meibiao — stronger road-intent engineering benchmark

**Hubei Meibiao Automobile Refrigeration System Co., Ltd.** remains the more credible engineering-level thermal-management benchmark.

Current public evidence includes:

- professional automotive A/C and thermal-management focus;
- controlled by listed automotive thermal supplier Zhejiang Yinlun Machinery;
- IATF 16949:2016 quality-system certification claim;
- CNAS-accredited laboratory claim;
- dedicated automotive A/C research institute;
- 36 automotive A/C R&D engineers;
- condenser / evaporator product families;
- heater and refrigerant-pipeline product families;
- OEM / Tier-1 relationships described by the company;
- active intellectual-property work on integrated vehicle thermal-management systems.

References:

- https://www.mbac.com.cn/en/
- https://www.mbac.com.cn/en/content_pic.asp?FID=1&TID=35
- https://patents.google.com/patent/CN115610187B/zh

The granted Meibiao thermal-management patent is especially useful as evidence that the company is not merely making replacement A/C cores; it describes coordinated battery / motor coolant radiators, pumps, valves, battery cooler and refrigeration functions.

### VolksMule use

Meibiao is currently better treated as:

> **CARRY — road-intent thermal-system / custom heat-exchanger engineering benchmark.**

It does not need to become the only supplier. In fact, VolksMule should deliberately retain a drawing-defined interface that HBS, Meibiao, another qualified supplier, or a local radiator specialist could reproduce.

---

## 7. Cooling fans — commodity hardware, but provenance still matters

Alibaba has a very deep market for 12-V brushless axial radiator / condenser fans, including SPAL-branded and SPAL-compatible products.

Current examples include:

- SPAL VA89-class 12-inch brushless fan listings;
- 12-V / 24-V brushless condenser fans;
- a current 12-inch / 12-V brushless listing around **3000 m³/h**;
- larger 500-W-class SPAL brushless fan listings.

References:

- https://www.alibaba.com/countrysearch/CN/spal.html
- https://www.alibaba.com/product-introduction/12-Inch-VA89-ABL320P-N-94A_1601320425442.html

These listings prove the category is easy to source. They do **not** prove authenticity or final road suitability.

### Current fan rule

Carry a **standard automotive brushless fan / shroud interface** and size the exact fan only after:

- stacked-core pressure drop;
- low-speed thermal rejection;
- A/C pull-down requirement;
- heat-pump frost / low-ambient behavior;
- 12-V load budget;
- noise target;
- fan-failure degraded mode

are modeled.

For road-intent hardware, an authentic SPAL / Tier-1 fan from a traceable channel may beat a cheaper marketplace clone even if Alibaba remains useful for samples and price discovery.

The fan controller must permit ordinary local diagnosis and replacement. PWM / simple documented control is preferable to proprietary network ownership.

---

## 8. Prototype-1 physical interface rules

Do not freeze exact front-core dimensions yet.

Instead the body / front carrier should preserve:

- a broad rectangular exchanger aperture rather than styling-driven tiny openings;
- removable upper / lower attachment structure;
- enough depth for at least two thin stacked heat exchangers plus fan / shroud / guard;
- fan removal without removing the battery pack or drive unit;
- exchanger removal without cutting welded body structure;
- hose-port access from above / below / front service zones;
- room for sealing foam / side baffles so fan air actually passes through the cores;
- stone guard clearance that does not rest directly on delicate fins;
- drain / washout path for mud, insects, road salt and leaves;
- sacrificial front protection that can be replaced separately from the heat exchangers.

The HBS-L509 650 × 327 × 22-mm condenser is a useful face-size example, but no body hard point should be derived from it until the whole front package is modeled.

---

## 9. Airflow order remains an engineering variable

A simple front-to-rear stack may look like:

> debris guard → refrigerant exchanger → coolant radiator → fan/shroud

but that order is **not frozen**.

The front exchanger heats the air entering the rear exchanger. The rear exchanger raises pressure drop seen by the fan. Heat-pump operation can further change the desirable arrangement.

Therefore the final stack order must be tested as a coupled system.

Measure:

- air-side pressure drop of each core;
- air temperature rise across the first core;
- radiator heat rejection with the refrigerant exchanger active/inactive;
- refrigerant performance with the coolant loop heavily loaded;
- fan power versus airflow;
- stone-guard / grille pressure penalty;
- low-speed and stopped-vehicle performance;
- reverse airflow / recirculation around the front carrier.

Do not size the two cores independently and assume stacking them preserves their catalog ratings.

---

## 10. What the exact coolant radiator must eventually prove

Before selection, require:

- coolant type compatibility;
- operating and burst pressure;
- core material and corrosion specification;
- heat rejection map versus coolant flow, inlet temperature and air flow;
- coolant pressure drop map;
- thermal-cycle / vibration / salt-spray evidence;
- dimensional CAD;
- port size / geometry;
- drain / bleed strategy;
- stone-impact considerations;
- repair / replacement availability;
- supplier ability to reproduce the same core from a project drawing.

Avoid sizing an EV low-temperature radiator using engine-cooling assumptions alone. A physically similar engine radiator may be useful, but the expected coolant temperatures and heat loads can be very different.

---

## 11. What the exact refrigerant outdoor exchanger must eventually prove

Require:

- refrigerant compatibility — R1234yf remains the current automotive direction unless the final compressor / system dictates otherwise;
- intended refrigerant role(s);
- heat-pump reverse-duty confirmation if required;
- rated working pressure and proof/burst pressure;
- heat-transfer map in cooling and heating modes where relevant;
- air-side pressure drop;
- refrigerant-side pressure drop;
- port / fitting standard;
- leak-test method and allowable leak rate;
- corrosion / vibration / thermal-cycle evidence;
- CAD and mounting interface;
- replacement / production horizon.

A seller statement such as “universal condenser” is not engineering evidence.

---

## 12. Supplier questions — hold for later outreach

Supplier outreach remains intentionally deferred.

When the broader requirement package is ready, HBS / Meibiao-class suppliers should be asked for:

1. custom radiator and refrigerant-outdoor-heat-exchanger capability;
2. IATF site certificate and applicable test capability;
3. thermal-performance test reports / maps for candidate cores;
4. pressure-drop maps;
5. R1234yf suitability;
6. reversible heat-pump outdoor-exchanger capability;
7. working / proof / burst pressure;
8. corrosion / vibration / thermal-cycle standards;
9. 2D / 3D CAD;
10. port / fitting options;
11. prototype MOQ and engineering/NRE cost;
12. replacement-core availability;
13. whether a project-owned drawing can be produced by alternate suppliers without a proprietary control interface.

No inquiry needs to be sent during this sourcing pass.

---

## 13. Current sourcing verdict

### Coolant radiator

**CARRY supplier category / exact core OPEN**

Preferred path:

1. HBS / Meibiao-class qualified custom automotive heat exchanger once the thermal model and front package exist;
2. mass-market donor/local radiator if a common core happens to fit the thermal and service requirements better.

### Refrigerant outdoor exchanger / condenser

**CARRY supplier category / exact core OPEN**

Preferred path:

1. qualified automotive parallel-flow heat exchanger from HBS / Meibiao-class manufacturer;
2. require heat-pump ambient-evaporator capability if the final cycle needs it;
3. do not let a cooling-only condenser silently define the HVAC architecture.

### Fan / shroud

**CARRY commodity architecture / exact fan OPEN**

Prefer traceable automotive brushless hardware with documented control and local serviceability.

### Front thermal stack

**CARRY MODULAR ARCHITECTURE**

The vehicle owns:

- stack geometry;
- common mounting interface;
- airflow seals / baffles;
- fan control requirement;
- stone protection;
- thermal validation.

Suppliers own the manufacture of proven heat exchangers and fans.

---

## 14. What still blocks exact selection

The remaining blockers are legitimate engineering dependencies, not sourcing failures:

- front-body / crash / service package;
- actual continuous and peak e-axle/inverter heat rejection;
- pack thermal load;
- final coolant-loop topology and target temperatures;
- refrigerant cycle topology;
- final refrigerant;
- cabin cooling / heating / defrost load;
- stacked-core airflow model;
- fan power / 12-V budget;
- low-temperature heat-pump and frost strategy.

Until those exist, selecting an exact radiator or condenser would be false precision.

---

# Bottom line

The front thermal stack is not an unsolved supplier problem.

VolksMule now has two credible Chinese automotive paths:

- **HBS** for an Alibaba-accessible automotive radiator / condenser / power-cell-radiator manufacturing family;
- **Hubei Meibiao** for a stronger road-intent custom thermal-management engineering benchmark.

The right Prototype-1 architecture is a **modular stacked front heat-exchanger package with project-owned interfaces**, not an inseparable thermal brick.

The exact cores remain intentionally OPEN until thermal loads and front geometry are real.
