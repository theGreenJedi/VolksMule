# Alibaba cabin HVAC air-handler sourcing screen

Research current as of **2026-09-01**.

This document closes the remaining obvious cabin-side gap in the Prototype-1 thermal architecture.

Previous work already established:

- high-voltage electric compressor / heat-pump hardware;
- battery/power-electronics coolant loops;
- chiller / coolant-heater / pumps / valves / front heat-exchanger paths;
- physical HVAC knobs and tactile controls as the project preference;
- positive windshield defrost/defog as a safety requirement;
- rejection of oversized luxury multi-zone HVAC modules for a compact two-seat utility vehicle.

The remaining cabin-side job is intentionally simple:

> **Move enough conditioned air through a compact one-zone box to heat/cool two occupants and clear the windshield reliably.**

---

## 1. Prototype-1 target architecture

Carry one common cabin air stream with:

- fresh-air / recirculation inlet;
- replaceable cabin filter;
- 12-V blower;
- evaporator core;
- heating core / indoor condenser path appropriate to the final heat-pump topology;
- condensate drain;
- simple blend/bypass function if required;
- simple mode doors for windshield / face / floor distribution;
- strong dedicated windshield-defrost outlets;
- ordinary ducts;
- physical fan-speed and temperature/mode controls.

### Explicitly not required

- left/right dual zone;
- rear zone;
- fragrance cartridges;
- ionizer as a vehicle dependency;
- camera-based occupant climate sensing;
- cloud-connected climate control;
- a giant tablet as the only HVAC interface;
- dozens of smart flap motors merely because a supplier offers them.

A screen/app may display temperature or allow optional convenience control, but the driver must be able to heat, cool and defrost the vehicle without infotainment.

---

## 2. Two sourcing tiers

### Tier A — prototype / airflow bench hardware

Alibaba has inexpensive universal under-dash evaporator/heater assemblies with low MOQs.

These are useful for:

- checking dashboard volume;
- blower current and noise experiments;
- duct routing experiments;
- evaporator condensate handling;
- physical knob/cable/control experiments;
- proving how much air the small cabin actually needs.

They are **not automatically road-intent defrost systems**.

### Tier B — road-intent integrated HVAC box

Final road-intent cabin air handling should come from:

- a genuine automotive HVAC supplier with design/validation capability; or
- a mature high-volume donor HVAC box that can be integrated cleanly with the Mule's refrigerant/heating architecture.

The box should be customized only as much as necessary. A bespoke air box with proprietary actuators/controls is not automatically superior to a common donor assembly.

---

# 3. Alibaba prototype candidates

## GOUKU universal 12-V under-dash evaporator family

Current Alibaba listings expose GOUKU under-dash evaporator assemblies with:

- 12-V blower/electrical architecture;
- compact under-dash packaging;
- low prototype MOQ around 2 pieces on current listings;
- published cooling figures in roughly the 2.5–3.5-kW class depending listing/variant;
- adjustable/customized mounting/hose arrangements claimed by marketplace material.

Examples:

- https://www.alibaba.com/product-introduction/GOUKU-Universal-Under-Dash-Evaporator-Assembly_1600201909895.html
- https://www.alibaba.com/product-introduction/12V-Universal-Under-Dash-Assembly-AC_1600248083262.html

One current listing advertises a 12-V under-dash evaporator at roughly **3300 kcal/h** cooling capacity, equivalent to approximately 3.8 kW if the published figure is valid.

### Verdict

> **YELLOW prototype / DONOR airflow-box candidate; not a final road-intent defrost selection without original engineering data.**

Useful because it is cheap enough to learn from physically.

Not enough public evidence for:

- automotive defrost performance;
- exact airflow versus static pressure;
- blower current map;
- evaporator pressure drop;
- R1234yf compatibility on the exact part;
- crash/flame/material qualification;
- condensate behavior at vehicle attitudes;
- duct outlet pressure balance;
- long-term actuator/flap durability.

---

## Generic heating/cooling universal under-dash kits

Alibaba also has complete 12/24-V universal heating/cooling under-dash assemblies at low MOQ, including current listings around USD 200–300 per unit.

Example:

- https://www.alibaba.com/product-introduction/Universal-Under-Dash-Kit-Heating-and_1600541588320.html

### Verdict

> **YELLOW bench/packaging reference only.**

These can be valuable to establish a physical envelope and test the premise that a simple one-zone air box is sufficient.

Marketplace claims such as CE, cooling capacity or 'universal EV' do not substitute for vehicle-level airflow/defrost validation.

---

# 4. Road-intent supplier lead — Yinlun

Yinlun currently publishes automotive HVAC assemblies for:

- new-energy electric vehicles;
- hybrids;
- conventional automobiles;
- heat-pump and conventional A/C systems.

Its current product material explicitly describes:

- offset HVAC arrangements;
- middle HVAC arrangements;
- front-cabin HVAC arrangements;
- modular/standardized parts;
- evaporator integration;
- lightweight / NVH-oriented design.

Source:

- https://newsite.yinlun.cn/page146?_l=en

### Why it fits

Yinlun is strong enough to understand the whole thermal system but publishes modular HVAC architecture rather than only one monolithic luxury box.

That creates the possibility of requesting a deliberately stripped one-zone module around VolksMule requirements.

### Verdict

> **STRONG GREEN engineering benchmark / YELLOW-GREEN direct road-intent supplier path.**

Final selection still needs exact CAD, airflow and thermal data.

---

# 5. Road-intent supplier lead — Hubei Meibiao

Hubei Meibiao Automobile Refrigeration System is a serious automotive A/C and thermal supplier.

Current manufacturer material states:

- IATF 16949 quality-system certification;
- CNAS-accredited laboratory;
- dedicated automotive-air-conditioning research capability;
- dozens of automotive A/C design engineers;
- relationship/supply activity with FAW and Valeo and other vehicle manufacturers.

Sources:

- https://www.mbac.com.cn/
- https://www.mbac.com.cn/view_message.asp?FID=2&TID=174

### Verdict

> **STRONG GREEN supplier class for a road-intent simple HVAC box.**

This is the sort of supplier that can answer real questions about:

- blower curves;
- core pressure drop;
- outlet distribution;
- evaporator icing;
- condensate management;
- defrost performance;
- NVH;
- thermal capacity;
- material/environmental qualification.

---

# 6. Other useful supplier/architecture references

## MIND thermal systems

MIND currently presents whole-vehicle thermal-system development and customized HVAC/thermal solutions and reports current global OEM supplier activity.

Source:

- https://www.mind-group.com/en

**Verdict: GREEN benchmark / possible direct supplier, likely more system-level than Prototype-1 needs.**

## Xiezhong International

Xiezhong's automotive thermal business has long-standing relationships with multiple Chinese and international OEMs and has developed thermal systems for new-energy vehicles.

Source:

- https://www.njxiezhong.com/

**Verdict: GREEN supplier class / useful one-box HVAC development reference.**

The final Mule should not require one of these Tier-1 suppliers specifically; they establish the evidence quality expected of the road-intent air box.

---

# 7. Blower motor — keep it ordinary

Alibaba has a deep market of 12-V automotive blower motors and evaporator blower assemblies, including suppliers serving North American applications.

Example category/supplier page:

- https://www.alibaba.com/evaporator-blower-suppliers.html

### Preferred architecture

- conventional 12-V centrifugal blower;
- replaceable motor/module;
- serviceable from cabin or cowl side without removing the entire dashboard if practical;
- several discrete speeds or a simple locally controlled PWM module;
- no body-domain/cloud dependency.

### Control preference

For Prototype 1, either is acceptable:

1. conventional resistor / switched speeds; or
2. simple PWM blower controller driven by a physical knob.

PWM is not rejected merely because it is electronic. It earns its place if it improves efficiency, noise and speed control while retaining local control and replaceability.

---

# 8. Physical controls and flap actuation

## Fan

Physical rotary knob.

## Temperature

Physical rotary knob.

Depending final heat-pump topology, the knob may command:

- coolant/heater valve position;
- air-blend door;
- compressor/heat-pump temperature target;
- a simple combination of these through a local HVAC controller.

The important rule is that the driver has a tactile control independent of infotainment.

## Mode

Physical rotary knob or short lever for:

- windshield;
- windshield/floor;
- floor;
- face/floor;
- face.

The exact number of positions can be reduced if airflow testing proves fewer are sufficient.

## Recirculation

Physical button/lever.

### Actuators

Simple cable-operated doors are attractive where routing permits.

Simple 12-V geared flap actuators are also acceptable if:

- position/control is documented;
- default failure does not eliminate defrost;
- actuator is individually replaceable;
- no proprietary network pairing is required.

---

# 9. Defrost is the dominant design case

The cabin air box must be designed around windshield clearing, not merely occupant comfort.

The selected system must provide:

- high airflow to the windshield;
- warm air rapidly in cold weather;
- dehumidification when required;
- useful side-window clearing;
- airflow distribution that covers the selected windshield geometry;
- positive operation without infotainment boot.

### Failure philosophy

If a mode actuator fails, the preferred safe default is **windshield/defrost-biased**, not face vents only.

A local PTC/coolant-heater backup path exists specifically so windshield heat does not disappear merely because heat-pump performance is poor in severe cold.

---

# 10. Airflow / engineering data required

Before final HVAC-box selection, obtain or measure:

- total airflow versus blower speed;
- airflow versus static pressure;
- blower input current/power;
- blower acoustic data;
- evaporator air-side pressure drop;
- heater/indoor-condenser pressure drop;
- filter pressure drop clean/loaded;
- cooling capacity versus inlet conditions;
- heating capacity versus inlet conditions;
- condensate drain capacity/orientation;
- evaporator freeze/icing behavior;
- core dimensions;
- refrigerant/coolant fittings;
- exact refrigerant compatibility;
- inlet/fresh-air geometry;
- outlet geometry and areas;
- defrost outlet split;
- flap positions/truth table;
- actuator travel/torque;
- complete CAD.

---

# 11. Refrigerant boundary

The cabin air handler should not independently decide the vehicle refrigerant.

The final core/valve/seal specification must match the refrigerant selected for the complete heat-pump system.

Current thermal research keeps **R1234yf** strongly in the road-vehicle study because it is a modern automotive service ecosystem, but exact refrigerant remains a whole-system decision until compressor, heat exchangers, expansion devices, service procedures and applicable regulatory implications are reconciled.

Generic Alibaba universal boxes frequently advertise R134a. That makes them useful bench hardware but not automatic final-system compatibility.

---

# 12. Packaging target

Do not freeze a final air-handler dimension from generic listings.

Revision A should reserve a **compact central passenger-side/cowl air-box zone**, substantially smaller than the previously rejected 745 × 520 × 545-mm four-zone luxury HVAC benchmark.

Desired packaging behavior:

- passenger-side glovebox/trim may be sacrificed before occupant knee room or service access;
- blower/filter accessible without windshield removal;
- evaporator case can be removed without cutting structure;
- drain has a direct gravity route;
- refrigerant/coolant lines do not obstruct steering column/pedal service;
- main defrost duct stays short and broad;
- cabin filter can be replaced in minutes.

A generic under-dash prototype unit can be physically measured later to inform this reserve.

---

# 13. BUY / ADAPT / DESIGN verdict

| Item | Current verdict |
|---|---|
| Complete Mule-1 airflow test box | **BUY cheap Alibaba universal unit if useful** |
| Road-intent HVAC case/module | **BUY / ADAPT automotive one-zone family; supplier engineering may be required** |
| Blower motor | **BUY common 12-V automotive family** |
| Evaporator | **BUY as part of matched HVAC module / common core family** |
| Heater core / indoor condenser | **BUY matched to thermal architecture** |
| Cabin filter | **BUY common replaceable rectangular element if packaging permits** |
| Blend/mode doors | **part of air-box design** |
| Door actuators | **BUY simple local 12-V actuator or cable mechanism** |
| Defrost ducts | **DESIGN to selected windshield/body** |
| Face/floor ducts | **DESIGN / simple molded or fabricated parts** |
| HVAC control panel | **DESIGN around physical knobs using simple switches/pots/cables** |
| Cloud/app HVAC dependency | **REJECT** |

---

# 14. Current shortlist

### Prototype / bench

1. **GOUKU universal 12-V under-dash evaporator family** — low MOQ, useful airflow/packaging experiment.
2. generic Alibaba 12-V heating/cooling under-dash box — possible low-cost bench alternative.

### Road-intent

1. **Yinlun modular automotive HVAC family** — strongest current architecture/product reference.
2. **Hubei Meibiao** — strongest engineering/test-lab supplier evidence for custom automotive A/C/HVAC.
3. **Xiezhong International** — strong OEM thermal supplier family.
4. **MIND** — strong system supplier/benchmark, possibly more integrated than required.

---

# 15. Purchase gate

A cheap universal Alibaba box may be purchased later for experimentation without implying final architecture.

Do not freeze the road-intent HVAC box until:

- firewall/cowl/dashboard volume exists in CAD;
- selected windshield defrost area is known;
- heat-pump refrigerant topology is settled enough to define the cabin core;
- heating/cooling loads are estimated;
- airflow/defrost target is defined;
- service-removal path is modeled.

---

# 16. Current conclusion

Prototype 1 does not need a luxury HVAC computer.

The preferred cabin system is:

> **one compact automotive air box, one ordinary 12-V blower, one common conditioned-air stream, strong defrost, physical knobs, simple replaceable doors/actuators, and ducts designed around the VolksMule windshield/cabin.**

Alibaba is useful immediately for inexpensive prototype air-handler hardware and blower/component sourcing. Final road-intent air handling should use Tier-1-quality automotive HVAC engineering or a proven donor module, with Yinlun/Meibiao/Xiezhong-class suppliers setting the evidence bar.
