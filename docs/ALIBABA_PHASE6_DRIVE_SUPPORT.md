# Alibaba Phase-6 drive-support candidates — CVs, halfshafts and wheel-speed sensing

Research current as of **2026-08-31**.

This document continues the roadmap-driven Alibaba sourcing mission into:

> **Phase 6 — Make it move and grip.**

The e-axles themselves were screened earlier. This pass covers the ordinary but critical hardware around them:

- CV joints;
- halfshafts / drive shafts;
- boots / clamps / axle nuts;
- wheel-speed sensing;
- service/replacement strategy;
- interfaces that must remain open so the car does not become captive to one e-axle supplier.

The rule is:

> **The e-axle may provide torque; VolksMule must own the wheel-side interface contract.**

---

## 1. Halfshaft / CV architecture

Prototype 1 uses independent suspension with two independent e-axles.

Therefore each driven corner needs a halfshaft system capable of:

- full suspension jounce/rebound;
- steering angle at the front axle;
- maximum traction torque;
- regenerative torque reversal;
- plunge for suspension/structure movement;
- acceptable operating angle at full travel;
- acceptable boot temperature and articulation life;
- replaceable outer/inner joints, boots, clamps and axle nuts where practical.

The shaft system must not be treated as an afterthought between a chosen motor and a chosen hub.

---

# 2. Current strongest Alibaba CV/halfshaft path — Wuxi Kingfarm

Alibaba directly surfaces **Wuxi Kingfarm Corporation Limited** for:

- CV joints;
- complete CV axles;
- drive shafts;
- passenger-car applications;
- ATV/UTV applications;
- existing Geely/Lifan and other vehicle programs.

Current non-Alibaba manufacturer-directory evidence describes Kingfarm as:

- manufacturer/factory + trading operation;
- ISO 9001 / **IATF 16949** management-system certification;
- more than 15 years in CV/shock-absorber supply;
- engineers with 20+ years experience;
- customization capability;
- exports to the U.S., Japan, Australia, Europe and other markets.

Current trade-data sources also show **2026 U.S.-bound CV-joint/CV-axle shipments** from Wuxi Kingfarm, which is useful evidence that this is an active supplier rather than a dormant catalog page.

### Verdict

> **STRONG YELLOW / first custom-halfshaft supplier candidate once READ2982 output geometry is known.**

The company appears capable of making the sort of conventional steel CV axle VolksMule needs.

But no shaft dimensions should be invented before the drive-unit and hub interfaces are real.

Sources:

- https://www.alibaba.com/axle-drive-shaft-suppliers.html
- https://www.alibaba.com/geely-cv-joint-factory.html
- https://www.alibaba.com/cv-joint-axle-suppliers.html
- https://www.made-in-china.com/showroom/aqurious/

---

# 3. Exact halfshaft information needed before selection

For each front/rear shaft, the eventual interface matrix must contain:

## E-axle side

- output spline major/minor diameter;
- spline count/profile;
- seal land;
- retention method / circlip geometry;
- nut/bolt retention if applicable;
- allowable plunge into the drive unit;
- differential/output centerline position;
- maximum output torque;
- maximum output speed.

## Wheel side

- chosen hub spline geometry;
- axle-nut thread and torque;
- bearing preload interaction;
- seal land;
- outer CV center relative to steering axis;
- ABS encoder/sensor clearance.

## Shaft body

- installed/compressed length;
- maximum/minimum articulation length;
- bar diameter/material/heat treatment;
- torsional strength;
- buckling/bending margin;
- fatigue life;
- balance requirements at wheel speed;
- maximum continuous rpm;
- corrosion protection.

## Joint behavior

- outer CV maximum operating angle;
- inner CV maximum operating angle;
- plunge travel;
- continuous torque at angle;
- peak torque duration;
- efficiency/heat at high angle;
- grease specification;
- boot material and temperature range.

These are design inputs, not sales questions.

---

# 4. Existing vehicle CV hardware versus custom shafts

## Preferred order

1. **Reuse a common existing outer CV / hub-spline family** if the chosen wheel hub and knuckle permit it.
2. Reuse an existing inner joint if it matches the e-axle output.
3. If only one end matches, use a custom center bar / hybrid shaft with proven joint families.
4. Commission a completely unique CV joint only as a last resort.

This matters because CV joints and boots are wear/service items.

A custom shaft bar is acceptable.

A custom outer joint that becomes unavailable in ten years is much less attractive.

### VolksMule preference

> **Custom length is acceptable. Custom service ecosystem is not.**

---

# 5. Alibaba CV market notes

Alibaba currently exposes a deep passenger-car CV market with examples for:

- BYD EVs;
- Chevrolet Volt;
- Toyota RAV4/Highlander/Camry;
- Honda/CR-V families;
- Nissan/Hyundai/Kia;
- Chinese NEVs.

Current public pricing for ordinary joints/axles ranges broadly from single-digit-dollar joint kits to tens of dollars for complete common shafts, with low MOQs on some existing-fitment products.

This price depth confirms the hardware is commodity-scale.

Price is **not** the selection criterion yet.

The value of Alibaba here is:

- supplier discovery;
- joint-family cross-reference;
- low-cost prototype spares once fit is known;
- later custom-length manufacture using known joint ends.

---

# 6. Wheel-speed sensing

Automatic rear traction, ABS, ESC and AEB all depend on high-integrity wheel-speed information.

The sensor system should remain a normal automotive wheel-speed architecture rather than being synthesized from GPS, motor rpm or a consumer computer.

## Strong current specialist — Ruian Jinzhou / JinzhouABS

Current manufacturer material for **Ruian Jinzhou Auto Parts Co., Ltd. / JinzhouABS** reports:

- dedicated ABS wheel-speed-sensor manufacturing;
- over 3,000 sensor applications;
- approximately **2.2 million pieces/year** capacity;
- more than 100 employees;
- export/OE/new-energy-vehicle work;
- **IATF 16949:2016** certification claim;
- European/American and Japanese-vehicle product coverage.

This is a stronger source profile than a generic electronics reseller.

Manufacturer source:

- https://www.jinzhouabs.com/

## Alibaba-accessible alternatives

Alibaba also surfaces current IATF-claimed custom sensor manufacturers such as **Shenzhen Boundless Sensor Technology Co., Ltd.** with wheel-speed-sensor products and customization capability.

That gives us a potential Alibaba transaction path even if Jinzhou itself is not the easiest storefront route.

### Current verdict

> **BUY a normal automotive active wheel-speed sensor / encoded hub system. Do not create a bespoke wheel-speed sensor.**

---

# 7. Sensor/hub interface rule

The cleanest wheel-end architecture is likely:

- Gen-III hub/bearing with integrated magnetic encoder;
- fixed active wheel-speed sensor in the knuckle;
- sealed automotive connector;
- direct signal to ABS/ESC HCU;
- VCU may consume a documented copy/network message but does not replace the HCU's direct safety input.

Final selection must verify:

- active/passive sensor type;
- supply voltage/current;
- signal protocol/waveform;
- pole count;
- direction detection if required;
- air gap;
- temperature range;
- EMC robustness;
- cable routing through full steering/jounce travel;
- replaceability without hub destruction where possible.

---

# 8. Traction-control input boundary

VolksMule's automatic rear-drive behavior should use the same real chassis signals that normal stability systems use.

Useful inputs include:

- four wheel speeds;
- accelerator request;
- steering angle;
- yaw/lateral acceleration from the ESC architecture;
- front/rear e-axle actual torque/speed;
- brake state;
- vehicle speed estimate;
- thermal/availability state of each drive unit.

The rear axle does not need a driver-selected routine mode.

The normal behavior remains:

> **Front does the ordinary work. If useful slip/traction demand appears, rear contribution arrives automatically and smoothly.**

The driver should not have to think about it.

---

# 9. Mechanical support pieces

Once drive-unit CAD is known, the following become ordinary sourcing/fabrication items:

- e-axle isolation mounts;
- brackets;
- shaft shields;
- CV boot heat shields where required;
- axle nuts/washers;
- retaining rings;
- shaft support bearing if asymmetric shaft length requires one;
- sealed sensor connectors;
- harness clips;
- service guards.

Alibaba is appropriate for most of these once drawings/specifications exist.

E-axle mounts themselves should be selected by load/NVH requirements, not generic "EV motor mount" descriptions.

---

# 10. Current Phase-6 sourcing shortlist

| Function | Current first path | Verdict | Blocker |
|---|---|---|---|
| Complete halfshaft/CV | Wuxi Kingfarm | BUY / ADAPT | READ2982 output + hub spline/geometry |
| Outer CV joint | common local high-volume application first | BUY | hub/knuckle choice |
| Inner CV joint | existing e-axle-compatible family if possible | BUY / ADAPT | Rawsuns output drawing |
| Custom shaft bar/length | Kingfarm or equivalent IATF driveline manufacturer | BUY to drawing | installed length + torque |
| Wheel-speed sensor | JinzhouABS-class automotive sensor | BUY | selected hub encoder/signal type |
| Alibaba sensor alternate | Shenzhen Boundless-class IATF supplier | BUY / alternate | exact encoder interface |
| Mount brackets/guards | drawing-based Alibaba/local fabrication | DESIGN + BUY | e-axle CAD and cradle geometry |

---

# 11. Purchase gates

## Halfshaft sample gate

Do not buy or commission custom shafts until:

- e-axle output spline is documented;
- hub spline is selected;
- nominal installed lengths are known;
- jounce/rebound/steering travel is modeled;
- maximum torque is defined;
- operating angles are checked.

## Wheel-speed sensor gate

Do not freeze sensor SKU until:

- hub encoder is selected;
- ABS/ESC controller signal requirements are known;
- mounting air gap and knuckle geometry are modeled.

Commodity replacement sensors may be bought cheaply later for bench testing.

---

# 12. What this pass tells us

The driveline support ecosystem is healthy.

VolksMule does **not** need Rawsuns to become the permanent supplier of shafts, wheel hubs, sensors or wheel-end service parts merely because Rawsuns supplies an e-axle.

That is an important sovereignty win.

The preferred architecture is increasingly clear:

> **e-axle output interface → independently sourceable CV/halfshaft → common hub/bearing → ordinary wheel/brake ecosystem.**

If we document those boundaries well, a future e-axle replacement does not require redesigning the whole corner.

---

# 13. Next roadmap sourcing move

Continue Phase 6/7 public sourcing with:

1. **traction-drive support and sensors complete enough for now**;
2. move to the remaining **12-V commodity/service hardware** that can be narrowed without vehicle CAD: fuse/relay centers, physical switch families, horn, washer pump/reservoir components, sealed connectors and service disconnect/telltale hardware;
3. then build a first **roadmap sourcing BOM skeleton** listing every subsystem, preferred supplier path, alternate/local path, and exact-data blocker.

No supplier outreach is required for this pass.