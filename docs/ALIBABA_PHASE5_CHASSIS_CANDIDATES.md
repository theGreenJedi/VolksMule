# Alibaba Phase-5 chassis candidates — roll, steer, stop

Research current as of **2026-08-31**.

This document resumes the VolksMule Alibaba sourcing mission directly from the roadmap:

> **Phase 5 — Make it roll, steer, and stop.**

The purpose is not to freeze suspension hard points or buy a pile of unrelated replacement parts. It is to identify the best current supplier paths for the ordinary mechanical pieces around the geometry VolksMule will own.

The sourcing rule remains:

> **VolksMule owns kinematics, loads, interfaces and calibration. Suppliers provide solved bearings, dampers, springs, arms, steering assist and brake hardware to those requirements.**

---

## 1. Current Phase-5 architecture boundary

Revision A currently carries:

- independent suspension at all four corners;
- MacPherson front as the first packaging study, not a final freeze;
- compact independent rear suspension, exact layout still open;
- mechanical rack-and-pinion steering with electric assist;
- Gen-III-style bolt-on hub/bearing assemblies with wheel-speed sensing preferred;
- hydraulic four-wheel friction brakes;
- ABS/ESC/AEB pressure control supplied/calibrated as a coherent automotive safety system;
- approximately **320 mm front / 310 mm rear brake conflict envelopes**;
- 16-in wheels studied first, with 17-in only if brake/knuckle geometry requires them;
- approximately **28–34 in tire OD**, favoring relatively tall/narrow shapes and locally replaceable sizes.

Nothing below is allowed to reverse those architecture choices merely because a seller has inventory.

---

# 2. Wheel hub / bearing unit

## Preferred sourcing mode: BUY / ADAPT

### Current leader — Hangzhou / Zhejiang Xingjie

Alibaba directly surfaces **Hangzhou Xingjie Auto Parts Manufacturing Co., Ltd.** as a long-running wheel-hub supplier with existing hub-unit products including 513187, 513214 and other passenger-vehicle references.

The associated Zhejiang Xingjie manufacturer material is stronger than ordinary marketplace copy:

- Gen I / Gen II / **Gen III** wheel-hub bearing capability;
- integrated ABS-sensor variants;
- nearly 1,000 market applications;
- ISO 9001 and **IATF 16949** certification claims;
- AutoCAD / Pro-E / FEA-based development capability;
- simulation/test capability;
- annual capacity quoted at approximately 1 million wheel-unit sets;
- direct chassis-company supply history.

### Why it fits VolksMule

A Gen-III bolt-on hub is exactly the kind of assembly we should avoid reinventing:

- bearing preload is factory-controlled;
- flange and encoder are integrated;
- service replacement is simple;
- ABS wheel-speed sensing can be integrated cleanly;
- several suppliers can cross-reference the same mature application family.

### Do not freeze yet

Exact hub SKU waits on:

1. target wheel bolt pattern;
2. front/rear static and dynamic radial/axial loads;
3. brake rotor hat geometry;
4. knuckle bolt pattern;
5. e-axle halfshaft spline / nut geometry at driven corners;
6. ABS encoder signal type and tooth/pole count;
7. desired commonality front/rear;
8. local North-American replacement depth.

### Current verdict

> **STRONG BUY/ADAPT path. Carry Xingjie as first hub manufacturer candidate. Choose an existing high-volume hub family where possible rather than commissioning a unique bearing.**

Alibaba evidence:

- https://www.alibaba.com/national-hub-assemblies-suppliers.html
- https://www.alibaba.com/wheel-hub-bearing-assembly-suppliers.html

Manufacturer evidence:

- https://www.zjxingjie.com/

---

# 3. Dampers / struts

## Preferred sourcing mode: BUY / ADAPT

### Current leader — Hubei Dongfeng JC Auto Shock Absorber

Alibaba repeatedly surfaces **Hubei Dongfeng JC Auto Shock Absorber Incorporated Co., Ltd.** as an established automotive damper supplier.

Current public evidence includes:

- suspension shock absorbers;
- tube shocks;
- cartridge dampers;
- complete strut assemblies;
- gas-spring products;
- Alibaba history around 10 years / direct factory representation;
- marketplace IATF/TS 16949 quality-system claims;
- official/industry-directory description as an appointed Dongfeng Motor Group shock-absorber supplier;
- annual production reported above 3 million units;
- North-American and European export activity.

### Why it fits VolksMule

VolksMule wants a passive damper with no adaptive suspension theater.

The damper should be treated as a tuneable solved component:

- conventional hydraulic/gas architecture;
- replaceable bushings/mounts where possible;
- predictable bump/rebound curves;
- common body/shaft/seal technology;
- no ECU dependency.

### First geometry strategy

Do **not** ask a supplier to invent suspension geometry.

Once Revision-A establishes:

- installed length;
- jounce/rebound stroke;
- motion ratio;
- corner mass;
- unsprung mass;
- target wheel rate;
- bump-stop strategy;
- mounting-eye/stem geometry;

then compare:

1. an existing high-volume damper family with local replacement availability;
2. a Dongfeng-JC variant built around a standard body with VolksMule-specific valving/mounts if needed.

### Current verdict

> **STRONG BUY/ADAPT supplier. Do not freeze a shock part number before suspension travel and corner loads are real.**

Alibaba evidence:

- https://www.alibaba.com/china-car-absorber-suppliers.html
- https://www.alibaba.com/honda-shock-suppliers.html

Industry/manufacturer directory evidence:

- https://www.cccme.cn/catalogs/detail-1632.aspx

---

# 4. Coil springs and stabilizer bars

## Preferred sourcing mode: BUY from a drawing / load specification

### Road-intent benchmark — Zhejiang Meili High Technology

Zhejiang Meili is a much stronger engineering benchmark than a generic marketplace spring shop:

- automotive suspension springs and stabilizer bars are core products;
- founded 1990;
- listed company;
- **IATF 16949:2016**;
- CNAS-accredited testing center;
- fatigue, residual-stress, material, salt-spray and coating test capability;
- 100+ patents;
- participates in automotive standards work;
- supplies global OEM/Tier-1 customers.

Meili is the standard of evidence to expect from a final spring source even if the transaction route is not ultimately Alibaba.

### Alibaba prototype/fabrication path

Alibaba also exposes multiple drawing-capable spring manufacturers with IATF/ISO claims. Current stronger leads include:

- **Sichuan Jingxi Auto Parts Co., Ltd.** — IATF 16949 shown on current Alibaba suspension-spring supplier pages, full customization/ODM capability;
- **Ningbo Lisheng Precision Spring Co., Ltd.** — current Alibaba supplier pages show IATF 16949 and drawing-based custom spring capability;
- **Guangdong Hershey Spring Industrial Co., Ltd.** — current Alibaba pages show IATF 16949 and custom spring design/drawing capability.

### VolksMule rule

The spring follows the car, not the other way around.

Final spring specification waits on:

- corner weights;
- front/rear motion ratios;
- desired ride frequency;
- wheel travel;
- static ride height;
- bump/rebound margins;
- payload target;
- off-road articulation target;
- damper and bump-stop selection.

### Current verdict

> **GREEN fabrication category after loads are known. Prefer an automotive spring specialist with fatigue/testing evidence. Alibaba is a viable custom-fabrication channel; exact spring dimensions are intentionally not selectable yet.**

Sources:

- https://www.alibaba.com/supplier/coil-spring-suspension-supplier.html
- https://www.alibaba.com/supplier/full-service-spring-manufacturer.html
- https://www.meilisprings.com/en/

---

# 5. Control arms / knuckles / links

## Preferred sourcing mode: ADAPT existing geometry where it fits; DESIGN + BUY fabrication where it does not

### Engineering benchmark — Jinjiang Automotive Group

Jinjiang Automotive Group reports more than 30 years supplying OEM suspension and steering hardware and lists:

- control arms;
- steering arms;
- stabilizer links;
- tie rods;
- thrust rods;
- drag links;
- passenger-car and commercial-vehicle programs;
- TS/IATF automotive quality-system history;
- major OEM customers.

Alibaba also has a very deep control-arm market, including verified manufacturers with IATF claims and low prototype MOQs on existing applications.

### VolksMule sourcing strategy

Before custom arms, attempt to find an existing donor/commodity arm or knuckle whose:

- ball-joint taper;
- bushing spacing;
- wheel-center geometry;
- hub attachment;
- steering-arm location;
- brake mounting;
- strength/load rating;

fits the geometry without damaging scrub radius, bump steer, CV angle or ground clearance.

If no existing part fits, VolksMule owns the arm/knuckle drawing and sources fabrication.

### Do not do

- do not adopt a random arm because it is cheap;
- do not allow a donor knuckle to dictate a bad steering axis;
- do not commission unique ball joints if a common replaceable joint can be incorporated;
- do not make the wheel bearing captive/nonserviceable for styling reasons.

### Current verdict

> **ADAPT/DESIGN. Alibaba is excellent for existing-arm comparison and later drawing-based manufacture; exact arms/knuckles cannot be selected until the hard-point study exists.**

Sources:

- https://www.alibaba.com/countrysearch/CN/automobile-control-arm.html
- https://www.alibaba.com/supplier/lower-control-arm-wholesaler.html
- https://www.jinjianggroup.cn/

---

# 6. Steering assist

## Preferred sourcing mode: BUY / ADAPT with supplier calibration

### Current leader remains Zhuzhou Elite

Alibaba directly surfaces **Zhuzhou Elite Electro Mechanical Co., Ltd.** with:

- C-EPS;
- P-EPS;
- R-EPS;
- passenger-car / EV / SUV / MPV application;
- brushless column systems;
- integrated sensor/ECU products;
- supplier scale materially above a normal aftermarket steering-rack seller.

Revision-A currently studies:

1. P-EPS / DP-EPS first;
2. C-EPS as the simplicity fallback;
3. R-EPS if assist/load requirements demand it.

The continuous mechanical steering path remains non-negotiable.

### Current verdict

> **Zhuzhou Elite remains the strongest Alibaba-accessible road-intent EPS path. Exact rack length/travel/ratio waits for hard points; the computer assists steering but never replaces the mechanical path.**

Sources:

- https://www.alibaba.com/a-c-steers-suppliers.html
- https://www.alibaba.com/automotive-steering-system-suppliers.html

---

# 7. Brake rotors, pads, calipers and hoses

## Rotor/pad sourcing: BUY commodity

Alibaba currently has deep brake-disc supply including:

- 320-mm vented rotor families;
- high-carbon and coated rotors;
- low-MOQ performance/reference parts;
- IATF-filterable supplier catalogs.

Current marketplace examples include 320-mm automotive rotors and mass-market passenger/SUV brake discs at low factory prices.

This confirms that rotor manufacture itself is not a sourcing blocker.

### Engineering benchmark

Revision-A already reserves approximately:

- **320 mm front rotor conflict envelope**;
- **310 mm rear rotor conflict envelope**.

The final rotor should preferably be an existing high-volume North-American application so replacements remain available locally.

Alibaba may supply prototype rotors or later alternate-source equivalents if material, vane geometry, runout, balance and traceability are documented.

## Caliper sourcing: DONOR / proven family first

A brake caliper is more sensitive than a rotor.

Before accepting a custom or generic Alibaba caliper, VolksMule needs:

- piston area;
- pad area and shape;
- bridge stiffness;
- sliding/fixed architecture;
- seal/boot temperature capability;
- hydraulic volume;
- hose/thread interface;
- parking-brake integration where relevant;
- validated compatibility with master-cylinder/HCU displacement;
- known spare pads/seals/boots.

Current Alibaba pages contain IATF-claimed brake-system manufacturers, but marketplace performance-caliper kits are **not** enough evidence for Prototype 1 road brakes.

### Brake hoses

Brake hoses are independently regulated equipment in the U.S. Final road-intent hoses should come from a supplier able to document the applicable FMVSS 106 requirements/markings/traceability for the exact assembly.

### Current verdict

> **Rotors/pads: GREEN commodity. Calipers: proven donor/application family first. Brake hoses: compliant regulated equipment. ABS/ESC HCU remains supplier-calibrated system engineering, not generic Alibaba shopping.**

Sources:

- https://www.alibaba.com/catalog/brake-discs_cid127672031
- https://autopart.alibaba.com/product/rotors-on-cars
- https://www.alibaba.com/catalog/Auto-Brake-Cables_cid127686027?categoryId=127686027&companyAuthTag=IATF+16949

---

# 8. Initial Phase-5 shortlist

| Function | Current first path | Role | Exact SKU now? |
|---|---|---|---|
| Wheel hub/bearing | Xingjie Gen-III family | BUY / ADAPT | **No — geometry/load/spline first** |
| Dampers/struts | Hubei Dongfeng JC | BUY / ADAPT | **No — stroke/load/motion ratio first** |
| Springs/stabilizer | Meili benchmark; Jingxi/Lisheng/Hershey Alibaba custom paths | BUY to drawing | **No — corner loads first** |
| Arms/links/knuckles | existing common parts first; Jinjiang-class fabrication | ADAPT / DESIGN | **No — hard points first** |
| EPS | Zhuzhou Elite | BUY / ADAPT | **No — rack geometry/assist load first** |
| Rotors/pads | common high-volume application; Alibaba alternate manufacturing | BUY | **Not until hub/bolt pattern/axle load** |
| Calipers | proven donor/application family | DONOR / ADAPT | **Not until hydraulic/brake study** |
| ABS/ESC HCU | APG/WBTL-class calibrated system | BUY + calibration | **No generic SKU** |

---

# 9. What this pass changes

The Phase-5 hardware market is not forcing a bespoke chassis.

We have credible paths for every ordinary wear/mechanical component:

- hub units;
- dampers;
- springs;
- arms/links;
- steering assist;
- rotors/pads.

The remaining blockers are now geometry and load calculations, not supplier existence.

That is good.

It means VolksMule can continue to own the suspension and steering geometry while deliberately using boring, replaceable, mass-manufactured hardware around it.

---

# 10. Next roadmap sourcing move

Continue Phase 5/6 in this order:

1. build a **hub / CV / knuckle interface matrix** for the current e-axle concept;
2. screen locally replaceable donor hub/knuckle families whose geometry may work with 28–34-in tires and 320-mm front brake envelope;
3. compare CV shaft supplier paths and splines once READ2982 output data is available;
4. keep exact spring/damper selection open until preliminary corner weights and motion ratios exist;
5. then move into Phase 6 hardware needed for **move-and-grip** validation: wheel-speed sensors, traction-control inputs and e-axle support hardware.

No supplier outreach is required to continue the public sourcing mission.