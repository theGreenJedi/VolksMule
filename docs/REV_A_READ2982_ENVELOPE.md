# Revision-A READ2982 integration envelope

This file converts the current public information for the **Rawsuns READ2982** CV electric drive axle into a disciplined Prototype 1 packaging input.

It is **not a component freeze** and it is **not a substitute for supplier CAD**.

The purpose is to answer three questions:

1. What can Revision-A packaging safely use now?
2. What promising behavior has already been established?
3. What geometry or interface must remain blocked until Rawsuns supplies original engineering data?

> **Use verified dimensions and interfaces. Never invent the missing box because the rendering looks about right.**

---

## 1. Current role in VolksMule

READ2982 remains the strongest current **front-primary e-axle research candidate** found through the Alibaba/Chinese-supplier sweep.

Why it remains interesting:

- independent-suspension / CV-output architecture;
- passenger-car / SUV / pickup positioning rather than a rigid commercial-truck axle;
- modest 62 kg published assembly mass;
- 55 kW rated / 110 kW peak power on Rawsuns' current manufacturer page;
- 14,000 rpm published peak motor speed;
- single 11.93:1 reduction;
- liquid cooling;
- IP67 claim on the current Alibaba listing;
- Rawsuns explicitly describes the READ2982 family as suitable for roughly 1–3 ton passenger cars, off-road vehicles and pickups in front-, rear- or all-wheel-drive layouts.

That combination is unusually close to Prototype 1's physical problem.

It still has to earn the vehicle.

---

## 2. Public engineering data usable now

### Manufacturer-published current family table

Rawsuns' current electric-axle page publishes:

| Item | READ2982 public value |
|---|---:|
| Suspension/output family | independent suspension / CV electric drive axle |
| Maximum wheel-end output torque | 2,982 N·m |
| Assembly mass | 62 kg |
| Motor rated / peak power | 55 / 110 kW |
| Motor rated / peak torque | 110 / 270 N·m |
| Motor rated / peak speed | 4,775 / 14,000 rpm |
| Reduction | single speed, 11.93:1 |

### Current Alibaba manufacturer listing adds

- permanent-magnet synchronous motor;
- liquid cooling;
- IP67 claim;
- reducer + differential architecture;
- CV-axle application;
- passenger car / off-road vehicle / pickup application;
- current sample-scale price indication roughly USD 14,000 for 1–49 sets on the viewed listing, with materially lower volume pricing shown;
- roughly 30-day listed lead time for the displayed quantity range.

Marketplace pricing and lead time are planning intelligence only. They are not purchase approval.

### Important listing inconsistency

One current Alibaba page is titled and described as READ2982 but its key-attribute model field says READ2624 while showing READ2982-class power/torque/mass data.

Therefore:

> **The exact supplier quotation, datasheet and drawing revision must identify the model unambiguously before any sample order.**

This is another example of manufacturer engineering documents outranking marketplace metadata.

---

## 3. Road-speed compatibility check

The published peak motor speed and reduction ratio let us perform one useful whole-vehicle check without supplier CAD.

Peak wheel speed is approximately:

`14,000 rpm / 11.93 = 1,173.5 wheel rpm`

Using the current VolksMule **28–34 inch tire-diameter study envelope**, ideal no-slip road speed at peak motor rpm is approximately:

| Tire diameter | Road speed at 14,000 motor rpm |
|---:|---:|
| 28 in | 97.8 mph |
| 29 in | 101.2 mph |
| 30 in | 104.7 mph |
| 31 in | 108.2 mph |
| 32 in | 111.7 mph |
| 33 in | 115.2 mph |
| 34 in | 118.7 mph |

At the published 4,775-rpm rated motor speed, the same tire envelope corresponds to roughly 33–41 mph.

### Revision-A conclusion

Unlike READ2624, READ2982 does **not** expose an obvious motor-overspeed conflict at normal U.S. highway speeds across the current tire envelope.

This does **not** prove acceptable continuous coast behavior.

Still required from Rawsuns:

- permitted continuous driven speed;
- permitted continuous back-driven/coast speed;
- overspeed duration limits;
- back-EMF behavior with inverter disabled;
- drag torque / coast-loss map;
- lubrication/bearing limits at sustained road speed;
- whether any operating mode is required while the axle is being back-driven.

---

## 4. Voltage is not yet frozen from public evidence

Current Alibaba titles market READ2982 as a **350-V-class** system, but the current manufacturer family table does not publish the operating voltage window.

Do not convert a title into a pack requirement.

Required supplier data:

- minimum operating DC voltage;
- nominal DC voltage;
- maximum continuous DC voltage;
- transient/regen maximum;
- inverter undervoltage/overvoltage thresholds;
- torque/power derating versus bus voltage;
- DC-link capacitance and precharge requirements.

The final pack series count must reconcile the actual READ2982 voltage window with the cells, rear drive unit, OBC, fast-charge system and BMS.

---

## 5. Physical packaging status

### Known

- assembly mass: 62 kg;
- independent/CV-output architecture;
- motor + reduction + differential are integrated in the axle family;
- liquid cooling is required;
- passenger/SUV/pickup use is explicitly contemplated by the supplier.

### **Unknown — do not guess in CAD**

Public material reviewed so far does **not** provide a trustworthy installation drawing containing:

- overall X/Y/Z envelope;
- motor centerline relative to differential centerline;
- left/right differential output locations;
- output flange or spline geometry;
- CV plunge requirements;
- halfshaft angular limits;
- mounting-boss coordinates;
- mount stiffness / reaction-load requirements;
- minimum service-removal clearance;
- coolant port positions and thread/interface;
- HV connector location and cable bend radius;
- LV/control connector location;
- vent/breather location;
- oil fill/drain/service access;
- allowed installation attitude;
- sprung/unsprung mass split, if any supplier terminology treats more than the drive unit as the assembly;
- final inverter location if the quoted package differs between motor/reducer/differential and 4-in-1 configurations.

### Revision-A CAD rule

Until supplier CAD arrives, the READ2982 is represented only as a **blocked provisional drive-unit zone**, not a fabricated dimensional box claimed to be the component.

The provisional zone may be used to reserve:

- approximately 62 kg at the axle center region;
- coolant routing access;
- HV/LV harness approach space;
- CV/halfshaft corridors between differential outputs and front hubs;
- underside protection / service-removal corridor.

No cradle mount may be frozen to an unpublished rendering.

---

## 6. CV / suspension interface questions

The phrase **CV electric drive axle** is encouraging but insufficient for chassis design.

Rawsuns must provide:

1. differential output spline specification;
2. mating CV stub/flange drawing;
3. whether halfshafts are supplied or customer-designed;
4. recommended inboard CV joint family;
5. maximum continuous joint angle;
6. maximum transient joint angle;
7. minimum/maximum plunge through suspension travel;
8. permissible side-to-side output offset;
9. hub-side torque requirement and recommended spline family if they offer a complete shaft;
10. torque-steer / equal-length-shaft guidance for front-drive use;
11. axle-seal service parts and replacement procedure.

VolksMule should own the **hub-to-drive-unit halfshaft interface drawing** once these constraints are known, so a disappearing halfshaft supplier cannot immobilize the vehicle.

---

## 7. Mounting and cradle-load questions

Supplier request must include:

- STEP/IGES installation model;
- dimensioned 2D installation drawing;
- center of gravity;
- mount coordinates;
- required mount count and bushing stiffness range;
- peak positive/negative reaction torque at each mount;
- shock-load factors;
- allowable case/mount deflection;
- fatigue duty cycle;
- crash/isolation recommendations;
- lifting points;
- service removal orientation.

The **front cradle remains VolksMule-owned geometry**. The drive unit supplies interface loads and mount coordinates; it does not dictate the rest of the body.

---

## 8. Cooling interface questions

Public listing states liquid cooling but not enough to size the loop.

Need:

- coolant type;
- inlet/outlet sizes;
- required flow range;
- nominal pressure drop;
- maximum inlet temperature;
- recommended control temperature;
- rated-power continuous thermal condition;
- peak-power duration at defined coolant conditions;
- derating curve;
- freeze/corrosion requirements;
- whether inverter and motor share one coolant path in the exact proposed package.

This data decides whether READ2982 shares the propulsion electronics loop or earns a separate branch.

---

## 9. Control / diagnostics gates

No production-intent use without:

- torque-command interface;
- regen-command interface;
- direction/state machine;
- CAN bus speed and physical layer;
- DBC or equivalent message specification;
- heartbeat/watchdog behavior;
- torque plausibility behavior;
- limp/fault states;
- overspeed handling;
- motor/inverter temperature reporting;
- resolver/encoder diagnostic behavior;
- DTC list;
- local offline calibration/reflash path;
- replacement-controller pairing procedure;
- firmware/revision identification.

The VCU commands the drive unit. The supplier controller does **not** become the owner of the vehicle.

---

## 10. First RFQ decision gates

### GREEN if Rawsuns provides

- exact READ2982 revision;
- STEP/2D installation data;
- voltage window;
- CV/output spline drawings;
- continuous coast/back-drive limits;
- coolant map;
- CAN/diagnostic documentation;
- mount/load data;
- prototype engineering support.

### YELLOW if

- mechanical CAD is supplied but control protocol is only partially documented;
- halfshaft solution requires adaptation but uses reproducible spline/CV standards;
- sample pricing is high but still useful for one development unit;
- inverter can be replaced by a more open compatible controller with documented motor parameters.

### RED if

- CAN torque control is undocumented/locked;
- replacement controller requires vendor-cloud authorization;
- supplier refuses installation/CV geometry before purchase;
- sustained full-road-speed back-driving is prohibited;
- exact unit cannot operate across the final pack voltage range;
- axle requires proprietary hubs/shafts with no drawings or alternate source;
- service parts are unavailable.

---

## 11. What Revision A may conclude today

**READ2982 remains worth carrying.**

Public evidence supports treating it as a plausible compact passenger/SUV drive family rather than a low-speed cart axle or oversized commercial axle.

Its published speed and gearing are compatible with the current tall-tire study in principle, and its 62 kg mass is reasonable enough that it does not obviously blow the front-axle packaging/mass budget.

But the most important packaging information is still missing.

Therefore the correct status is:

> **CARRY IN REVISION A / CAD BLOCKED PENDING ORIGINAL INSTALLATION DATA / NO PURCHASE YET**

The next progress on this component should come from **engineering documents**, not more marketplace browsing.

---

## 12. Sources reviewed

Public research current as of **2026-08-31**:

- Rawsuns — `Electric Axle Drive Systems (30 kW–620 kW)` current READ-series table;
- Rawsuns Alibaba — current READ2982 55/110-kW passenger/off-road/pickup CV-axle listings;
- Rawsuns passenger-vehicle kit pages for surrounding supplier-system context.

Detailed supplier outreach questions also live in [`ALIBABA_RFQ_WAVE1.md`](ALIBABA_RFQ_WAVE1.md).
