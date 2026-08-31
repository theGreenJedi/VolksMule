# Revision-A brake-corner envelope

This file turns the current brake/ABS/ESC sourcing work into a physical wheel-corner packaging envelope for Prototype 1.

It does **not** freeze a rotor, caliper, hub, knuckle, pad or ABS/ESC supplier. It exists so the suspension/wheel CAD has a realistic brake volume to clear while the final axle loads and supplier calibration remain open.

> **Friction brakes are the safety system. Regen helps.**

---

## 1. Vehicle context

Current whole-vehicle working targets remain approximately:

- curb weight: <= 4,200 lb, preferably below 4,000 lb;
- GVWR: around 5,500 lb or less;
- useful payload: about 1,000 lb or more;
- front-primary drivetrain;
- four-wheel hydraulic discs;
- ABS / ESC / AEB-capable hydraulic control;
- regenerative braking coordinated around, not instead of, the friction brakes.

Exact axle loads and CG height are not frozen.

Therefore this document carries a **conservative physical brake envelope**, not a final thermal/stopping calculation.

---

## 2. Current mass-market comparison band

Current compact-SUV examples provide a useful sanity check.

### 2025 Toyota RAV4

Public specifications show approximately:

- front rotor: **12.0 in / ~305 mm**;
- rear rotor: **~11.0–11.1 in / ~280–282 mm**;
- common 17-in wheel family.

### 2025 Honda CR-V

Current non-hybrid public specifications are around:

- front rotor: **~310–312 mm**;
- rear rotor: **~310 mm** on current generation service data.

Current hybrid brake-service listings show an approximately:

- **320 mm front** rotor;
- **310 mm rear** rotor.

These are not donor selections. They show that 300–320-mm front brakes are normal on modern compact utility vehicles in roughly our mass/mission neighborhood.

---

## 3. Revision-A rotor conflict envelopes

Until the first axle-load/brake-energy model is complete, carry:

### Front

- rotor outside diameter conflict envelope: **up to 320 mm**;
- nominal rotor thickness placeholder: **up to ~30 mm**;
- caliper radial/axial envelope beyond the rotor: supplier-dependent, reserve generously;
- vented rotor is the default study assumption.

### Rear

- rotor outside diameter conflict envelope: **up to 310 mm**;
- nominal rotor thickness placeholder: **up to ~25 mm**;
- mechanical parking-brake provision must be accommodated;
- solid versus vented remains open until energy/thermal duty is modeled.

These are **packaging maxima**, not final minimum required sizes.

---

## 4. Wheel-size consequence

VolksMule still prefers the **smallest common wheel that safely clears the final brake package**.

The current tire philosophy favors tall, relatively narrow tires with useful sidewall rather than large fashion wheels.

### Revision-A rule

1. **Study 16-in wheels first.**
2. Put the full 320-mm front rotor + candidate caliper envelope inside the actual wheel barrel CAD.
3. Check spoke/caliper face clearance, not only nominal rim diameter.
4. If a common 16-in wheel cannot clear the brake system with proper manufacturing/service margin, move to a common **17-in wheel**.
5. Do **not** shrink a validated brake below what the stopping/thermal model requires merely to preserve a preferred wheel diameter.

A 17-in wheel with tall/narrow tire geometry is still fully compatible with the VolksMule tire philosophy.

---

## 5. Provisional static axle-load study

For packaging calculations only, Revision A may use a provisional static GVWR split to establish order of magnitude.

At **5,500 lb GVWR**:

### 55/45 front/rear study split

- front axle: ~3,025 lb;
- rear axle: ~2,475 lb;
- static front corner: ~1,513 lb;
- static rear corner: ~1,238 lb.

This is **not a target weight distribution**.

It is a placeholder for early bearing/brake/tire load checks until the integrated CAD produces real axle loads.

Braking dynamic load transfer will increase front-axle demand substantially and must be calculated from:

- actual wheelbase;
- loaded CG height;
- loaded mass;
- deceleration;
- tire-road friction;
- suspension/anti-dive geometry.

Do not size front brakes from static axle load alone.

---

## 6. Final brake sizing inputs

Before rotor/caliper selection is frozen, calculate at least:

- FMVSS 135 stopping requirements and applicable test conditions;
- maximum loaded vehicle mass;
- front/rear axle loads;
- CG height and wheelbase;
- dynamic brake-force distribution;
- tire effective radius;
- maximum hydraulic line pressure;
- master-cylinder/pedal ratio/booster or pressure-generation characteristics;
- caliper piston area;
- effective rotor radius;
- pad coefficient range hot/cold/wet;
- rotor heat capacity and repeated-stop thermal load;
- mountain descent / regen-unavailable case;
- full-battery / cold-battery case where regen is limited;
- towing load if towing becomes a validated requirement;
- AEB/ESC pressure-generation requirements.

The design case includes **zero regenerative braking**.

---

## 7. Brake-by-wire boundary remains unchanged

Prototype 1 retains:

- hydraulic friction brakes as the foundation;
- real brake-pedal input;
- ABS/ESC hydraulic pressure modulation;
- AEB-capable supplier-calibrated pressure generation as required;
- regen blending around the friction foundation.

Prototype 1 does **not** default to a brake-by-wire-only architecture.

Electronic pressure generation may be used as an assist/control layer only if the final architecture preserves safe, understandable friction-brake behavior under faults.

---

## 8. Caliper and rotor sourcing rule

Calipers/rotors/pads are commodity enough that Volkswagen-style supplier lock-in would be self-inflicted.

Prefer:

- common rotor dimensions or families;
- multiple replacement brands;
- ordinary pad shapes with broad aftermarket support where practical;
- serviceable slide pins/pistons/boots;
- normal bleed screws;
- no proprietary electronic pad authentication;
- no unique rotor/pad solely for styling.

Alibaba can help source initial hardware and manufacturing alternatives, but the final wear items should be purchasable through ordinary North-American replacement channels whenever practical.

---

## 9. Hub / knuckle interface

Brake selection must converge with:

- Gen-III bolt-on hub candidate;
- ABS encoder / wheel-speed sensor;
- wheel bolt pattern;
- e-axle/CV spline;
- steering knuckle geometry;
- scrub radius;
- tire offset;
- suspension ball-joint/strut locations.

Do not independently select a beautiful caliper and then redesign the entire upright around it.

The whole corner is one interface problem.

---

## 10. Parking brake

The current simplicity preference remains:

> **mechanical cable-operated friction parking brake unless packaging/testing proves another answer materially better.**

Revision-A rear brake packaging must therefore reserve either:

- rear caliper with mechanical parking-brake actuation; or
- separate small drum-in-hat / mechanical parking-brake mechanism if that produces the better whole corner.

Electronic parking-brake motors are not forbidden, but they do not get selected merely because modern donor brakes use them.

---

## 11. ABS / ESC integration

The hydraulic controller remains a vehicle-calibrated safety system rather than a generic marketplace pump.

Current serious supplier paths remain APG/Zhejiang Asia-Pacific and WBTL/Bethel-class suppliers.

Final wheel-corner design must provide:

- four reliable wheel-speed signals;
- steering-angle input;
- yaw/lateral-acceleration sensing;
- brake-pressure information as required;
- consistent tire effective rolling radius assumptions;
- predictable friction/regen coordination.

A donor ABS module may help bench development. Road-intent ESC requires vehicle-specific calibration.

---

## 12. Revision-A physical boxes to carry

### Front wheel corner

Carry a no-go cylinder/disc envelope representing:

- **320-mm maximum rotor OD study**;
- **~30-mm rotor thickness allowance**;
- candidate caliper body extending radially/axially beyond the rotor;
- bleed-screw and hose-service access;
- full wheel-barrel/spoke clearance.

### Rear wheel corner

Carry:

- **310-mm maximum rotor OD study**;
- **~25-mm thickness allowance**;
- mechanical parking-brake mechanism/service path;
- caliper/hose access.

Exact caliper dimensions remain blocked on the eventual candidate family.

---

## 13. Current conclusion

The brake corner is now sufficiently bounded for first CAD conflict work.

The current rule is:

> **Carry ~320-mm front / ~310-mm rear rotor conflict envelopes, attempt a common 16-in wheel first, and allow the validated brake package to force 17 in if necessary.**

This does not select a rotor.

The next engineering step is the first integrated vehicle mass/CG/axle-load estimate, followed by brake-force and repeated-stop thermal calculations.

Status:

> **BRAKE-CORNER PACKAGING BLOCKER REDUCED / FINAL ROTOR-CALIPER SELECTION WAITS FOR AXLE LOADS + THERMAL MODEL + SUPPLIER CALIBRATION PATH**

---

## 14. Sources reviewed

Public research current as of **2026-08-31**:

- current 2025 Toyota RAV4 brake specifications;
- current 2025 Honda CR-V brake specifications and replacement rotor data;
- existing VolksMule `ALIBABA_BRAKES_ESC.md` and suspension-corner sourcing work.
