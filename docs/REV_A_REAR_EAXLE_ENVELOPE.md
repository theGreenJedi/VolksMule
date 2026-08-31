# Revision-A rear e-axle envelope

This file narrows the **secondary/rear traction unit** for VolksMule Prototype 1.

The rear axle is not supposed to turn the vehicle into permanent performance AWD. Its job is simple:

> **Normal driving is front-primary. When traction or a validated control need appears: if it slips, it grips.**

The correct rear drive therefore optimizes for:

- low drag while inactive;
- full-road-speed survivability while back-driven;
- rapid, predictable torque contribution;
- simple service/spares;
- adequate but not gratuitous power;
- documented control and diagnostics.

---

## 1. The two current Rawsuns CV candidates

Current Rawsuns manufacturer data list only two independent-suspension READ CV e-axles in this family:

| Item | READ2624 | READ2982 |
|---|---:|---:|
| Assembly mass | 60 kg | 62 kg |
| Motor rated / peak power | 30 / 60 kW | 55 / 110 kW |
| Motor rated / peak torque | 90 / 220 N·m | 110 / 270 N·m |
| Motor rated / peak speed | 3,183 / 10,000 rpm | 4,775 / 14,000 rpm |
| Reduction | 11.93:1 | 11.93:1 |
| Wheel-end max output torque | 2,624 N·m | 2,982 N·m |
| Suspension/output architecture | independent / CV | independent / CV |

At first glance READ2624 looks like the natural rear-assist choice because it is less powerful.

The speed arithmetic changes that conclusion.

---

## 2. READ2624 road-speed constraint

At 10,000 motor rpm and 11.93:1 reduction, READ2624 wheel speed is roughly 838 rpm.

Ideal no-slip vehicle speed across the current VolksMule tire envelope is approximately:

| Tire diameter | READ2624 speed at 10,000 rpm |
|---:|---:|
| 28 in | **69.8 mph** |
| 29 in | **72.3 mph** |
| 30 in | **74.8 mph** |
| 31 in | **77.3 mph** |
| 32 in | **79.8 mph** |
| 33 in | **82.3 mph** |
| 34 in | **84.8 mph** |

This is only simple geometric speed at the supplier's published peak motor rpm.

It does not include:

- overspeed margin;
- sustained back-drive limits;
- downhill tire growth/slip;
- bearing/lube thermal limits;
- inverter-off back-EMF behavior.

### Consequence

A permanently coupled READ2624 rear axle would make the vehicle's safe road-speed envelope uncomfortably dependent on tire diameter and undocumented overspeed tolerance.

That is especially unattractive because VolksMule intentionally keeps the exact 28–34-in tire choice open.

---

## 3. READ2624 does not buy much mass

READ2624 is published at **60 kg**.

READ2982 is **62 kg**.

The smaller rear unit therefore saves only **~2 kg** at the published assembly level.

That is not enough mass benefit, by itself, to justify:

- lower road-speed margin;
- another unique motor/inverter calibration;
- potentially different spare parts;
- a separate service specification;
- a rear-only overspeed constraint.

READ2624 can still win if Rawsuns proves a major advantage in:

- coast drag;
- efficiency at rear-assist loads;
- price;
- physical size;
- thermal load;
- built-in disconnect behavior.

None of those advantages is established by the current public table.

---

## 4. Symmetric READ2982 becomes the provisional packaging baseline

For Revision-A CAD, the cleanest current assumption is:

- **front: READ2982-class provisional zone**;
- **rear: second READ2982-class provisional zone**.

This is **not a component freeze**.

It is a conservative packaging baseline because the known READ2982 speed/ratio envelope already clears normal road-speed needs across the whole current tire study, while its mass is only 2 kg above READ2624.

### Benefits of symmetric mechanical hardware

Potential benefits include:

- common spare drive unit;
- common reduction/differential family;
- common seals/bearings/service approach;
- common inverter/control protocol if supplier package is identical;
- fewer unique diagnostic tools/firmware families;
- same published 14,000-rpm speed margin front and rear;
- ability to cap rear torque in VCU software instead of selecting a weaker mechanical unit solely to enforce behavior.

### Rear torque behavior remains asymmetric by control

Identical hardware does **not** imply 50/50 permanent AWD.

The VCU can define the rear unit as:

- normally zero-torque / lowest-loss state;
- pre-armed for rapid traction response;
- torque-capped below its hardware maximum during ordinary slip recovery;
- available for temporary thermal/load sharing when justified;
- unavailable/disabled gracefully if rear system faults.

The hardware can be symmetric while the vehicle behavior remains front-primary.

---

## 5. The real unresolved problem is idle drag

A secondary permanent-magnet drive unit can create losses while being back-driven even when commanded torque is zero.

Need measured data for READ2982 and READ2624:

- drag torque versus road/motor rpm;
- drag versus oil/coolant temperature;
- inverter-on zero-torque vs inverter-disabled drag;
- back-EMF voltage at maximum road speed;
- bearing/seal/churning loss;
- required rotor-field/control strategy during coast;
- energy loss over representative highway cycle.

Without those data, we cannot claim that an always-coupled rear READ2982 is efficient enough.

---

## 6. Disconnect remains a legitimate option, not a routine driver control

A mechanical disconnect on the **secondary** e-axle is technically attractive if it materially reduces highway losses.

Schaeffler's current secondary-e-axle intermediate-shaft disconnect product is useful architecture evidence:

- specifically intended to decouple a secondary e-axle when it is not needed;
- advertised energy-consumption reduction up to roughly 6% in applicable systems;
- scalable torque capacity up to 1,800 N·m;
- shift time roughly 50–150 ms;
- electro-mechanical actuation;
- designed for AWD secondary-drive applications.

### VolksMule interpretation

A disconnect is acceptable if engineering proves it worthwhile.

It would be **automatic**, controlled by the VCU, and invisible during normal driving.

The driver does not get a daily "2WD / AWD" chores switch.

Manual control, if any, would exist only for:

- recovery;
- service;
- fault handling.

---

## 7. Disconnect selection gate

Add a disconnect only if whole-vehicle testing/modeling shows a meaningful benefit after accounting for:

- disconnect mass;
- actuator/controller complexity;
- extra bearings/splines/seals;
- engagement shock/NVH;
- lubrication;
- serviceability;
- failure modes;
- cost;
- packaging;
- engagement time during a slip event.

A 1–2% theoretical efficiency gain may not justify another failure-prone mechanism.

A robust ~5–6% real highway-energy improvement could.

The test decides.

---

## 8. Questions for Rawsuns — rear use specifically

For both READ2624 and READ2982 ask:

1. continuous permissible back-driven rpm;
2. transient overspeed rpm and duration;
3. drag torque curve from 0 to max rpm at multiple temperatures;
4. back-EMF with inverter disabled;
5. recommended inverter state while mechanically back-driven;
6. whether motor field weakening/zero-torque control is required during coast;
7. oil churning/bearing loss data;
8. whether a factory mechanical disconnect variant exists;
9. whether a differential/output-side disconnect can be integrated;
10. exact unit dimensions and whether READ2624 is physically smaller than READ2982;
11. exact price delta in prototype and volume quantities;
12. efficiency map in the low-torque rear-assist region;
13. expected service life while predominantly back-driven rather than powered.

For symmetric READ2982 use also ask:

- can identical hardware be installed front and rear with only mounting/shaft changes?;
- are rotation direction and lubrication valid in the intended rear orientation?;
- can the same controller firmware support front and rear addresses/torque limits?;
- can one spare drive unit service either axle after configuration?

---

## 9. Alternative suppliers remain open

The fact that Rawsuns has only two public CV families does not lock VolksMule to them.

A better rear unit may be:

- lower power than READ2982;
- high-speed enough for all tire options;
- physically smaller/lighter;
- induction or another motor type with lower passive drag;
- equipped with a documented disconnect;
- integrated motor/inverter/reducer with better efficiency and open CAN controls.

Current Chinese marketplace searches continue to surface many "rear axle" products that are actually bus/truck/UTV systems. Those are not acceptable substitutes merely because the page says rear axle.

The rear candidate must remain passenger-vehicle / independent-suspension shaped.

---

## 10. Battery-power interaction

Two READ2982 units imply a large **hardware** peak-power capability.

That does not mean the pack must support 220 kW continuously or that the VCU should ever request it.

The current detailed REPT 150-Ah 120S1P baseline indicates only about **57.6 kW nominal continuous cell power** from its dated 150-A continuous limit, with much higher short-duration peak capability.

Therefore:

- front/rear torque limits must obey BMS pack-current authority;
- rear engagement must not create an uncontrolled current step;
- peak combined motor ratings are not a vehicle power specification;
- final cell choice and power map may materially affect how much rear torque is useful.

The computer may coordinate this. It does not get to ignore electrical reality.

---

## 11. Revision-A packaging decision

For now:

### Front

**Carry READ2982 provisional envelope.**

### Rear

**Carry a second READ2982-sized provisional envelope as the conservative/common-hardware baseline.**

Also preserve an alternate smaller rear-unit envelope study once credible high-speed/low-drag candidates emerge.

### READ2624

Status:

> **DO NOT REJECT, BUT DO NOT BASELINE AS PERMANENTLY COUPLED REAR WITHOUT BACK-DRIVE DATA.**

Reason:

- only ~2 kg lighter than READ2982;
- published speed ceiling creates ~70–85 mph geometric limit depending on tire;
- no public evidence yet of enough drag/cost/package advantage to compensate.

### Disconnect

Status:

> **OPTIONAL ARCHITECTURE TOOL — AUTOMATIC ONLY — ADD ONLY IF MEASURED ENERGY SAVINGS EARN THE COMPLEXITY.**

---

## 12. Current mission status

The rear-drive uncertainty has narrowed from:

> "find some smaller rear motor"

to:

> **"model an identical READ2982-sized rear unit first; require coast/back-drive data; only switch to READ2624 or a disconnect/smaller unit if it produces a measurable whole-vehicle advantage."**

That is enough for Revision-A packaging to proceed without prematurely selecting a rear axle.

---

## 13. Sources reviewed

Research current as of **2026-08-31**:

- Rawsuns current READ-series CV e-axle table for READ2624 and READ2982;
- Rawsuns current passenger-vehicle/under-2.5-ton system material;
- Schaeffler current intermediate-shaft integrated disconnect architecture for secondary e-axle efficiency context;
- surrounding current Chinese passenger/rear e-axle searches used to reject bus/truck/UTV-shaped candidates from the immediate baseline.

The front READ2982 details remain in [`REV_A_READ2982_ENVELOPE.md`](REV_A_READ2982_ENVELOPE.md).
