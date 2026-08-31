# Alibaba brake-assist sourcing — keep the pedal hydraulic

Research current as of **2026-08-31**.

This document fills a Phase-5 gap between the previously screened friction brakes and the calibrated ABS/ESC/AEB hydraulic controller.

The target is intentionally conventional:

> **physical brake pedal → hydraulic master cylinder → vacuum-assisted booster → hydraulic circuits → friction brakes**

with ABS/ESC/AEB pressure modulation layered around that foundation.

Regeneration remains supplemental.

---

## 1. Why a vacuum booster remains attractive in an EV

An electric vehicle has no intake-manifold vacuum, but that does not require brake-by-wire.

A dedicated 12-V electric vacuum pump can evacuate a conventional pneumatic brake booster.

This preserves:

- direct physical pedal input;
- hydraulic pressure generation by the master cylinder;
- familiar booster/master-cylinder service architecture;
- ordinary brake-fluid practice;
- a degraded manual-braking path when assist is unavailable.

The pump becomes an **assist appliance**, not the owner of the brakes.

---

## 2. Regulatory architecture fit

Current FMVSS 135 defines a **brake power assist unit** as a hydraulic-brake-system device that reduces required muscular force and, if inoperative, **does not prevent the driver from braking by continued muscular force**.

The standard also includes an explicit test with the brake power assist/power source inoperative/depleted.

That is strongly aligned with the VolksMule preference:

> **Loss of electric assist may make the pedal heavier; it must not make the hydraulic foundation disappear.**

This does not by itself prove that any chosen booster/master-cylinder/pump combination complies. Vehicle-level performance still has to be engineered and tested.

Sources:

- https://www.law.cornell.edu/cfr/text/49/571.135
- current NHTSA FMVSS 135 laboratory procedure

---

## 3. OEM benchmark — HELLA UP30 / UP32 / UP5.0

HELLA currently publishes electric vacuum pumps specifically suitable for electric/hybrid brake-booster vacuum supply.

Current public data includes:

### UP30 / UP32 class

- 12-V-class operation;
- standalone vacuum generation suitable for vehicles without engine vacuum;
- approximately 13–14 V rated operation depending model;
- average current roughly <15 A UP30 / <18 A UP32 in current HELLA literature;
- maximum vacuum roughly 86% below ambient;
- roughly 4–5 L reference booster/test volumes;
- -40 to +120 °C-class operating range on current literature;
- approximately 1,200-h pump-life class;
- over one million on/off operations in current product literature;
- maintenance-free dry/self-lubricating architecture.

### UP5.0

HELLA also publishes a larger standalone pump suitable for approximately 5-L pneumatic volume and higher lifetime.

### Benchmark verdict

> **A standalone 12-V electric vacuum pump is normal production EV/hybrid brake hardware, not a conversion hack.**

Sources:

- https://www.hella.com/forvia-us/assets/documents/BI_Vacuum_Pumps_12V_2026.pdf
- https://www.hella.com/soe/en/Products/Product-detail-4957/?pid=2427

---

## 4. Strong Chinese manufacturer path — Wenzhou Zoren

**Wenzhou Zoren Auto Electric Control Co., Ltd.** publishes electric vacuum pumps specifically for brake boosters.

Current product data includes:

### UP28

- -40 to +100 °C, with limited higher-temperature exposure;
- approximately 86% maximum vacuum;
- 13-V / 4-L published evacuation timing;
- designed to support brake-booster evacuation.

### UP30 / UP32

Zoren explicitly describes UP30/UP32 as suitable for vehicles with no natural vacuum source, including:

- hybrid;
- fuel-cell;
- electric vehicles.

Current published 13-V / 4-L timing is roughly:

- UP30: 50% ambient pressure in ~3.3 s, 70% in ~6.2 s;
- UP32: 50% in ~2.4 s, 70% in ~4.4 s.

Zoren's current company material reports:

- automotive-focused manufacturing;
- large China and Thailand production bases;
- dedicated R&D/QC teams;
- global/North-American market exposure;
- automated pump production/testing capability.

### Verdict

> **STRONG CHINESE MANUFACTURER CANDIDATE for a conventional vacuum-assisted hydraulic brake architecture.**

Source:

- https://www.zoren.cn/products.asp
- https://www.zoren.cn/about.asp
- https://www.zoren.cn/technology.asp

---

## 5. Alibaba-accessible brake-system path — Hipsen

Alibaba currently lists electric brake-vacuum-pump products through **Quzhou Hipsen Vehicle Parts Co., Ltd.**

Hipsen's own current manufacturer material is more useful than the listing alone:

- brake-system specialist;
- vacuum and hydraulic boosters;
- master cylinders;
- electric vacuum pumps;
- proportioning valves;
- calipers/discs and related brake hardware;
- OEM/custom manufacturing;
- ISO 9001 and IATF 16949 certification claims;
- North-American export activity.

This makes Hipsen potentially useful not merely as a pump seller but as a source for a **matched conventional booster + master cylinder + pump hardware family**.

### Caveat

That still does **not** make Hipsen the ABS/ESC calibration provider automatically.

Foundation-brake hydraulic hardware and vehicle stability-control calibration remain separate engineering responsibilities unless a supplier proves coherent integration capability.

### Verdict

> **CARRY Hipsen as the strongest currently visible Alibaba-accessible brake-assist hardware family.**

Sources:

- https://www.alibaba.com/brake-vacuum-pump-suppliers.html
- https://hbs-parts.com/who-we-are/

---

## 6. Marketplace warning — UP28/UP30 clone labels

Alibaba has many products described as:

- UP28;
- UP30;
- UP32;
- UP50.

Those labels often indicate **form/function interchange aspirations**, not necessarily HELLA manufacture or HELLA-equivalent endurance.

Some listings are associated with suppliers whose primary business is not automotive braking.

Therefore:

> **Do not buy a brake-assist pump merely because the housing and model label resemble a HELLA UP30.**

For road-intent use require an automotive manufacturer with traceable testing and quality systems.

---

## 7. Vacuum-system architecture

A basic Revision-A study should include:

1. electric vacuum pump;
2. vacuum reservoir if required by booster/pump duty-cycle analysis;
3. check valve;
4. pressure/vacuum sensor;
5. conventional pneumatic brake booster;
6. tandem hydraulic master cylinder;
7. split hydraulic circuits;
8. ABS/ESC/AEB HCU downstream/integrated as engineered;
9. local brake warning/telltale logic.

### Control principle

Pump control may be simple:

- monitor booster/reservoir vacuum;
- start below a validated threshold;
- stop after sufficient vacuum is restored;
- monitor excessive runtime / inability to reach vacuum;
- warn the driver on assist-system fault.

The control computer does not generate the physical brake command.

---

## 8. Pump failure behavior

Bench/vehicle test must include:

- pump electrically disconnected;
- blown fuse;
- failed relay/output driver;
- vacuum leak;
- check valve failed;
- reservoir leak;
- vacuum sensor failure;
- pump running but insufficient vacuum;
- repeated hard brake applications depleting reserve;
- 12-V brownout;
- high-temperature pump derating/failure.

Desired result:

> **Assist degrades predictably, warning is obvious, and sufficient mechanical/hydraulic braking remains available to satisfy the applicable failed-assist performance requirement.**

---

## 9. Booster / master-cylinder selection

Do not select booster diameter or master-cylinder bore by donor convenience.

Need:

- pedal ratio;
- target pedal travel/force;
- front/rear caliper piston areas;
- hydraulic circuit architecture;
- ABS/ESC HCU displacement requirements;
- desired line pressure;
- booster assist curve;
- available firewall/pedal-box geometry;
- vacuum level and reserve volume;
- GVWR/axle-load/braking calculations.

### Preferred sourcing strategy

1. Find a **common conventional passenger-SUV booster/master-cylinder family** whose hydraulic capacity matches the calculated system.
2. Use a known electric vacuum pump to provide assist.
3. Preserve locally available seals/master-cylinder/booster replacements where practical.
4. Only commission a custom booster/master cylinder if calculations prove necessary.

### Verdict

> **DONOR / BUY / ADAPT proven conventional booster and tandem master cylinder. Exact family waits on brake calculations.**

---

## 10. Vacuum reservoir

A reservoir may reduce pump cycling and preserve assist for successive applications, but it is not automatically required.

Size based on:

- booster chamber volume;
- desired assisted applications after pump loss;
- pump evacuation rate;
- vacuum switch thresholds;
- packaging;
- cold/altitude operation.

A simple reservoir can be a commodity automotive part if required.

Do not build complexity around a reservoir before the assist model exists.

---

## 11. Electrical load consequence

A standalone brake vacuum pump is another reason the 12-V DC/DC capacity should not be frozen at 1.5 kW without a load study.

Current HELLA-type pump classes can draw roughly **10–18 A** while operating.

That is only one transient load among:

- EPS;
- ABS/ESC pump;
- radiator/thermal fans;
- coolant pumps;
- cabin blower;
- wipers;
- lighting;
- contactors/controllers.

### Consequence

> **Keep the 3-kW-class 14-V DC/DC benchmark alive until the real worst-case LV transient budget is complete.**

---

## 12. Current sourcing shortlist

| Function | First path | Alternate | Status | Blocker |
|---|---|---|---|---|
| Electric vacuum pump | **Wenzhou Zoren UP30/UP32-class** | HELLA UP30/32/5.0 benchmark | **CARRY** | booster volume/duty/noise/package |
| Alibaba brake-assist supplier | **Hipsen** | other IATF pump manufacturer | **CARRY** | exact matched pump/booster/master data |
| Vacuum booster | common passenger-SUV unit / Hipsen family | local donor/OE | **OPEN** | pedal force/hydraulic sizing/firewall |
| Tandem master cylinder | matched common unit | local donor/OE | **OPEN** | caliper/HCU displacement + line-pressure math |
| Vacuum sensor | automotive pressure sensor | HELLA/common donor | **OPEN** | threshold/control strategy |
| Check valve/hoses | common automotive vacuum hardware | local | **LOCAL-FIRST** | port sizes/layout |
| Reservoir | common automotive if required | local/custom simple tank | **OPEN** | reserve/duty-cycle calculation |

---

## 13. Architecture decision from this pass

For Revision A, carry this as the **preferred first-study brake-assist architecture**:

> **conventional hydraulic tandem master cylinder + pneumatic booster + independent 12-V electric vacuum pump + ABS/ESC/AEB HCU**

Why it earns first study:

- physical/hydraulic brake path remains obvious;
- loss of assist does not inherently eliminate braking;
- EV-compatible electric vacuum pumps are mature;
- parts are widely available;
- no central computer becomes the sole brake actuator;
- easy bench fault injection;
- simpler owner understanding/service.

This is not yet a final brake-system freeze.

If later vehicle-level braking/AEB requirements prove a modern e-booster materially superior, it can compete on evidence.

The burden of proof is on the more complex architecture.

---

## 14. Reject for Prototype 1 unless evidence changes

- brake-by-wire-only foundation;
- generic no-name UP30 clone with no endurance evidence;
- proprietary e-booster requiring locked OEM pairing simply to restore braking assist;
- master-cylinder/booster choice made before caliper/hydraulic calculations;
- assuming regen reduces friction-brake sizing requirement;
- hiding failed vacuum assist from the driver.

---

## 15. Next engineering input

This sourcing block is complete enough until brake calculations exist.

Next required engineering work is:

1. provisional front/rear axle loads and CG height;
2. tire effective radius / friction assumption;
3. target deceleration/stopping performance;
4. front/rear brake torque requirement;
5. caliper piston-area study;
6. master-cylinder bore/pedal-ratio study;
7. booster assist/vacuum-volume requirement;
8. pump duty-cycle/reserve sizing.

Then a common donor booster/master-cylinder family can be screened against exact requirements rather than guessed.