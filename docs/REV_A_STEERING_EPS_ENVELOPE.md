# Revision-A steering / EPS envelope

This file turns the current VolksMule steering research into a **Revision-A packaging and supplier interface envelope**.

It does not select an exact rack yet.

The goal is to narrow the correct steering-system family, define what CAD may reserve now, and explicitly identify what must wait for supplier drawings and the first suspension hard-point study.

> **Mechanical steering is the steering system. Electric assist is assistance.**

---

## 1. Architecture that remains fixed

Prototype 1 keeps:

- rack-and-pinion steering;
- continuous mechanical connection from steering wheel to road wheels;
- collapsible column;
- electric power assist;
- steering-angle sensing for ESC/AEB integration;
- local diagnostics and calibration;
- manual steering capability after loss of assist, within the practical limits of the final tire/load geometry.

Rejected for Prototype 1:

- steer-by-wire as the primary path;
- steering dependent on infotainment/cloud operation;
- an EPS controller that cannot be replaced or calibrated locally.

---

## 2. Current supplier lead

**Zhuzhou Elite Electro Mechanical Co., Ltd.** remains the strongest Alibaba-accessible road-intent EPS supplier lead found so far.

Current company material states that Elite:

- develops and manufactures EPS systems;
- has C-EPS, P-EPS, DP-EPS and R-EPS product platforms;
- operates an EPS research institute / steering engineering center;
- has IATF 16949 certification;
- has six EPS assembly lines and annual EPS capacity around 1.8 million sets;
- supplies multiple Chinese passenger-vehicle OEMs and exports systems internationally.

Current Alibaba supplier pages also expose Elite passenger-car products including:

- P-EPS pinion-assist systems;
- brushless C-EPS columns;
- customized C-EPS for sedan / EV / SUV / MPV applications.

That is enough supplier depth to justify an engineering RFQ.

It is not enough to freeze geometry.

---

## 3. Family ranking for Revision A

### First study — P-EPS / DP-EPS

These receive first packaging attention.

Why:

- assist is closer to the rack than C-EPS;
- likely adequate assist class for a compact SUV with tall tires;
- preserves a conventional mechanical rack and column;
- can avoid the larger rack-axis motor package of full R-EPS;
- potentially simpler front-cradle packaging than rack-assist while offering more assist margin than a small C-EPS system.

### Second study — C-EPS

Keep alive as the simplicity/package fallback.

Advantages:

- motor/ECU can live in the cabin/column region;
- ordinary passive rack can remain mechanically simple;
- avoids an electric motor attached to the rack in the wheel/splash/cradle zone;
- potentially excellent serviceability if column/crash integration remains clean.

Risks:

- assist capacity may become marginal with large scrub radius, high caster, high front axle load, low tire pressure or 30+ inch tires;
- column package and collapse behavior must coexist with restraints and knee-space requirements.

### Third study — R-EPS

Carry as a higher-output alternative if final loads demand it.

Advantages:

- high rack-force capability;
- good steering performance and stiffness;
- broad modern SUV precedent.

Costs:

- larger/more complex rack package;
- motor and reduction hardware consume cradle/tie-rod space;
- potentially more difficult service access;
- should not be chosen merely because it is the newest architecture.

---

## 4. Rack-force study band — benchmark only

The exact VolksMule rack force cannot be specified before we know:

- front GAWR / actual front corner loads;
- tire diameter and section width;
- tire pressure and low-pressure recovery case;
- scrub radius;
- caster;
- kingpin/steering-axis geometry;
- steering-arm length;
- rack travel and steering ratio;
- desired manual fallback effort.

Current external supplier benchmarks are still useful for scale:

- one current passenger-car DP-EPS catalog publishes **9–13 kN maximum rack force**;
- the same source publishes **12–16 kN** for an R-EPS family aimed at passenger car / van / light truck applications;
- JTEKT's published system-selection material shows C-EPS toward smaller rack-force vehicle classes and rack-assist families extending into SUV/pickup ranges.

### Revision-A rule

Use **roughly 9–13 kN as an initial P/DP-EPS comparison class**, not a VolksMule requirement.

If first-principles steering-load calculations exceed that range with reasonable margin, move upward in assist class before compromising tire geometry, steering feel or manual fallback unnecessarily.

---

## 5. Electrical envelope

Prototype 1 remains a **12-V low-voltage vehicle**.

Current comparable passenger-car DP/R-EPS catalogs commonly operate at 12 V with peak electrical currents in the tens of amps to roughly ~90 A depending on class.

Revision-A low-voltage packaging should therefore reserve:

- a dedicated high-current EPS feed from the 12-V distribution system;
- appropriately short high-current wiring;
- dedicated fuse / protected feed;
- clean chassis/ground return strategy;
- no dependence on infotainment/body-network power distribution;
- enough DC/DC and 12-V battery transient capability to support full steering assist at low vehicle speed while other safety loads are active.

Exact fuse/current sizing waits for the selected supplier system.

---

## 6. Geometry that is still blocked

Public Elite material reviewed so far does **not** provide the trustworthy installation dimensions needed to release a steering rack in CAD.

Do not invent:

- rack housing overall length;
- inner tie-rod pivot spacing;
- total rack travel;
- pinion location and angle;
- input spline;
- mounting boss coordinates;
- rack center height;
- assist motor envelope;
- ECU location;
- boot/bellows envelope;
- tie-rod thread/interface;
- column intermediate-shaft angle limits;
- collapse length;
- steering ratio.

These dimensions interact directly with bump steer, Ackermann behavior, wheel lock, CV packaging, crash structure and turning circle.

### CAD rule

Until original supplier drawings exist, Revision A may reserve **steering corridors and hard-point targets**, not a fake rack model.

---

## 7. Hard points VolksMule owns

The supplier may provide a suitable rack family, but VolksMule owns:

- front wheel centers;
- steering-axis geometry;
- tie-rod outer points;
- inner tie-rod target region;
- desired Ackermann behavior;
- bump-steer target;
- turning-circle target;
- rack location relative to axle/CV centerline;
- steering-column route through crash structure;
- service-removal path.

The rack is selected **to satisfy the vehicle geometry**.

The vehicle is not widened, lengthened or given bad steering geometry merely to accommodate an attractive catalog rack.

---

## 8. Supplier data request

For each Elite P-EPS / DP-EPS / C-EPS candidate request:

### Mechanical

- STEP/IGES;
- full 2D drawing;
- rack total length;
- inner-joint centers at rack center;
- rack stroke;
- input pinion position/angle;
- input spline spec;
- mount coordinates;
- mass and center of gravity;
- inner/outer tie-rod interfaces;
- maximum allowable tie-rod articulation;
- boot envelope;
- service parts list.

### Performance

- maximum rack force;
- continuous/thermal assist limits;
- assist-vs-speed map;
- friction/backdrive torque with assist off;
- steering-return behavior;
- rack ratio;
- backlash specification;
- maximum road-wheel kickback / impact load;
- environmental specification.

### Electrical/control

- supply voltage range;
- peak/current map;
- CAN interface;
- torque and angle sensor outputs;
- steering-angle interface for ESC if integrated;
- DTC list;
- UDS/service protocol;
- calibration tool;
- offline reflash/recovery;
- replacement-unit commissioning;
- failed-assist behavior.

### Safety

- functional-safety work products available for the exact system;
- torque-sensor plausibility handling;
- motor/ECU fault handling;
- watchdog behavior;
- overcurrent/overtemperature behavior;
- mechanical-stop/load limits.

---

## 9. Manual fallback requirement

Loss of EPS assist must not sever steering.

But "mechanically connected" is not enough if the driver physically cannot steer the vehicle at low speed after a fault.

Final validation must measure steering-wheel effort with assist disabled at least for:

- stopped/dry pavement;
- parking-lot crawl;
- moderate road speed;
- nominal tire pressure;
- reasonable low-pressure tire condition;
- maximum front-axle loading case.

This test may influence:

- caster;
- scrub radius;
- steering ratio;
- tire width;
- steering-wheel diameter;
- selected EPS family.

The correct response to poor manual fallback is not automatically "add more software."

---

## 10. Current Revision-A status

The steering architecture is now narrowed enough to proceed with chassis layout, but not enough to release exact rack geometry.

Current status:

> **P-EPS / DP-EPS FIRST STUDY — C-EPS SIMPLICITY FALLBACK — R-EPS HIGHER-OUTPUT FALLBACK — EXACT RACK CAD BLOCKED ON SUPPLIER DRAWINGS AND FRONT HARD-POINT STUDY**

This is a useful answer.

The next steering progress should come from:

1. first suspension/steering hard-point geometry;
2. estimated rack-force requirement;
3. Elite engineering drawings for matching P/DP/C-EPS families.

---

## 11. Public sources reviewed

Research current as of **2026-08-31**:

- Zhuzhou Elite / nfelite company and product-platform material;
- current Alibaba Elite EPS supplier pages;
- JTEKT EPS system-selection material for architecture/rack-force-class context;
- current third-party passenger-car DP-EPS / R-EPS catalog for rough rack-force-class comparison only.

The detailed supplier outreach remains in [`ALIBABA_RFQ_WAVE1.md`](ALIBABA_RFQ_WAVE1.md).
