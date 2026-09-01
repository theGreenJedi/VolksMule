# Phase 5 roll / steer / stop sourcing narrowing

Research date: **2026-09-01**

This document continues the VolksMule sourcing mission using the roadmap rather than marketplace browsing for its own sake.

Phase 5 says:

> Make it roll, steer, and stop.

The task here is therefore narrower than the earlier Alibaba discovery sweep. The question is no longer whether a supplier ecosystem exists. It is:

> **Which chassis hardware should Prototype 1 deliberately standardize, which pieces should be tuned locally first, and where is Alibaba useful now versus later?**

The governing rules remain:

- VolksMule owns suspension hard points and steering geometry.
- Hydraulic friction brakes remain the stopping foundation.
- Mechanical steering remains continuous; EPS only assists.
- Passive springs and dampers are the baseline.
- Service parts should remain replaceable without factory-cloud permission.
- Prefer interfaces that permit multiple suppliers.
- A cheap part that forces proprietary geometry is expensive.

---

## 1. Executive result

### Strong standardization targets now

1. **Gen-III bolt-on hub/bearing unit with ABS encoder/sensor**
2. **Conventional replaceable ball joints and tie-rod ends**
3. **Conventional passive strut/damper interfaces**
4. **Conventional steel coil springs sized from vehicle loads**
5. **Commodity ventilated disc brake hardware sized from actual axle loads**
6. **Mechanical rack-and-pinion steering with electric assist as a separate, documented function**

### Best current sourcing roles

| Subsystem | Prototype 1 sourcing role | Alibaba / Chinese supplier role |
|---|---|---|
| Hub/bearing unit | BUY / ADAPT | Strong now |
| Ball joints / tie rods | BUY common family | Strong now |
| Control arms | DONOR/ADAPT first; DRAWING if needed | Strong after geometry |
| Knuckles | DONOR/ADAPT if possible; DESIGN if needed | Fabrication later |
| Dampers/struts | DONOR/BUY for first tuning | Strong custom supplier after targets stabilize |
| Coil springs | Local/custom small-batch first | Strong production supplier after rate/free-length settle |
| Rotors/calipers/pads | BUY common catalog family | Strong, but local replacement ecosystem matters more than origin |
| ABS/ESC hydraulic/control unit | SYSTEM ENGINEERING | APG/WBTL-class direct relationship, not generic marketplace unit |
| EPS | SUPPLIER ENGINEERING / ADAPT | Zhuzhou Elite remains strongest Chinese lead |

### Main conclusion

> **Alibaba is already useful for the wheel-end hardware, but Prototype 1 should not pay production MOQ to custom-tune springs and dampers before the vehicle has real corner weights and motion ratios.**

For springs/dampers, tuning speed matters more than unit price during Mule #1. Once rates, lengths and force-velocity curves stabilize, Alibaba/Chinese automotive suppliers become attractive for repeatable production.

---

# 2. Wheel hub / bearing — first deliberate chassis standard

## Preferred architecture

Carry a **Gen-III bolt-on integrated hub unit** with:

- integrated bearing preload;
- wheel flange;
- ABS encoder/sensor support;
- replaceable bolt-on service interface;
- driven-wheel spline where required;
- ordinary wheel studs or bolts;
- multiple replacement manufacturers.

Why this is attractive:

- field bearing presses are not required for routine replacement;
- preload is factory-set;
- ABS sensing is already integrated into a mature service part;
- local parts stores and independent shops understand the architecture;
- the knuckle interface can be documented and reused.

## Strong supplier lead — Zhejiang Xingjie

Current manufacturer data states that Zhejiang Xingjie produces:

- Gen-I, Gen-II and Gen-III wheel bearing/hub units;
- ABS-sensor-equipped hub units;
- nearly 1,000 product types;
- roughly 1 million hub-unit sets annual production capacity;
- ISO 9001 and IATF 16949 certified production;
- CAD/FEA and validation capability.

Manufacturer source:

- https://www.zjxingjie.com/
- https://www.zjxingjie.com/about.html

**Current verdict: STRONG YELLOW-GREEN supplier family.**

This is a good example of the correct sourcing relationship: VolksMule should define required bearing loads, bolt pattern, flange offset, spline/CV interface, brake-pilot geometry and sensor interface, then choose an existing catalog unit if possible rather than letting the supplier choose the vehicle geometry.

## Bolt pattern

**5×114.3 remains an attractive study target, not a freeze.**

Reasons:

- enormous North American compact-SUV/crossover wheel ecosystem;
- abundant replacement hubs and rotors;
- common Honda/Nissan/Hyundai/Kia/Mazda/Toyota-adjacent application families;
- broad aftermarket wheel availability;
- compatible with the project's preference for locally replaceable tires/wheels.

Do not freeze 5×114.3 until these converge:

- front/rear hub load rating;
- driven spline/CV requirement;
- brake rotor hat/pilot geometry;
- wheel offset;
- 16-vs-17-inch brake clearance;
- actual tire envelope;
- preferred common donor/alternate family.

## Hub requirement to carry forward

The hub RFQ / selection table eventually needs:

- static radial load;
- dynamic radial load/test basis;
- axial load/test basis;
- overturning-moment basis;
- fatigue life/test cycles;
- wheel offset assumptions;
- flange runout;
- ABS encoder type/pole count;
- sensor air gap and connector;
- driven spline size/count/engagement length;
- nut torque / retention method;
- corrosion/salt validation;
- complete drawing and service torque values.

> **"For SUV" is not a load rating.**

---

# 3. Ball joints, tie rods and links — buy boring parts

Prototype 1 should strongly prefer ordinary serviceable joint families.

Selection preference:

- bolt-in or press-in lower ball joint if packaging allows;
- common automotive tapered stud;
- ordinary outer tie-rod end;
- ordinary stabilizer-link ball joints if an anti-roll bar is ultimately required;
- mechanical retention that is visible and inspectable;
- multiple aftermarket brands.

Do not create a custom taper merely to save a few millimeters.

The control arm and knuckle should adapt to a useful common joint before the project invents a proprietary joint.

### Alibaba role

**GREEN commodity market, but exact family waits for geometry/load calculations.**

Alibaba is appropriate for manufacturer/supplier mapping and later repeat purchase. For Mule #1, a locally stocked equivalent may be preferable so replacement remains immediate during suspension iteration.

---

# 4. Control arms — geometry first, supplier second

Existing research found strong fabrication ecosystems including Jinjiang, MingTu and DLZ.

Current Phase-5 narrowing:

### First choice

Try to adapt an existing mass-market arm **only if** its:

- ball-joint position;
- inner-pivot spacing;
- bushing axes;
- section strength;
- CV clearance;
- wheel-travel envelope;

fit the VolksMule geometry without corrupting suspension kinematics.

### Second choice

If no donor arm works, make the arm a **VolksMule-controlled drawing** and buy the fabrication.

For Prototype 1, stamped/welded or forged steel should be studied before expensive custom aluminum.

Why:

- easy to understand;
- robust rough-road behavior;
- conventional corrosion treatments;
- straightforward repair/reproduction path;
- lower incentive to hide geometry inside a one-piece casting.

**Current verdict: DONOR/ADAPT first; DESIGN + BUY-FABRICATED-TO-DRAWING second.**

No generic Alibaba control arm should set the hard points.

---

# 5. Dampers / struts — Alibaba is real, but production MOQ matters

## Strong manufacturer lead — Hubei Dongfeng JC

Alibaba currently exposes Hubei Dongfeng JC Auto Shock Absorber as a long-standing manufacturer with product families including:

- suspension shock absorbers;
- tube dampers;
- cartridge dampers;
- complete strut assemblies;
- gas springs.

Current Alibaba supplier pages show the company as a 17-year supplier with reported revenue above US$100 million and North American export activity.

Examples:

- https://www.alibaba.com/china-car-absorber-suppliers.html
- https://www.alibaba.com/shock-absorber-auto-parts-suppliers.html

Current exact listings show typical minimum orders around **50–100 pieces** for many ordinary passenger-vehicle shock/strut products.

**Verdict: STRONG YELLOW automotive damper supplier; poor fit for iterative one-off custom tuning unless sample policy differs from public MOQ.**

## Prototype 1 strategy

Do not choose final custom damping before we know:

- actual curb and payload corner weights;
- front/rear sprung mass;
- unsprung mass;
- spring rate;
- motion ratio;
- jounce/rebound travel;
- tire vertical stiffness;
- body-control target;
- rough-road impact target.

### Mule #1

Prefer an existing replaceable strut/damper family or low-volume local motorsport/industrial damper service that permits rapid revalving.

### After tuning stabilizes

Send Dongfeng JC-class supplier:

- extended/compressed length;
- stroke;
- mounting details;
- rod/piston size;
- target force-velocity curves;
- gas pressure;
- temperature/fade requirements;
- durability cycle;
- salt/corrosion requirements.

Then Alibaba/Chinese automotive manufacturing can become a cost-effective repeat source.

### Hard rule

> **A damper that fits dimensionally but has the wrong force-velocity curve does not fit the car.**

---

# 6. Coil springs — tune locally before production sourcing

Several real Alibaba spring manufacturers exist.

## Zhejiang Meili — automotive benchmark

Meili states that it:

- manufactures automotive suspension-system springs;
- supplies global OEM and Tier-1 customers;
- has IATF 16949 certification;
- operates a CNAS-accredited test center;
- performs mechanical, fatigue, residual-stress, coating and salt-spray validation;
- has participated in more than 20 standards and holds 100+ patents.

Source:

- https://www.china-springs.com/en/
- https://china-springs.com/en/about.html

**Verdict: STRONG GREEN benchmark / direct supplier candidate once geometry is stable.**

## Zhejiang Jinchang — explicit Alibaba customization path

Alibaba directly lists Jinchang custom automotive suspension coil springs.

Current examples:

- JC-0121 custom automotive coil spring: TS16949 claim, custom size, sample time ~15 days, but public MOQ around 1,000 pieces.
- JC-0078 custom suspension spring: custom rate/size, sample time 3–7 days, public MOQ around 500 pieces.

Sources:

- https://www.alibaba.com/product-detail/China-Zhejiang-factory-custom-Coil-over_201747476.html
- https://www.alibaba.com/product-detail/JINCHANG-500-Pcs-JC-0078-Suspension_201861831.html

**Verdict: YELLOW-GREEN production path; public MOQ makes it unattractive for early spring-rate iteration.**

## Phase-5 decision

Mule #1 spring strategy:

1. calculate initial wheel rate/body natural-frequency target;
2. select a readily adjustable/local spring source;
3. test empty, normal-load and payload conditions;
4. settle rate/free length/seat diameter/block height;
5. then quote automotive production suppliers.

This is cheaper than buying 200–1,000 incorrect springs because Alibaba's unit price looked attractive.

---

# 7. Brake hardware — separate the metal from the control system

## Current geometry reserve

Revision-A already carries approximately:

- **320 mm front rotor conflict envelope**;
- **310 mm rear rotor conflict envelope**;
- 16-inch wheel first study;
- 17-inch wheel fallback if validated brakes need the room.

Those are packaging bounds, not final brake sizes.

## APG / Zhejiang Asia-Pacific — strongest broad brake-system supplier lead

APG's current product portfolio includes:

- fixed calipers;
- aluminum floating calipers;
- front/rear caliper families;
- brake discs;
- complete disc-brake assemblies;
- ABS;
- ESC/EPBi;
- electric brake booster;
- one-box IBS;
- EHB regenerative electro-hydraulic brake systems.

APG describes itself as a long-established Tier-1 automotive brake supplier.

Source:

- https://www.apg.cn/

**Verdict:**

- foundation brake metal: **GREEN supplier class**;
- ABS/ESC/AEB pressure control: **SYSTEM ENGINEERING / calibration relationship required**.

## WBTL / Bethel — very strong system benchmark

WBTL reports mass production and very large production histories for calipers, EPB and wire-controlled brake systems. Its 2026 material reports volume production of electro-mechanical braking and extensive system/vehicle validation.

Sources:

- https://en.btl-auto.com/
- https://en.btl-auto.com/index.php/News-and-Trends/2026/05-26/416.html

WBTL's sophistication is useful as a benchmark, but Prototype 1 should not let modern brake-by-wire capability displace the simple hydraulic foundation.

### Phase-5 brake sourcing rule

Use common, well-supported:

- ventilated rotors;
- floating calipers unless loads justify fixed calipers;
- conventional pads;
- mechanical parking-brake mechanism where practical;
- conventional hydraulic hoses/lines.

Then integrate ABS/ESC/AEB as a separately validated pressure-control system.

### Alibaba role

Alibaba is suitable for:

- commodity rotors/calipers/pads for prototypes and comparisons;
- supplier discovery;
- later production pricing.

But final road hardware should be selected by:

- thermal capacity;
- piston area;
- pedal/master-cylinder relationship;
- parking-brake architecture;
- local replacement availability;
- FMVSS/system validation;

not by marketplace price.

---

# 8. EPS — narrow the assist family, do not let EPS define steering geometry

## Zhuzhou Elite remains the strongest Alibaba-accessible road-intent lead

Alibaba directly exposes Zhuzhou Elite product families including:

- P-EPS / pinion electric power steering;
- C-EPS / column electric power steering;
- R-EPS;
- steering-system OEM products.

Current Alibaba source:

- https://www.alibaba.com/electric-power-steering-system-suppliers.html

Manufacturer research already indicates C-EPS, P-EPS, DP-EPS and R-EPS capability and automotive production background.

## Phase-5 narrowing

### P-EPS / DP-EPS — first study

Why:

- assist is applied closer to the rack;
- less torque transmitted through upper column than pure column assist;
- potentially useful for a compact SUV-scale front axle;
- preserves mechanical rack path.

### C-EPS — simplicity fallback

Why:

- compact;
- can permit a relatively conventional mechanical rack;
- often easier to package/service independently from the rack.

Risk:

- assist capacity / column torque may be inadequate once tire scrub radius and axle load are known.

### R-EPS — higher-output fallback

Use only if front axle/tire loads justify the extra cost/packaging/integration complexity.

## Hard rules

Regardless of assist type:

- steering remains mechanically connected;
- driver can steer after assist failure, subject to acceptable effort;
- torque/angle sensing is redundant enough for road-intent safety;
- assist curve and return behavior are locally calibratable;
- CAN failure does not command steering motion;
- no cloud/account required to commission replacement hardware;
- local DTCs and firmware/calibration version are accessible;
- rack travel, steering ratio and tie-rod geometry remain VolksMule design inputs.

---

# 9. Prototype-1 chassis sourcing order

The correct order is now:

## Step 1 — vehicle geometry

Freeze enough of Revision-A to know:

- wheelbase/track study point;
- tire diameter/width candidate;
- wheel offset range;
- front/rear corner loads;
- suspension travel;
- front steering angle;
- rough knuckle/hub center location;
- front/rear CV centerlines.

## Step 2 — hub/joint standardization

Choose candidate:

- Gen-III hub family;
- bolt pattern;
- driven spline;
- ball joint;
- tie-rod end;
- brake pilot/hat relationships.

These interfaces unlock the knuckle and halfshaft work.

## Step 3 — first springs/dampers

Calculate initial rates and select **small-quantity tunable** components.

Do not optimize production price yet.

## Step 4 — brake metal

Use axle loads / CG / tire radius / stopping target to size:

- rotor effective radius;
- rotor thickness/thermal mass;
- caliper piston area;
- pad area;
- master-cylinder/pedal relationship.

Then choose a common service family.

## Step 5 — EPS

Use measured/estimated steering loads from the real tire/geometry to choose C/P/DP/R assist class.

## Step 6 — supplier conversion

Once the geometry/tuning values stop moving rapidly:

- Xingjie-class hub supplier can quote exact hub family;
- Dongfeng JC-class damper supplier can valve to our curve;
- Meili/Jinchang-class spring supplier can manufacture the settled spring;
- APG/WBTL-class supplier can be approached for calibrated brake-control integration;
- Zhuzhou Elite can recommend/quote the proper EPS family from actual steering loads.

---

# 10. Current BUY / ADAPT / DESIGN verdict

| Part | Current verdict |
|---|---|
| Hub/bearing | **BUY — common Gen-III family** |
| ABS wheel-speed sensor/encoder | **BUY with hub family** |
| Ball joints | **BUY common family** |
| Tie rods/ends | **BUY common family** |
| Control arms | **DONOR/ADAPT; DESIGN only if geometry demands** |
| Knuckles | **DONOR/ADAPT first; DESIGN + fabricate if necessary** |
| Springs | **BUY/TUNE low-volume first; later custom production** |
| Dampers | **BUY/TUNE low-volume first; later custom production** |
| Anti-roll bars | **DESIGN/TUNE only if handling work proves necessary** |
| Rotors | **BUY common family after load sizing** |
| Calipers | **BUY common family after load sizing** |
| Pads | **BUY locally common family** |
| Parking brake | **BUY/ADAPT mechanical system** |
| ABS/ESC/AEB control | **SUPPLIER-CALIBRATED SYSTEM** |
| Steering rack | **BUY/ADAPT conventional rack geometry** |
| EPS | **BUY/SUPPLIER-ENGINEERED assist, mechanical steering retained** |

---

# 11. Items deliberately not bought yet

Do **not** buy yet:

- custom production springs;
- custom production dampers;
- random performance coilovers;
- generic racing spherical-joint control arms;
- a rack because its overall width looks approximately right;
- an EPS unit without torque/assist/interface data;
- an ABS/ESC pump/controller from another vehicle as the road-intent solution;
- oversized fixed calipers for appearance;
- wheels before hub/brake/offset convergence.

Prototype donor pieces may still be purchased later for bench/packaging experiments, but they are not architecture commitments.

---

# 12. Current mission result

Phase-5 Alibaba sourcing is no longer a question of availability.

The useful answer is now:

> **Standardize the wheel-end interfaces early. Tune springs/dampers cheaply and locally while the car changes. Use Alibaba automotive manufacturers when the specification becomes stable enough to deserve production tooling/MOQ. Treat EPS and ABS/ESC as application-engineering systems, not anonymous catalog electronics.**

This preserves the whole VolksMule principle:

> **Buy the solved mechanism. Own the geometry, calibration and interface.**
