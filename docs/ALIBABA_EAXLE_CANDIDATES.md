# Alibaba e-axle candidate screen

Research date: **2026-08-31**

This document is a focused follow-on to [ALIBABA_SOURCING.md](ALIBABA_SOURCING.md). It screens currently discoverable integrated electric drive units against the existing VolksMule Prototype 1 architecture.

Nothing here is a selected production part.

The job at this stage is to answer a narrower question:

> **Do credible, compact, roughly 400-V drive-unit families exist that could support a front-primary / automatic rear-assist VolksMule without forcing the vehicle architecture to contort around them?**

The answer after this first screen is **yes — but the rear-axle coast/overspeed problem becomes an explicit design gate.**

---

## VolksMule drivetrain screen

A serious candidate should support, or at minimum not obstruct:

- roughly 400-V-class pack architecture;
- compact passenger/light-MPV packaging;
- independent suspension/CV half-shafts rather than a heavy live axle;
- front-primary normal driving;
- automatic rear contribution only when useful;
- hydraulic/friction braking independent of regen availability;
- locally controllable torque and regen requests;
- documented CAN or other vehicle-control interface;
- known failure and degraded modes;
- cooling data and thermal derating;
- normal replacement without cloud/vendor authorization;
- enough documentation to design interchangeable mechanical/electrical interfaces;
- vehicle road speed without motor overspeed when an axle is mechanically coupled.

Cheapness is not a qualification.

---

# Candidate 1 — Rawsuns READ2982

**Status: HIGH-PRIORITY CONDITIONAL CANDIDATE**

Manufacturer reference:

- https://www.rawsuns.com/ev-transaxle/electric-axle/

Alibaba discovery example:

- https://www.alibaba.com/search/page?SearchScene=imageTextSearch&productId=1601005375645

## Manufacturer-published parameters

| Parameter | READ2982 |
|---|---:|
| Suspension type | Independent |
| Wheel-end max output torque | 2,982 Nm |
| Total assembly weight | 62 kg |
| Motor rated / peak power | 55 / 110 kW |
| Motor rated / peak torque | 110 / 270 Nm |
| Motor rated / peak speed | 4,775 / 14,000 rpm |
| Reduction | single-speed 11.93:1 |

Alibaba currently surfaces Rawsuns conversion/e-axle listings describing the 55/110-kW family for SUV/sedan/CV-axle use, with prototype-scale MOQ in at least some listings. Marketplace voltage and power descriptions are not fully consistent between listings, so the manufacturer engineering package must govern.

## Approximate road-speed check

Using a **28-inch nominal tire diameter** only as a screening assumption:

- motor maximum speed: 14,000 rpm;
- output speed after 11.93:1 reduction: ~1,174 rpm;
- theoretical road speed: **~97.8 mph**.

This is not a vehicle top-speed claim. Real allowable continuous speed depends on tire loaded radius, motor mechanical limits, bearing limits, inverter voltage, field weakening, thermal state, and supplier-defined overspeed margins.

It does show that READ2982 gearing is not immediately incompatible with ordinary U.S. highway speeds.

## Why it is interesting

- 62 kg is reasonable enough to warrant serious packaging work.
- 55 kW continuous / 110 kW peak is in a plausible range for a compact utility EV primary axle.
- integrated differential/reduction removes a large amount of custom drivetrain engineering.
- independent-suspension output fits the Mule architecture far better than the many live commercial axles on the marketplace.
- Rawsuns also offers controllers, VCU, BMS, OBC/DC-DC/PDU and other EV-system hardware, so there is at least a possibility of obtaining coherent interface documentation rather than reverse-engineering an isolated OEM takeout.

## Open gates

Before this becomes a shortlist part, obtain:

1. exact supported HV operating window for the specific READ2982 configuration;
2. exact inverter/controller model supplied with it;
3. CAN command/feedback documentation or DBC;
4. torque-command and regen-command semantics;
5. neutral/coast behavior;
6. **unpowered drag torque versus shaft speed**;
7. continuous mechanically permissible motor speed while coasting;
8. whether a mechanical disconnect option exists;
9. CAD, mounting points, half-shaft spline and plunge requirements;
10. differential type and lubrication/service procedure;
11. coolant flow/temperature requirements;
12. continuous and peak thermal-derating curves;
13. inverter current limits versus DC-link voltage;
14. resolver/position-sensor details;
15. EMC/environmental qualification evidence;
16. failure modes and safe-state behavior;
17. local commissioning, firmware and diagnostic tooling;
18. replacement-unit pairing/calibration procedure;
19. sample MOQ/pricing and production-support horizon.

---

# Candidate 2 — Rawsuns READ2624

**Status: CONDITIONAL REAR-AXLE CANDIDATE — ROAD-SPEED BLOCKER IDENTIFIED**

Manufacturer reference:

- https://www.rawsuns.com/ev-transaxle/electric-axle/

## Manufacturer-published parameters

| Parameter | READ2624 |
|---|---:|
| Suspension type | Independent |
| Wheel-end max output torque | 2,624 Nm |
| Total assembly weight | 60 kg |
| Motor rated / peak power | 30 / 60 kW |
| Motor rated / peak torque | 90 / 220 Nm |
| Motor rated / peak speed | 3,183 / 10,000 rpm |
| Reduction | single-speed 11.93:1 |

## Approximate road-speed check

Using the same **28-inch nominal tire** assumption:

- motor maximum speed: 10,000 rpm;
- output speed after 11.93:1 reduction: ~838 rpm;
- theoretical road speed: **~69.8 mph**.

That produces our first meaningful rejection condition.

If READ2624 remains mechanically coupled to the rear wheels, a VolksMule capable of substantially more than ~70 mph would overspeed the motor relative to the published maximum-speed number.

Therefore READ2624 is **not an acceptable rear-assist choice yet**, even though its 30/60-kW output looks attractive for that role.

It survives only if one of the following is demonstrated:

- Rawsuns provides a mechanically validated disconnect/freewheel solution;
- a taller final-drive ratio is available;
- the published 10,000-rpm value is not the mechanically allowable coast/overspeed ceiling and Rawsuns supplies a higher documented limit;
- the vehicle's final tire/gearing/top-speed envelope proves compatible;
- or a different smaller rear unit is selected.

This is exactly the sort of issue that the sourcing screen is supposed to expose before packaging becomes commitment.

---

# Candidate 3 — Shenzhen Sumcont 60/120-kW 3-in-1 family

**Status: HIGH-PRIORITY DISCOVERY CANDIDATE**

Alibaba currently surfaces Sumcont 3-in-1 PMSM powertrain products around **60 kW rated / 120 kW peak**, including liquid-cooled configurations and high-voltage ranges spanning approximately the 400-V class. Prototype-scale quantities appear to be offered in some listings.

Discovery references:

- https://www.alibaba.com/countrysearch/CN/electric-car-conversion-kit.html
- https://www.alibaba.com/premium/60kw_electric_motor.html
- https://autopart.alibaba.com/product/ev-truck-kit-conversion

The supplier also markets a broader EV-system portfolio including motor controllers, VCU, PDU, BMS, battery packs, OBC/DC-DC, compressors and harnessing.

## Why it remains interesting

A supplier capable of supporting **motor + inverter + reducer + VCU + HV auxiliaries as a documented system** may be much more useful to VolksMule than a cheap motor alone.

The present public listings do not expose enough mechanical data to rank the Sumcont unit against READ2982.

## Information required immediately

- assembly weight;
- exact dimensions and CAD;
- gearbox ratio;
- maximum motor and output speed;
- differential/half-shaft geometry;
- supported DC voltage window;
- continuous/peak current;
- CAN/DBC availability;
- coast drag;
- disconnect/freewheel options;
- thermal map;
- automotive qualification;
- local diagnostics/firmware access;
- whether front and rear variants can be supplied with different ratios/power while preserving a common control interface.

That last point could be especially valuable for VolksMule.

---

# Candidates screened downward

## Heavy commercial live e-axles

**Status: REJECT for Prototype 1 architecture**

Alibaba contains many excellent-looking 60–250+ kW commercial e-axles, but assemblies designed as truck live axles are generally the wrong architecture for the compact independently suspended Mule.

They remain useful as supplier/technology references, not packaging candidates.

## Brogen 60/120-kW commercial e-axle families

**Status: LOW PRIORITY for Prototype 1**

Alibaba currently surfaces Brogen 350-V-class 60/120-kW e-axle systems. The visible offerings skew toward commercial trucks, higher MOQs, and heavier-duty architecture. Nothing found yet makes them superior to the passenger/CV-oriented Rawsuns and Sumcont leads.

Discovery reference:

- https://autopart.alibaba.com/product/electric-drive-shaft

## 100–180+ kW B/C-class sedan drive units

**Status: WATCHLIST**

Alibaba also surfaces integrated drive units intended for B/C-class sedans, including EDEV products. These prove that genuinely passenger-car-oriented hardware is present on the marketplace, but several are 700-V-class or substantially more powerful than Prototype 1 appears to require.

They should remain in the search pool in case their mass, efficiency, documentation, or supplier support is unusually strong.

---

# Architecture options exposed by this sweep

## Option A — identical READ2982-class units front and rear

**Advantages**

- common drive-unit hardware;
- common spares;
- same speed capability;
- potentially simpler controls and diagnostics;
- front unit alone provides enough peak power for ordinary driving.

**Disadvantages / unknowns**

- ~124 kg combined assembly mass before mounts/coolant/harnesses;
- 220 kW combined peak capability is probably more than the Mule needs;
- two PMSM units may impose unnecessary rear-axle drag when the rear unit is unpowered;
- cost and cooling capacity may be larger than necessary.

This option lives or dies on **rear-unit coast loss** and controllability.

## Option B — READ2982-class front + smaller rear assist unit

**Advantages**

- matches the intended front-primary philosophy;
- potentially lower mass/cost/rear drag;
- rear unit only needs useful traction contribution, not full vehicle performance.

**Problem discovered**

A smaller unit cannot merely have less power. It must also tolerate full vehicle road speed while mechanically coupled.

READ2624 demonstrates the trap: it looks ideal by power rating but its published 10,000-rpm limit corresponds to only about 70 mph with the assumed tire.

Therefore the rear-unit specification must include **road-speed/freewheel/disconnect behavior as a first-class requirement**.

## Option C — supplier-engineered matched front/rear family

Ask Rawsuns, Sumcont, and similar integrators whether they can provide:

- a primary front unit;
- a lower-power/high-speed or disconnectable rear unit;
- shared CAN semantics and diagnostics;
- compatible DC bus/cooling architecture;
- documented torque arbitration;
- local service tools.

This may produce the cleanest orchestration solution if supplier lock-in can be controlled with documented interfaces and alternates.

---

# New drivetrain requirement created by this sweep

Add this concept to all future rear-e-axle screening:

> **The secondary e-axle must tolerate the vehicle's maximum mechanically possible road speed while inactive, or provide a validated disconnect/freewheel mechanism that prevents motor overspeed and unacceptable parasitic loss.**

Required evidence includes:

- maximum continuous coast rpm;
- absolute mechanical overspeed limit and duration;
- drag torque versus rpm when inverter torque command is zero;
- induced back-EMF/DC-bus behavior while coasting;
- inverter behavior with HV bus unavailable;
- disconnect engagement/disengagement envelope if fitted;
- failure behavior if the disconnect cannot change state.

This requirement matters even more for a permanent-magnet rear motor because an unpowered mechanically coupled PMSM still rotates its magnetic field and cannot be treated as a frictionless lump.

---

# Supplier RFQ — e-axle-specific questions

For Rawsuns, Sumcont, and the next serious e-axle supplier, request the following before further selection:

1. Exact model number and revision of motor, inverter, reduction gear and differential.
2. 3D STEP CAD and 2D controlled drawing.
3. Total wet and dry mass.
4. Supported DC-link operating/min/max voltage.
5. Rated and peak power/torque with duration and coolant conditions.
6. Maximum continuous drive rpm, continuous coast rpm, and absolute mechanical overspeed rpm/time.
7. Gear ratio and differential type.
8. Half-shaft spline, plunge, angle and joint requirements.
9. Motor/inverter efficiency map.
10. Zero-torque coast drag map versus speed and temperature.
11. Back-EMF/DC-link behavior during unpowered coast.
12. Whether a mechanical disconnect/freewheel option exists.
13. Coolant type, flow, pressure drop, inlet-temperature limits and derating map.
14. CAN/CAN-FD DBC or complete protocol documentation.
15. Torque request, regen request, direction/neutral, enable and fault-reset behavior.
16. Resolver/position-sensor type and diagnostic coverage.
17. Diagnostic trouble-code list and offline service software.
18. Bootloader/reflash procedure and whether it requires a cloud account.
19. Functional-safety concept and safe-state behavior.
20. EMC, vibration, shock, ingress, temperature and corrosion qualification reports.
21. IATF 16949 or equivalent factory quality-system evidence.
22. Expected production lifetime and replacement-part commitment.
23. Prototype MOQ, sample price and lead time.
24. Whether the supplier will support a matched higher-power front + lower-power high-speed/disconnectable rear configuration using common controls.

---

# Current ranking

| Candidate family | Mechanical fit | Voltage fit | Power fit | Documentation visible | Rear-assist suitability | Current verdict |
|---|---|---|---|---|---|---|
| Rawsuns READ2982 | Strong | Promising / verify exact variant | Strong primary | Good basic published data | Unknown coast loss | **Investigate first** |
| Rawsuns READ2624 | Strong | Promising / verify | Attractive rear power | Good basic published data | **Speed blocker unless resolved** | **Conditional** |
| Sumcont 60/120 kW 3-in-1 | Unknown pending CAD | Strong-looking 400-V-class family | Strong | Marketplace/system-level only | Unknown | **Investigate first tier** |
| Brogen commercial 60/120 kW | Commercial-biased | Plausible | More than adequate | Moderate | Unknown | **Low priority** |
| Heavy live-axle products | Wrong | Varies | Varies | Varies | Wrong architecture | **Reject P1** |

---

# Immediate conclusion

The Alibaba drivetrain search has crossed an important threshold: **we have found plausible integrated drive families rather than merely proving that electric motors exist.**

Rawsuns READ2982 is the strongest first mechanical candidate because its published mass, independent-suspension architecture, gearing, speed and power are all within a credible Prototype 1 envelope.

READ2624 also taught us something more valuable than a cheap candidate would have: **a lower-power rear e-axle must still survive full vehicle road speed.** That is now an explicit VolksMule screening requirement.

No purchase and no architecture freeze should happen until coast loss, overspeed behavior, CAN control, thermal data and mechanical CAD are obtained from the supplier.
