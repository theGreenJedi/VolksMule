# Alibaba Phase-5 chassis hardware selection

This document continues the VolksMule sourcing mission at **Roadmap Phase 5 — make it roll, steer, and stop**.

The goal is no longer to prove that China/Alibaba has suspension and brake parts. That was already established. The goal here is to narrow the supplier families and component classes that deserve to survive into Revision-A packaging and later RFQs.

> **VolksMule owns hard points, kinematics, brake sizing, steering geometry and calibration. Suppliers provide proven hardware to those interfaces.**

---

## 1. Working chassis assumptions

Current non-final study envelope:

- compact two-seat SUV/MPV roughly first-generation-CR-V scale;
- working GVWR around **5,500 lb or less**;
- front MacPherson gets first packaging study;
- rear independent layout remains open;
- tire outside diameter roughly **28–34 in**, with a preference for tall/narrow proportions and real sidewall;
- **16-in wheel studied first**, with 17 in allowed if validated brake clearance requires it;
- Revision-A brake conflict envelope approximately **320 mm front / 310 mm rear**;
- mechanical steering path with electric assist;
- hydraulic four-wheel friction brakes remain the stopping foundation;
- ABS/ESC/AEB pressure control is a vehicle-calibrated system, not a generic pump purchase.

---

# 2. Wheel hub / bearing unit

## Zhejiang Xingjie Auto Parts — strongest current hub-unit path

Manufacturer evidence identifies:

- Gen I, Gen II and **Gen III wheel hub units**;
- ABS-sensor variants;
- nearly 1,000 hub-bearing / wheel-unit types;
- ISO 9001 and **IATF 16949** certification;
- OEM-synchronous development capability using CAD/FEA tools;
- simulation and bench-test capability;
- annual capacity around 1 million wheel-unit sets.

### Why it fits VolksMule

A **Gen III bolt-on hub unit with integrated wheel-speed encoder/sensor target** is exactly the kind of solved assembly the Mule should exploit.

It can collapse several service items into one replaceable unit:

- wheel bearing;
- hub flange;
- wheel-speed sensing interface;
- axle/knuckle interface.

### Do not freeze yet

Exact hub family waits for convergence of:

- wheel bolt pattern;
- wheel offset;
- brake rotor hat geometry;
- axle spline;
- knuckle bearing pilot;
- ABS encoder/sensor type;
- front/rear axle loads.

### Current verdict

> **GREEN supplier family / exact Gen-III unit open.**

Prefer a common North-American/Japanese-pattern Gen-III architecture with broad replacement interchange over an obscure proprietary hub.

---

# 3. Dampers / struts

## Hubei Dongfeng JC — strong passive-damper manufacturing lead

Alibaba currently exposes Hubei Dongfeng JC as a long-running manufacturer of:

- twin-tube gas-charged dampers;
- struts;
- complete strut assemblies;
- coilover-style assemblies;
- conventional replacement shocks.

Current listings claim IATF/TS 16949 and show broad OE-replacement coverage across Japanese, Korean, European and American vehicles.

### Why it fits VolksMule

VolksMule does not need electronically adjustable dampers for Prototype 1.

A conventional passive twin-tube or monotube damper with:

- known stroke;
- documented force-vs-velocity curve;
- common bushings/eye/stud interfaces;
- replaceable top mounts;
- rebuild/alternate sourcing path;

is preferable to adaptive suspension complexity.

### Selection rule

Do **not** adopt an existing vehicle shock merely because its length is convenient.

Hard points and motion ratio come first. Then specify:

- extended length;
- compressed length;
- usable stroke;
- shaft diameter;
- body diameter;
- mount style;
- jounce bumper strategy;
- compression/rebound force curves;
- thermal/fade limits;
- side-load allowance for strut duty.

### Current verdict

> **YELLOW-GREEN supplier family / exact damper must be built to VolksMule load and geometry data.**

Hubei Dongfeng JC is credible enough to remain in the RFQ pool, but off-the-shelf replacement fitment is not architecture.

---

# 4. Coil springs / stabilizer bars

## Zhejiang Meili High Technology — strongest spring supplier path

Manufacturer evidence identifies:

- automotive suspension springs;
- stabilizer bars;
- OEM/Tier-1 customers;
- IATF 16949:2016;
- CNAS-accredited testing capability;
- fatigue, material, residual-stress, coating and salt-spray testing;
- lightweight/high-strength spring development;
- dedicated automobile-spring subsidiary;
- hot and cold forming capability;
- engineering-sample capability in roughly 15 days on current company material.

### Why it fits VolksMule

Springs are where **custom to our geometry** makes more sense than adapting a random donor spring.

Once corner weights, motion ratios and travel are known, a spring manufacturer can provide the correct:

- rate;
- free length;
- loaded height;
- wire diameter;
- end form;
- fatigue margin;
- coating;
- progressive/linear behavior.

This is preferable to distorting suspension geometry around a convenient donor spring.

### Alibaba comparison

Alibaba also exposes many custom spring manufacturers at very low unit prices, but many have high MOQs and weaker automotive engineering evidence. Generic marketplace spring shops remain useful for price intelligence, not as the first road-intent engineering path.

### Current verdict

> **GREEN supplier family for custom spring/stabilizer development after Rev-A loads exist.**

Meili is preferred over generic Alibaba coil-spring listings when road-intent engineering data matters.

---

# 5. Steering assist

## Zhuzhou Elite Electro Mechanical — strongest current EPS lead

Alibaba directly exposes the manufacturer for:

- **P-EPS** pinion-assist systems;
- **C-EPS** column-assist systems;
- R-EPS families;
- passenger-car/SUV steering applications.

Existing VolksMule steering work already carries:

1. P-EPS / DP-EPS for first packaging study;
2. C-EPS as the simplicity fallback;
3. R-EPS only if output/packaging requires it.

### Phase-5 selection rule

The supplier may provide the assist unit, but VolksMule must own/understand:

- rack ratio;
- rack travel;
- tie-rod inner-joint locations;
- column collapse path;
- steering-angle sensing;
- torque-sensor behavior;
- assist curve;
- failure/degraded behavior;
- CAN/local diagnostics;
- calibration replacement procedure.

### Current verdict

> **GREEN road-intent supplier family / P-EPS or DP-EPS remains first choice pending front hard points and CAD.**

Do not let EPS supplier geometry dictate scrub radius, bump steer or suspension hard points.

---

# 6. Friction brake hardware and brake-control supplier

## Zhejiang Asia-Pacific Mechanical & Electronic (APG) — strongest integrated brake supplier path

APG's current manufacturer material identifies it as a major Tier-1 brake/chassis supplier and shows current product families including:

- fixed calipers;
- cast-aluminum floating calipers;
- brake discs;
- front/rear brake assemblies;
- steering-knuckle + caliper assemblies;
- ABS;
- ESC/EPBi;
- EBB;
- IBS/one-box;
- EHB;
- conventional hydraulic brake products.

The company states that it has been developing automotive braking systems for roughly five decades and supplies OEMs.

### Why this matters

For VolksMule, APG is interesting in two distinct roles.

#### Commodity/proven mechanical brake hardware

Potentially useful:

- front floating or fixed caliper family;
- rear caliper with **mechanical parking-brake provision** where possible;
- rotors sized after axle-load/thermal calculations;
- knuckle/caliper modules as architecture references.

#### Vehicle-calibrated brake-control system

Potentially useful later:

- ABS;
- ESC;
- AEB pressure generation;
- regen/friction coordination.

This second role is **not** a catalog buy. It requires whole-vehicle calibration and test cooperation.

### Current packaging rule

Carry the existing Revision-A conflict envelope:

- up to about **320 mm front rotor**;
- up to about **310 mm rear rotor**;
- ordinary hydraulic line/service access;
- caliper removal without hub/knuckle destruction;
- wheel clearance validated before freezing 16 vs 17 in.

### Current verdict

> **GREEN supplier family for road-intent brake hardware and future calibrated ABS/ESC relationship.**

APG is substantially more interesting than anonymous Alibaba caliper/ABS listings because it can potentially supply both the mechanical brake corner and the calibrated electronic layer while still allowing VolksMule to keep a hydraulic foundation.

---

# 7. What NOT to source as a generic marketplace part

Reject for road-intent use unless traceability and engineering evidence change the verdict:

- unbranded complete coilover kits marketed mainly as lowering/performance accessories;
- random "universal" hub units;
- generic EPS columns without torque-sensor/CAN/failure documentation;
- ABS/ESC hydraulic units removed from another vehicle and treated as universal;
- brake calipers chosen solely by piston diameter or visual fit;
- coil springs selected from dimensions alone without fatigue/material/rate data;
- air suspension or adaptive dampers merely because Alibaba pricing looks attractive.

Prototype donor parts may still be useful for benches and dimensional studies. They do not become road architecture automatically.

---

# 8. Current Phase-5 architecture recommendation

Carry the following supplier/component families into the next chassis-engineering layer:

| Function | Current first path | Role |
|---|---|---|
| Hub/bearing | Zhejiang Xingjie Gen-III family | BUY / ADAPT after interface freeze |
| Damper/strut | Hubei Dongfeng JC passive automotive family | BUY/custom-valve to geometry |
| Coil spring / stabilizer | Zhejiang Meili | DESIGN RATE/GEOMETRY + BUY |
| EPS | Zhuzhou Elite P-EPS / DP-EPS | BUY / ADAPT / CALIBRATE |
| Friction brakes | APG caliper/disc family | BUY / ADAPT |
| ABS/ESC/AEB pressure control | APG-class system | SYSTEM ENGINEERING / CALIBRATE |
| Knuckles/control arms | Supplier-fabricated to VolksMule hard points where practical | DESIGN + BUY/FABRICATE |

This is intentionally not a final BOM.

---

# 9. What must be known before exact part numbers

The chassis selection cannot responsibly freeze until Revision A provides:

1. front/rear static axle loads at curb and GVWR;
2. dynamic braking load transfer;
3. wheelbase/track;
4. front/rear motion ratios;
5. jounce/rebound travel;
6. steering lock target and tire envelopes;
7. exact hub spline/bolt-pattern direction;
8. rotor/caliper torque and thermal requirement;
9. target spring frequencies / wheel rates;
10. damping targets;
11. rack travel and steering ratio;
12. ABS/ESC sensor architecture.

> **Source the hardware after the vehicle tells us what the hardware must do.**

---

# 10. Alibaba sourcing verdict

Phase 5 now has credible road-intent supplier paths for the solved chassis hardware.

The important result is not that Alibaba has cheap suspension pieces. It is that the marketplace can lead us to real manufacturers capable of producing:

- common serviceable hub units;
- conventional passive dampers;
- engineered springs and bars;
- road-intent EPS;
- complete mechanical brake systems and eventual ABS/ESC calibration support.

That means VolksMule can keep the **geometry and behavior sovereign** without needing to invent bearings, dampers, springs, steering motors or calipers.

---

## Sources reviewed

Research current as of **2026-09-01**:

- Zhejiang Xingjie Auto Parts manufacturer material: Gen I/II/III hub units, ABS sensors, IATF 16949, development/test capacity;
- Hubei Dongfeng JC Alibaba listings and supplier pages: passive shocks/struts and IATF/TS 16949 claims;
- Zhejiang Meili official manufacturer material: suspension springs/stabilizer bars, IATF 16949, CNAS testing and OEM development;
- Zhuzhou Elite Alibaba manufacturer listings: P-EPS/C-EPS/R-EPS families;
- Zhejiang Asia-Pacific Mechanical & Electronic (APG) official manufacturer material: calipers, discs, brake assemblies, ABS, ESC, EBB/EHB/IBS and chassis products.

This document narrows supplier families only. Exact road-intent parts remain gated by loads, geometry, CAD and validation.
