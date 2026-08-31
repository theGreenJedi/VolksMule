# Alibaba thermal auxiliaries — pumps, valves, fans and simple coolant plumbing

Research current as of **2026-08-31**.

This document fills the ordinary thermal-service pieces around the previously screened Aotecar compressor/module and NF/EVLINK-class HV heater.

The architecture stays modular:

> **A failed pump, valve, fan or reservoir should be an appliance failure—not a reason to replace the whole thermal system.**

---

## 1. Strong Alibaba-native coolant-pump lead — Hebei Shenhai

Alibaba directly lists **Hebei Shenhai Electric Appliances Co., Ltd.** with main categories including:

- automobile water pumps;
- accelerator pedals;
- automotive insulation monitors;
- electric heaters;
- electric fans.

Shenhai's own manufacturer site materially strengthens the case:

- founded 2006;
- dedicated to new-energy-vehicle electronic products;
- ~48,000 m² site / ~34,000 m² buildings;
- ISO/TS 16949 certification history through TÜV Rheinland;
- provincial NEV engineering laboratory;
- more than 20 patents;
- products matched/tested and supplied in volume to more than 100 domestic vehicle manufacturers;
- named customer history including Yutong, Wanxiang, Zhengzhou Nissan, JAC, BAIC and others.

Current pump products include **HS-030-702A** and **HS-030-4816**, described specifically for cooling motors/controllers in hybrid and battery-electric vehicles. The HS-030-4816 uses a brushless motor and magnetic drive and is published as IP54.

### Verdict

> **STRONG YELLOW / first Alibaba-native 12-V coolant-pump supplier family to carry alongside local Bosch/Pierburg-style alternatives.**

Exact pump selection waits for flow/head/temperature requirements.

Sources:

- https://hbshenhai.en.alibaba.com/
- https://www.hbshenhai.com.cn/
- https://www.hbshenhai.com.cn/about.html

---

## 2. Pump specification gate

Do not select by liters-per-minute alone.

For each loop, require:

- 12-V operating window and transient tolerance;
- flow-versus-head curve;
- power/current versus operating point;
- coolant temperature range;
- ambient temperature range;
- glycol compatibility;
- cavitation/NPSH guidance where applicable;
- PWM/LIN/CAN/discrete control interface;
- tach/diagnostic feedback if available;
- dry-run behavior;
- stalled-rotor behavior;
- overtemperature protection;
- connector and hose-port geometry;
- mounting orientation;
- noise/vibration;
- service life;
- IP/environmental evidence.

### Architecture preference

Use separate ordinary pumps for understandable loops rather than one proprietary pump/valve block unless integration genuinely improves the whole car.

---

## 3. Coolant valves

### Strong Chinese automotive benchmark — Sanhua Automotive

Sanhua currently publishes automotive electric coolant valves with:

- 2–12 pathways;
- water-glycol coolant;
- BDC / BLDC / solenoid actuators;
- switching or regulating functions;
- **9–16 V** input;
- -40 to +120 °C ambient and fluid ranges;
- LIN / PWM communications;
- published pressure-difference and leakage data.

This is the evidence standard for a road-intent valve.

### Alibaba/China prototype path — Hebei Nanfeng

Hebei Nanfeng Automobile Equipment Group currently publishes EV/BTMS 3-way coolant-control valves and states:

- IATF 16949 manufacturing;
- EV battery-thermal-management application;
- OEM/ODM port/actuator customization;
- sample availability;
- vertically integrated thermal-system manufacturing;
- export to Europe and the Americas.

Nanfeng also has a long automotive heater/thermal history and produces HV coolant heaters.

### Verdict

> **BUY normal 2/3-way automotive coolant valves. Sanhua is the benchmark; Nanfeng is a credible China/Alibaba-adjacent prototype path.**

Do not buy a 10-way valve merely to imitate a current luxury EV thermal octopus.

Sources:

- https://www.sanhuaautomotive.com/en/product/detail/28
- https://www.auto-parkingheater.com/electric-bus-parts/water-valve/electric-3-way-coolant-control-valve-for-btms.html
- https://www.hvh-heater.com/

---

## 4. Electric radiator / condenser fan

Alibaba currently exposes many 12-V brushless automotive cooling-fan assemblies and supplier pages with IATF claims.

Shenhai itself publishes **HS-160-102A electronic fan** for new-energy-vehicle/bus cooling systems, giving us another integrated manufacturer path.

Current Alibaba sourcing data also identifies IATF-capable radiator-fan suppliers such as Wenzhou Cop Auto Parts and Guangzhou Jinbiao.

### Preferred strategy

Try a complete common high-volume automotive brushless fan/shroud assembly first.

Why:

- blade/shroud geometry is already developed;
- motor/control electronics are sealed;
- replacement assemblies are widely available;
- PWM control is normal;
- less fabrication than designing a fan system from scratch.

### Selection gate

Need:

- airflow-versus-static-pressure curve;
- electrical draw;
- PWM/diagnostic interface;
- motor temperature limits;
- fan diameter/depth;
- shroud dimensions;
- startup/inrush behavior;
- stall/blocked-fan behavior;
- noise;
- environmental qualification.

### Verdict

> **BUY/ADAPT common brushless automotive fan assembly. Exact SKU waits for radiator/condenser sizing.**

Sources:

- https://autopart.alibaba.com/product/car-auto-spare-parts-radiator-cooling-fan
- https://www.hbshenhai.com.cn/

---

## 5. Expansion/degas reservoir

Alibaba has deep supply of ordinary molded coolant expansion tanks for common BMW, Ford, Honda, Nissan, BYD and other applications.

This is another place where a common donor part may be better than a custom component.

### Preferred strategy

1. Establish loop volume, fill point and service location.
2. Search existing pressure/degas reservoirs with suitable:
   - volume;
   - cap pressure;
   - port sizes;
   - mounting geometry;
   - level sensor if desired.
3. Adapt brackets/hoses to the common reservoir.
4. Only commission custom molding if no ordinary tank packages well.

### Verdict

> **DONOR/BUY common reservoir first. Alibaba is excellent for cross-reference/initial units; local replacement availability matters more than branding.**

Sources:

- https://www.alibaba.com/car-expansion-tank-suppliers.html
- https://www.alibaba.com/coolant-expansion-tank-suppliers.html

---

## 6. Useful cross-lead — Shenhai insulation monitoring

Shenhai's own catalog also publishes automotive **high-voltage insulation monitors** with notable current public claims:

- online/dynamic insulation-resistance monitoring;
- self-diagnosis / automatic calibration on some models;
- leakage-capacitance adaptation;
- **PWM, CAN and ALARM outputs**;
- **0–800 VDC** application range on HS-020-3101;
- multi-channel options.

This does **not** displace Bender as the current evidence/architecture benchmark.

But it is sufficiently automotive-specific to add Shenhai as a serious Chinese alternate worth tracking for the future exact IMD comparison.

### Verdict

> **PROMOTE FROM generic-China alternate to named automotive candidate; still require exact functional-safety/environmental/EMC data before road-intent use.**

Source:

- https://www.hbshenhai.com.cn/

---

## 7. Coolant temperature / pressure / flow sensing

Do not create exotic sensor requirements.

Prefer common automotive sensors with:

- simple analog, frequency or documented CAN/LIN output;
- replaceable threaded/O-ring interface;
- known coolant compatibility;
- local availability where possible.

Not every loop needs every sensor.

Use instrumentation where it improves:

- safety;
- fault isolation;
- control quality;
- validation.

Avoid sensor accumulation without a diagnostic/control job.

### Verdict

> **BUY commodity automotive sensors after loop instrumentation requirements exist.**

---

## 8. Hose / clamps / service fittings

Thermal plumbing should use ordinary automotive practices:

- EPDM coolant hose or validated equivalent;
- standard formed hose only where necessary;
- quality constant-tension/spring clamps or appropriate crimp clamps;
- clearly accessible drain/fill/bleed points;
- protected routing;
- abrasion sleeves where required;
- no hidden permanent quick-connect dependency unless it provides a real benefit.

Alibaba can source hose, clamps and fittings once diameters and temperature/pressure ratings are known.

Final maintenance items should remain readily obtainable locally.

---

## 9. Phase-7 thermal-auxiliary shortlist

| Function | First sourcing path | Alternate/local path | Status | Blocker |
|---|---|---|---|---|
| 12-V coolant pump | **Hebei Shenhai** automotive pump family | Bosch/Pierburg/common OEM electric pump | **CARRY supplier family** | loop flow/head/thermal model |
| Electric coolant valve | Nanfeng automotive 3-way; Sanhua benchmark | common OEM valve | **CARRY family** | final loop topology/flow/Cv |
| Cooling fan | Shenhai / IATF Alibaba brushless fan supplier | common complete OEM fan/shroud | **OPEN / BUY-ADAPT** | radiator/condenser heat rejection |
| Expansion/degas tank | common donor reservoir via Alibaba cross-reference | local donor/OEM | **LOCAL-INTERCHANGE FIRST** | loop volume/package/fill point |
| IMD alternate | **Hebei Shenhai HS-020 family** | Bender benchmark / other automotive IMD | **NEW NAMED ALTERNATE** | exact safety/EMC/environment docs |
| Temp/pressure/flow sensors | common automotive families | local supplier | **OPEN** | instrumentation plan |
| Hoses/clamps | spec-driven commodity | local auto parts/hose shop | **LOCAL-FIRST** | port diameters/routes |

---

## 10. Important sourcing consequence

The thermal system does not need one supplier to own:

- compressor;
- pumps;
- valves;
- heater;
- chiller;
- fan;
- reservoir;
- controller.

We now have credible independent suppliers for each appliance class.

That preserves the architecture we wanted:

> **VolksMule owns the thermal diagram. Components plug into it.**

Aotecar's integrated module can still win if its documentation/serviceability is excellent, but it does not become mandatory just because it packages several functions neatly.

---

## 11. BOM update guidance

The master `ROADMAP_SOURCING_BOM.md` should carry:

- Hebei Shenhai as the first China/Alibaba-native coolant-pump family;
- Nanfeng/Sanhua as coolant-valve paths;
- a common brushless OEM fan/shroud strategy;
- common donor expansion tank strategy;
- Shenhai HS-020 family as a named IMD alternate beneath the Bender benchmark.

Exact part numbers remain intentionally open until the thermal and electrical models produce real operating points.