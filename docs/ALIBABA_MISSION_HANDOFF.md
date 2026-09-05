# VolksMule Alibaba sourcing mission handoff

Updated: **2026-09-05**

This file exists so a new chat/session can resume the VolksMule Alibaba sourcing mission without reconstructing the project from conversation history.

## Active mission

Continue using the project roadmap as the organizing spine:

> **Roadmap requirement -> architecture constraint -> Alibaba search -> supplier/listing candidates -> manufacturer evidence -> interface/serviceability/regulatory check -> BUY / DONOR / ADAPT / DESIGN verdict -> save to GitHub.**

The mission is **roadmap-driven part sourcing and narrowing**, not generic Alibaba browsing and not supplier outreach.

Broad catalog archaeology is already complete enough to stop. That does **not** mean the Alibaba sourcing mission is over. Continue using Alibaba/Chinese suppliers where doing so advances an unresolved BOM item or materially improves a sourcing path.

## Current project control point — do not send the next chat backward

The project has advanced beyond the Phase-5 point captured earlier in this conversation.

The current working sourcing control document is:

- `docs/ROADMAP_SOURCING_BOM.md`

It is a **Phase-8 working BOM skeleton** and is the best current starting point for deciding what to source next.

The repo already contains later continuation screens for Phase 5, Phase 6, Phase 7 and Phase 8 work, including chassis, steering column, parking brake, CV/halfshaft/wheel-speed support, 12-V service hardware, thermal auxiliaries, brake assist, body hardware, manual seats, seals, cargo hardware, physical HVAC controls, underbody protection, side/rear glass and a simple cabin HVAC box.

### Current high-impact unresolved dependencies

The BOM currently says these matter more than finding random additional sellers:

1. first integrated vehicle packaging CAD;
2. actual front/rear suspension hard points;
3. READ2982 output/mount CAD;
4. hub spline / bolt pattern / wheel-end choice;
5. axle loads and CG;
6. brake hydraulic/thermal calculations;
7. REPT 171-Ah detailed power/compression/thermal data;
8. pack current/fault architecture;
9. exact 12-V load budget;
10. cabin HVAC-box integration geometry in dash/firewall/cowl;
11. front thermal loads, stacked-core airflow and refrigerant-cycle topology;
12. restraint/crash integration;
13. final windshield/body geometry;
14. door/hatch geometry sufficient to freeze regulators, seals and side/rear glass;
15. steering-column / clock-spring / turn-cancel geometry for exact stalk selection;
16. final FMVSS 101 telltale matrix and cluster interface/sightline;
17. underbody impact/load-path analysis;
18. cargo/roof structural loads before final anchor ratings.

A new session should use these dependencies plus the current BOM to decide which Alibaba search is actually useful next.

> **Do not restart Phase 5 merely because this chat once paused there. Read the current repo state first.**

## Critical working rule: save before moving on

Research is not complete merely because it appeared in chat.

> **No research block counts as complete until the useful findings are committed to GitHub, preferably merged into `main`.**

This rule was adopted after concern that long research runs could otherwise be lost at a chat/session boundary.

## Mission-style limitation learned in this chat

“Mission style” means: work autonomously and aggressively **during the active turn/session**, make decisions, research, write docs, open PRs, and merge sound changes without needless interruption.

It does **not** mean work continues in the background after the turn/session ends. If the chat goes quiet for hours, no work is occurring during that gap.

A future session should state this plainly rather than implying asynchronous/background execution.

## Alibaba evidence discipline

Alibaba is a discovery catalog, supplier map, OEM/ODM lineage source and possible purchasing channel. It is not the engineering authority.

Durable rules:

- seller != manufacturer;
- manufacturer engineering data outranks marketplace metadata;
- “Grade A,” “DOT approved,” CE/ECE badges, wattage/capacity claims and marketplace categories are leads, not proof;
- exact model/revision matters;
- generic ESS hardware does not become traction-automotive hardware because voltage/current/channel count fits;
- generic airbags, ABS/ESC controllers or undocumented VCUs do not become road-intent components because a listing exists;
- prefer manufacturer-direct Alibaba channels where possible;
- preserve multiple suppliers and substitution interfaces;
- documentation, serviceability and local recovery matter alongside price;
- a cheap part that creates a proprietary dependency may be more expensive than a boring part with a healthy service ecosystem.

Canonical lesson: JBD HV V3 looked numerically plausible on Alibaba, but JBD's own documentation explicitly said it does not support motive-power/EV integration. It was therefore rejected for road traction use.

## Supplier outreach rule

A complete Wave-1 RFQ packet exists in `docs/ALIBABA_RFQ_WAVE1.md`, and Issue #28 tracks the future supplier-document campaign.

However:

> **No supplier has been contacted yet, and no supplier should be contacted during the current sourcing mission.**

Wait until the roadmap-driven requirements are sufficiently consolidated so outreach can say:

- here is the vehicle envelope;
- here is the electrical/thermal/mechanical duty;
- here are the exact interfaces and documents required;
- recommend the correct configuration for those requirements.

Rawsuns CAD remains important, but the request should happen after the requirements/narrowing phase rather than interrupting it.

## Core vehicle principles learned/reinforced

### Vehicle reference

The **first-generation Honda CR-V remains the primary packaging/utility reference**, not a design to clone.

Do not drift into “make a second-generation CR-V EV.” Individual solved parts from other vehicles may still win.

### Tire philosophy

Do not reduce the preference to “215s or 225s.”

The actual preference is:

- roughly **28–34 in overall tire diameter**;
- relatively tall and narrow for its height;
- real sidewall;
- snow-cutting geometry preferred;
- local North American replacement availability required;
- Alibaba may win initial price;
- 205-series is generally disliked;
- 215/225 can be good but are not hard requirements.

Wheel diameter follows brake clearance. Study 16 in first; use 17 in if the validated brake package requires it.

### Human-machine interface

> **The computer does not own the vehicle.**

Frequent/basic controls default to knobs, switches, stalks, levers, pedals and other tactile hardware.

Loss of infotainment, a phone, app, network or cloud service must not remove ordinary vehicle operation.

### Convenience electrification

Mechanical/manual is acceptable and often preferred when cheaper/simpler/serviceable:

- manual windows are an acceptable baseline;
- mechanical/keyed locks are an acceptable baseline;
- mechanical inside door releases;
- power conveniences only if they genuinely win on total cost/packaging/serviceability.

### Start authorization

Prototype 1 baseline: **physical key**.

Study state:

- LOCK/OFF
- ACC
- RUN/READY

No proximity-fob/cloud/phone requirement.

### Traction behavior

- front-primary e-axle;
- rear axle automatic/on-demand;
- normal driving should feel simple and calm;
- rear contribution should disappear when not useful;
- manual override only if useful for recovery/service;
- **“if it slips, it grips.”**

A rear unit must tolerate full mechanically possible road speed while inactive, or have a validated disconnect/freewheel architecture.

## Key durable component findings

### Rawsuns READ2982

Public data currently supports carrying it as the conservative drive-unit envelope:

- 55/110 kW rated/peak;
- 110/270 Nm motor torque;
- 4,775/14,000 rpm;
- 11.93:1 reduction;
- ~62 kg;
- independent-suspension e-axle.

Its published speed ceiling does not create an obvious road-speed overspeed problem across the current 28–34 in tire study envelope.

Real cradle/CV/coolant geometry still requires original Rawsuns CAD/drawings; do not invent those dimensions.

### Rear e-axle

READ2624 only saves about 2 kg and its published 10,000-rpm ceiling corresponds to roughly 70–85 mph depending on tire diameter. Revision A therefore carries a second READ2982-sized rear zone as the conservative/commonality baseline unless a smaller rear unit proves a real coast-drag/efficiency/packaging advantage.

### Wheel ends / chassis

Current working BOM already carries:

- Zhejiang/Hangzhou Xingjie Gen-III hub/bearing family;
- Hubei Dongfeng JC dampers/struts;
- Meili spring-manufacturer path;
- Zhuzhou Elite P-EPS / DP-EPS family;
- Wuxi Kingfarm halfshaft/CV family;
- JinzhouABS-class active wheel-speed sensors.

Exact part numbers remain blocked by geometry, loads, splines, travel or safety-system interfaces—not by lack of supplier ecosystems.

### Battery cells

REPT remains the strongest current manufacturer-direct path.

- 150-Ah BEV cell: detailed engineering data available; 120S1P ~57.6 kWh nominal / ~344 kg raw cells.
- 171-Ah BEV cell: packaging favorite on current public data; 120S1P ~65.7 kWh / ~353 kg raw cells.
- 150-Ah pack design explicitly requires substantial cell preload/compression structure.
- do not borrow 150-Ah mechanical/current data for the 171-Ah cell without its own engineering specification.

A major Revision-A conflict was correctly exposed: a simple 120S1P 150-Ah baseline cannot automatically support the full continuous power implied by two 55-kW-rated READ2982 units. Cell power capability / parallel architecture / drivetrain continuous limits must be reconciled before final fuse/contactor sizing.

### Charging

MIDA GQEVPLC-V3.4 remains a strong EVCC lead:

- 9–28 V input, so it is compatible with the conventional 12-V architecture in principle;
- PLC / DIN 70121 / ISO 15118 family claims;
- provisional ~156.4 × 101 × 25 mm physical envelope pending supplier drawing.

Phoenix Contact provides the current high-confidence J3400 inlet benchmark:

- ~90.2 × 90.2 × 146.85 mm inlet body;
- 12-V lock;
- mechanical emergency release;
- dual DC-contact temperature sensing;
- 300-A permanent DC benchmark;
- rear-panel mounting;
- large 70-mm²-class DC conductor routing.

Final supplier remains open.

### Thermal/HVAC

Aotecar is the strongest current Chinese automotive thermal lead.

Useful Revision-A benchmark:

- integrated thermal module around 300 × 400 × 275 mm / ~11 kg;
- up to ~10 kW cooling / ~8 kW heating class.

Do not inherit an oversized luxury multi-zone cabin HVAC box. Two-seat cabin air handling should remain deliberately simple.

### BMS / BDU

BMS strategy stays two-track:

- transparent/open development platform for bench work;
- true automotive road-intent supplier for vehicle use.

Ligoo is the strongest current Chinese road-intent BMS lead; Miaoyi/Mewyeah remains a strong Alibaba-native automotive lead.

Orion is a serviceability/physical benchmark, not automatically the production answer.

Revision-A BDU/PDU is intentionally transparent and serviceable, reserving roughly a **600 × 350 × 180 mm gross zone** around separate contactors, fuse, precharge, current sensing, IMD, MSD/HVIL and branch protection rather than hiding safety plumbing inside an undocumented black box.

### Brakes / wheels

Carry approximately:

- **320 mm front rotor conflict envelope**;
- **310 mm rear rotor conflict envelope**.

Try 16-in wheel packaging first, but validated brakes get veto power.

Hydraulic friction brakes remain the stopping foundation. ABS/ESC/AEB pressure control and regen are layered around them.

### Windshield

Do not make the entire car follow a second-gen CR-V template.

Current common-glass candidates carried together:

1. second-gen CR-V family;
2. Nissan Xterra/Frontier/Pathfinder family;
3. first-gen CR-V family.

Choose by actual body packaging, sightlines, A-pillars, wiper geometry, replacement availability, crash structure and AEB-camera needs.

The windshield should remain a replaceable service part, not bespoke styling sculpture.

## Sourcing architecture that repeatedly worked

For solved hardware:

> **Buy the solved problems. Engineer the differentiator. Integrate everything. Own the result.**

Good Alibaba targets include:

- e-axles;
- cells;
- onboard power electronics;
- contactors/connectors/MSD;
- pumps/heaters/compressors;
- hubs/bearings;
- springs/dampers;
- lamps/glass/wiper mechanisms where standards and geometry fit;
- pedals/selectors;
- fabrication after geometry stabilizes.

VolksMule should retain design/control of:

- safety-cell/crash geometry;
- suspension hard points and kinematics;
- pack enclosure/integration;
- system architecture;
- traction-control logic;
- BMS/VCU authority boundaries;
- transparent HV distribution architecture;
- owner-control/service model.

## Fabrication lesson

For Mule #1, large geometry-changing weldments should stay **local** while CAD is moving.

Alibaba/Chinese manufacturing becomes more attractive for:

- precision brackets/CNC parts;
- tooling;
- stable later revisions;
- production/small-series quoting once geometry settles.

Do not pay international freight every time a prototype hard point moves a few millimeters.

## Current durable GitHub state

The repository already contains the major sourcing screens, Revision-A envelopes, roadmap continuation screens and the Phase-8 sourcing BOM. Treat GitHub as the project memory, not chat.

The earlier closeout document correctly said **broad supplier archaeology** had reached diminishing returns. That does **not** mean stop the active roadmap-driven sourcing mission.

Current rule:

> **Keep following the current sourcing BOM and roadmap. Use Alibaba where it advances a real unresolved item. Do not pivot into supplier outreach yet, and do not keep shopping when an OPEN item is actually waiting on engineering geometry/load/regulatory work.**

## New-chat startup instruction

A new chat should begin by reading, in this order:

1. `docs/ALIBABA_MISSION_HANDOFF.md` (this file)
2. `docs/ROADMAP_SOURCING_BOM.md` — current sourcing control document
3. `docs/ROADMAP.md`
4. `docs/WHAT_GOES_IN_THE_FIRST_MULE.md`
5. `docs/ALIBABA_PROCUREMENT_QUEUE.md`
6. the latest relevant detailed sourcing/continuation document for the item being worked

Then continue the **current BOM-driven Alibaba sourcing mission** in mission style.

Do not ask Pete to reconstruct this history unless a genuinely new decision requires his authority.
