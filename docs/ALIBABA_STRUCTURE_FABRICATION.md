# Alibaba / China sourcing for structure, cradles, and battery enclosure fabrication

This document records where Alibaba/Chinese manufacturing helps with the Prototype 1 structure—and where it should **not** own the design.

The structural architecture remains:

- welded steel safety cell;
- bolt-on/adaptable front and rear cradles;
- removable non-structural traction-battery enclosure;
- repairable body and service interfaces.

## Executive verdict

| Item | Prototype 1 sourcing direction |
|---|---|
| Safety-cell geometry / crash load paths | **DESIGN — VolksMule owns** |
| First safety-cell fabrication | **LOCAL PREFERRED** |
| Front/rear cradle geometry | **DESIGN/ADAPT — VolksMule owns interfaces** |
| First cradle fabrication | **LOCAL PREFERRED; China useful once drawings stabilize** |
| Battery enclosure geometry / crash protection | **DESIGN — VolksMule owns** |
| First battery-box fabrication | **LOCAL PREFERRED; China quote/second-source after Rev stabilizes** |
| Laser-cut brackets/tabs/gussets | **GREEN — Alibaba/China or local quote competitively** |
| CNC mounts/spacers/adapters | **GREEN — excellent prototype sourcing candidate** |
| Stamped production parts | **GREEN later — after geometry stabilizes/tooling makes sense** |
| Body stampings/small-batch body panels | **YELLOW/GREEN later** |
| Decorative/nonstructural trim | **GREEN** |
| Structural material specification | **DESIGN/ENGINEERING — never seller-selected** |

The key principle is:

> **Outsource manufacturing, not structural judgment.**

## 1. Why Mule #1 structure should be fabricated close to the build

Prototype 1 will discover geometry in the real world:

- steering rack clearance;
- e-axle mounts;
- CV plunge/angles;
- spring/damper towers;
- brake hose routing;
- battery-box clearances;
- charge-port routing;
- HVAC packaging;
- seat/belt/restraint anchor positions;
- pedal box and steering column;
- windshield/cowl geometry;
- service access.

During that phase, a bracket moving 10–20 mm is normal development—not a production defect.

A locally fabricated first structure buys:

- same-day measurement/rework;
- direct inspection of weld fit-up;
- easier jig modification;
- less freight on large low-value-volume parts;
- faster learning loops;
- ability to cut a mount off and redesign it without waiting for an overseas shipment.

This is not anti-China or anti-Alibaba. It is **prototype logistics**.

## 2. China becomes much more attractive after geometry stabilizes

Once the drawings survive actual vehicle fit-up and testing, Chinese automotive manufacturing becomes highly credible for:

- stamped brackets;
- welded subframes;
- machined suspension/e-axle mounts;
- battery tray/enclosure production;
- body panels;
- laser-cut and formed parts;
- production fixtures;
- aluminum castings;
- corrosion coating;
- PPAP/APQP production control.

At that point, the shipping delay is amortized across stable parts rather than engineering iterations.

## 3. Small-batch body supplier benchmark — Jiangsu Shenghao

**Status: YELLOW/GREEN — later body/production RFQ**

Jiangsu Shenghao Vehicle Industry currently advertises **small-batch vehicle body manufacturing** with:

- mold development;
- sheet-metal processing;
- stamping;
- laser cutting;
- welding assembly;
- electrophoretic coating;
- finished-product inspection;
- IATF-16949-centered production processes.

Reference:
https://www.aotubody.com/

Why it matters:

The Chinese supplier ecosystem is not limited to cheap replacement panels. Suppliers exist that can take stable body CAD and manufacture automotive sheet-metal assemblies in smaller batches.

Why it is not Mule #1's structural designer:

VolksMule still defines the body load paths, joints, materials, weld requirements and validation plan.

## 4. Structural/chassis supplier benchmark — Guangzhou Yihe

**Status: YELLOW — later structural-parts RFQ**

Yihe advertises IATF 16949 automotive production covering:

- structural chassis parts;
- suspension/steering components;
- custom EV components;
- CNC machining;
- stamping/casting;
- inspection/fatigue verification;
- OEM/ODM production.

Reference:
https://www.yiheautoparts.com/ev-auto-parts-manufacturers-supplier/

Potential role:

- stable production brackets;
- cradle/subframe components;
- machined or formed mounts;
- alternate manufacturing quotes after prototypes are proven.

## 5. EV subframe manufacturing is a solved supplier capability

Chongqing United currently publishes IATF-16949 EV subframe production using low-pressure aluminum casting plus welding/assembly, including approximately 1300 × 1000 × 600-mm assemblies and production traceability.

Reference:
https://www.cqunited.com/sale-42735974-aluminum-alloy-low-pressure-casting-parts-welded-and-assembled-subframe-for-ev-chassis.html

This is important **as manufacturing evidence**, not as a recommendation that VolksMule suddenly switch to cast-aluminum cradles.

Prototype 1 should keep the cradle architecture simple and fabricable unless analysis proves a casting has enough benefit to justify tooling and supplier dependence.

### Cradle rule

> **Do not cast what can sensibly be cut, bent, welded, repaired, and revised during development.**

A casting may become attractive later for weight/cost at volume.

## 6. CNC / one-off precision parts are an excellent China-sourcing category

Several Chinese automotive prototype firms advertise IATF-oriented CNC and sheet-metal work starting from one-off quantities.

OMO, for example, advertises automotive/EV machining from single-unit orders and specifically shows battery/chassis work.

Reference:
https://omocnc.com/Automotive-EV/

APA Prototype advertises IATF-16949/PPAP-oriented automotive machining, battery housings, brackets, and low-volume prototype support.

Reference:
https://www.apa-proto.com/cnc-machining/cnc-milling/automotive-cnc-components.html

These may be ideal for pieces such as:

- steering-rack mounts;
- e-axle adapter plates;
- bearing carriers where a donor part cannot be used;
- precision suspension spacers;
- brake brackets after analysis;
- HV connector bulkhead plates;
- compressor/OBC mounting plates;
- jig blocks and locating fixtures.

### Rule

Structural significance does not disappear because the part is CNC-machined. Require material certificates and dimensional inspection for critical pieces.

## 7. Alibaba battery-enclosure fabrication is abundant—but it is a manufacturing service

Alibaba currently advertises custom EV battery-box/tray/enclosure fabrication from aluminum/stainless/sheet metal at prototype-friendly quantities, including MOQ-1 listings.

Discovery reference:
https://www.alibaba.com/premium/lithium_ion_battery_holder.html

This proves the fabrication service is commodity-accessible.

It does **not** mean a marketplace supplier should choose:

- pack material;
- wall thickness;
- mounting points;
- intrusion structure;
- sealing concept;
- pressure/vent strategy;
- cell retention;
- coolant routing;
- crash loads.

Those are VolksMule design decisions.

## 8. Battery enclosure philosophy

The pack remains:

- non-structural to the passenger safety cell;
- physically removable;
- mechanically protected from road/debris/intrusion;
- sealed/drained/vented according to the final cell and safety architecture;
- serviceable after removal using a documented procedure;
- connected through deliberate HV/LV/coolant interfaces.

### Material remains open

Do not prematurely freeze steel versus aluminum.

#### Steel advantages worth studying

- easy local fabrication/welding;
- high toughness;
- repair familiarity;
- low material cost;
- compatible manufacturing philosophy with steel safety cell.

#### Aluminum advantages worth studying

- lower mass;
- corrosion behavior;
- extrusion possibilities;
- thermal-spreading possibilities.

#### Tradeoffs

Final choice follows:

- mass budget;
- corrosion protection;
- structural analysis;
- cell cooling/module architecture;
- road-debris protection;
- galvanic isolation;
- local repairability;
- cost.

## 9. Front/rear cradle philosophy

Cradles exist to make the expensive/complex systems modular:

- suspension hard points;
- steering rack;
- e-axle;
- lower crash/load interface;
- selected coolant/harness attachment.

The body should define known cradle attachment planes and datums.

### Prototype baseline

Favor:

- welded steel fabrication;
- ordinary inspectable joints;
- removable cradle;
- replaceable bushings/mounts;
- physical datums for alignment;
- enough access to remove drivetrain components without cutting the body.

### Later sourcing

Once stable, ask IATF automotive fabricators for:

- DFM feedback;
- robotic-weld fixture strategy;
- corrosion coating;
- dimensional CMM plan;
- weld traceability;
- PPAP;
- production quote.

## 10. Raw material sourcing rule

Prototype structure materials should be purchased to a **written material standard**, ideally through suppliers providing mill certificates/traceability.

Alibaba may provide commodity metal, but shipping raw structural steel halfway around the world is unlikely to beat a local metal-service center once freight and traceability are counted.

So:

- local structural tube/sheet is preferred for Mule #1;
- Alibaba/China may quote specialty extrusions, castings, stampings, and production quantities;
- seller-selected 'automotive steel' is not a material specification.

## 11. Welding/process ownership

For safety-cell and cradle drawings, eventually specify at minimum:

- material grade;
- thickness;
- joint type;
- weld process;
- weld length/size where required;
- sequence where distortion matters;
- inspection criteria;
- corrosion protection;
- reference datums/tolerances.

The exact requirements follow structural engineering and test evidence.

Supplier substitution is acceptable only if the finished part still meets the drawing/process specification.

## 12. Prototype fabrication sequence

### Mule #1

1. Build/fixture safety cell locally.
2. Build front/rear cradles locally from Rev-A geometry.
3. Build battery enclosure locally or with very fast prototype fabrication if geometry is already stable.
4. Use Alibaba/Chinese CNC/sheet-metal suppliers for discrete precision pieces when cost/lead time wins.
5. Measure and update CAD after assembly.
6. Preserve every revision in the repo.

### Mule #2 / stable prototype

1. Send mature drawings to two or more automotive fabricators, including China.
2. Compare DFM/cost/weight/tolerance proposals.
3. Require material/process traceability.
4. Validate supplier-built structure against the same dimensional/structural test plan.

### Production-intent

Use APQP/PPAP-oriented suppliers and production fixtures only after architecture and test evidence justify freezing the design.

## 13. Supplier RFQ template for a stable welded structure

Do not send this until the geometry is genuinely stable.

Ask:

1. IATF 16949 certificate and scope?
2. Experience with welded automotive subframes/body structures?
3. Supported materials/thicknesses?
4. Laser/stamping/tube-bending/robotic-welding capability?
5. Prototype quantity capability before tooling?
6. Fixture design responsibility and ownership?
7. Weld process qualification?
8. Material-cert traceability?
9. CMM capability and dimensional report?
10. Corrosion coating/e-coat/powder/galvanizing options?
11. PPAP/APQP support?
12. Fatigue/test support?
13. Drawing/STEP acceptance?
14. Change-control/revision process?
15. MOQ, tooling cost, sample lead time and production lead time?
16. Who owns the tooling?
17. Can service/replacement parts be ordered years later from the same drawing?

## 14. Things Alibaba should source readily

- laser-cut tabs/gussets;
- CNC adapters;
- machined spacers;
- brackets;
- weld fixtures;
- aluminum extrusions;
- nonstructural covers;
- interior/cargo panels;
- battery-box access covers;
- cable/hose clamps;
- body trim clips;
- weatherproof enclosures;
- production stampings once volumes justify them.

## 15. Things Alibaba should not decide

- crash architecture;
- roof crush/load paths;
- restraint anchor structure;
- side-impact intrusion structure;
- battery intrusion protection;
- suspension hard points;
- steering rack position;
- cradle pickup geometry;
- battery enclosure mounting strategy;
- weld/material specification.

## Current conclusion

Alibaba/China absolutely belongs in the VolksMule structural supply chain—but **after the project knows what it wants made**.

For the first physical Mule:

> **Design the safety cell, cradles, and pack enclosure ourselves; fabricate the rapidly changing big structures locally; use Alibaba/Chinese factories aggressively for precision pieces and later stable revisions; move to automotive PPAP-oriented Chinese fabrication when the geometry stops moving.**

That preserves the enormous cost/manufacturing benefit of China without turning a distant factory into the project’s chassis engineer.
