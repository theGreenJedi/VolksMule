# Revision-A thermal / HVAC packaging envelope

This file turns the existing thermal sourcing work into physical Revision-A packaging boxes.

It does **not** freeze a compressor, integrated module, cabin HVAC box, refrigerant, or final valve topology. It exists so the vehicle model cannot pretend thermal hardware has no volume.

> **Keep the thermal system modular enough to understand, service and replace. Do not let comfort features turn into an integrated maze.**

---

## 1. Current supplier direction

Aotecar remains the strongest current Chinese automotive thermal-management lead because it supplies:

- high-voltage electric compressor families for 400-V and 800-V platforms;
- CAN/LIN-controlled compressor electronics;
- heat-pump-capable components;
- integrated new-energy-vehicle refrigerant/coolant modules;
- cabin HVAC / air-handling assemblies;
- battery coolers/chillers;
- OEM-grade automotive manufacturing and IATF 16949 positioning.

Prototype 1 still prefers a modular architecture unless an integrated module proves transparent and serviceable.

---

## 2. Integrated thermal-management module — real packaging benchmark

Aotecar currently publishes an integrated NEV thermal-management module with:

- refrigerant sub-module;
- coolant sub-module;
- up to **10 kW cooling**;
- up to **8 kW heating**;
- **20 kW water-cooled condenser**;
- **10 kW chiller**;
- three integrated pumps in the 60–150 W range;
- three-way and ten-way coolant valves;
- support claims for R134a / R1234yf / R290;
- **300 × 400 × 275 mm** overall dimensions;
- **11 kg** mass.

### Revision-A implication

This is compact enough that a complete refrigerant/coolant integration module is physically plausible in a CR-V-scale Mule.

Carry a gross service zone of approximately:

- **450 × 400 × 350 mm**;
- hose and refrigerant fitting clearance on all routed sides;
- connector/service access;
- isolation from direct crash intrusion;
- removable mounting rather than buried body integration.

The gross zone is a VolksMule packaging reserve, not an Aotecar product dimension.

---

## 3. Do not mistake the integrated module for a mandatory architecture

The integrated module only wins if Aotecar provides:

- internal refrigerant schematic;
- internal coolant schematic;
- valve truth tables;
- pump specifications;
- individual replacement/service procedure;
- CAN/LIN interfaces;
- failsafe/default valve states;
- local diagnostics;
- CAD;
- replacement subcomponents.

If those are withheld, use it as a benchmark and build the vehicle from separate compressor/chiller/pumps/valves.

> **Integration is allowed. Dependency is not.**

---

## 4. Battery chiller / cooler benchmark

Aotecar currently publishes a battery cooler assembly:

- **217 × 195 × 148 mm**;
- **1.3 kg**;
- up to **18 kW** heat-exchange capacity under stated conditions;
- configurable plate count/flow arrangements;
- R290 / R1234yf / R134a compatibility claims.

This is a useful physical reference for the refrigerant-to-coolant coupling needed when battery temperature must be pulled below ambient.

### Revision-A reserve

If the final system uses a separate chiller rather than an integrated thermal module, reserve approximately:

- **280 × 250 × 210 mm gross chiller/service zone**;
- hose/refrigerant fitting access;
- isolation from cell vent paths;
- drain/leak management;
- bolted replacement access.

---

## 5. High-voltage compressor envelope

Aotecar confirms current E26 / E34 / E40 / E45 electric-compressor families for 400-V/800-V EV platforms and CAN/LIN control.

Exact current E-series CAD is still a supplier-document item.

A separate current 34-cc / 350-V automotive compressor family provides a useful category benchmark:

- ~209 mm compressor length;
- ~6.1 kg mass;
- 230–420 VDC operating range;
- ~5.9 kW rated cooling capacity;
- CAN 2.0B or PWM control;
- 12-V LV control interface.

This is **not** being substituted for Aotecar. It shows the approximate physical class of a practical compact-EV compressor.

### Revision-A compressor placeholder

Reserve approximately:

- **300 × 250 × 250 mm gross service zone**;
- refrigerant hose bend/access;
- HV/LV connector space;
- NVH-isolated mounts;
- enough clearance for removal without disturbing the battery pack or steering rack.

Replace this placeholder with Aotecar CAD before brackets are released.

---

## 6. Cabin air-handling unit — current large benchmark is deliberately rejected

Aotecar publishes a high-end four-zone air-handling unit used in the NIO ET9:

- **745 × 520 × 545 mm**;
- <= **15.8 kg**;
- >=5.6 kW cooling;
- >=4.6 kW internal-condenser heating;
- >=6.3 kW PTC heating;
- >=650 m3/h airflow;
- four temperature zones;
- numerous damper motors and sensors.

This is excellent evidence for what **not** to carry into Prototype 1.

VolksMule has two seats and values simple physical controls.

Therefore:

> **Do not reserve 745 × 520 × 545 mm for cabin HVAC. That module is an upper-bound / complexity reject, not a candidate.**

---

## 7. Cabin HVAC requirement instead

Prototype 1 needs a simpler two-seat air handler providing:

- windshield defrost/defog;
- face vents;
- footwell heat;
- simple fresh/recirculation control;
- one cabin temperature zone or simple left/right distribution only if essentially free;
- ordinary replaceable blower;
- evaporator;
- internal condenser/heater core arrangement required by the final heat-pump topology;
- physical fan/temperature/mode controls;
- no aromatherapy, four-zone theater, or dozens of motorized doors.

### Useful evaporator scale

Aotecar publishes a platform evaporator approximately:

- **315 × 236 × 38 mm**;
- **1.03 kg**;
- 8.5 kW heat-exchange capacity under its stated test condition.

That supports the conclusion that the heat exchanger itself is modest; the giant four-zone box is largely packaging/control complexity.

### Current CAD status

Do **not** invent a complete two-seat HVAC-box dimension yet.

Reserve a dashboard/cowl HVAC corridor and keep final box geometry blocked on either:

1. a simple production donor/commodity HVAC box; or
2. an Aotecar/simple-supplier two-seat/single-zone drawing.

The body/cowl should be designed to accept a serviceable box from the cabin side where practical.

---

## 8. PTC / coolant backup heat

The sourcing screen already identified 400-V-class coolant-heater families around:

- 3 kW;
- 5 kW;
- 7 kW.

The current thermal architecture still prefers roughly **5–7 kW** as the first backup-heater study range, subject to defrost and cold-weather validation.

Reserve a separate small heater/service branch unless the final integrated thermal module includes a documented, replaceable equivalent.

No final physical box is frozen until the exact NF/other automotive heater drawing is obtained.

---

## 9. Physical control philosophy

Thermal electronics may coordinate pumps, valves and compressor speed.

The driver still gets simple physical controls for:

- fan speed;
- temperature;
- vent mode;
- defrost;
- recirculation where provided.

Loss of infotainment must not remove defrost or basic cabin heat/cooling control.

The thermal controller may be smart. The screen does not own the heater.

---

## 10. Service placement rules

Thermal hardware should be placed so that:

- compressor can be removed without battery-pack removal;
- integrated module/chiller is bolted and reachable;
- refrigerant service ports are accessible;
- coolant fill/drain/bleed points are accessible;
- pumps and valves can be replaced individually if the architecture allows;
- leaks drain away from HV connectors;
- crash zones do not immediately crush refrigerant/HV components;
- hot refrigerant lines are protected from occupants and service hands;
- hoses do not cross steering/tire jounce envelopes;
- cabin air box does not require windshield removal for ordinary service.

---

## 11. Revision-A boxes to carry now

### Real supplier envelope

Aotecar integrated thermal module:

> **300 × 400 × 275 mm / 11 kg**

Carry gross vehicle service zone:

> **~450 × 400 × 350 mm**

### Separate battery chiller option

Aotecar battery cooler:

> **217 × 195 × 148 mm / 1.3 kg**

Carry gross service zone:

> **~280 × 250 × 210 mm**

### Compressor placeholder

Carry gross provisional zone:

> **~300 × 250 × 250 mm**

until Aotecar current E-series CAD arrives.

### Cabin HVAC

> **NO FINAL BOX YET**

The published 745 × 520 × 545-mm four-zone unit is explicitly **not** the desired architecture.

---

## 12. Current conclusion

Thermal packaging is no longer a blank page.

A CR-V-scale vehicle can plausibly fit a serious integrated thermal module, chiller and compact HV compressor without becoming an HVAC machine with wheels.

The remaining significant thermal packaging blocker is now **the simple cabin air-handler box**, plus exact current E-series compressor CAD.

Status:

> **THERMAL ENGINE-BAY PACKAGING BLOCKER SUBSTANTIALLY REDUCED / SIMPLE CABIN HVAC BOX STILL OPEN / FINAL COMPRESSOR CAD STILL REQUIRED**

---

## 13. Sources reviewed

Public research current as of **2026-08-31**:

- Aotecar current E-series electric-compressor family material;
- Aotecar integrated NEV thermal-management module;
- Aotecar battery cooler;
- Aotecar high-end four-zone air-handling unit;
- Aotecar platform evaporator;
- existing VolksMule `ALIBABA_THERMAL_MANAGEMENT.md` sourcing screen.
