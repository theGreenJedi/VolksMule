# VolksMule Alibaba sourcing mission handoff

Updated: **2026-09-05**

This file exists so a new chat/session can resume the VolksMule Alibaba sourcing mission without reconstructing the project from conversation history.

## Active mission

Continue using the project roadmap as the organizing spine:

> **Roadmap requirement -> architecture constraint -> Alibaba search -> supplier/listing candidates -> manufacturer evidence -> interface/serviceability/regulatory check -> BUY / DONOR / ADAPT / DESIGN verdict -> save to GitHub.**

The current emphasis is **deeper part-family narrowing for the roadmap**, not supplier outreach.

Do **not** contact Rawsuns or other suppliers yet. Outreach is intentionally deferred until VolksMule knows the complete set of requirements/questions it wants to send in a disciplined wave.

The broad discovery pass proved that credible supplier ecosystems exist. The current mission is to keep following the roadmap and narrow actual hardware families and interfaces where useful, especially Phase 5 onward.

## Exact resume point

Resume at **ROADMAP Phase 5 — Make it roll, steer, and stop**.

Current focus:

- actual Alibaba-accessible Gen-III hub/bearing candidates;
- dampers / springs / control-arm / knuckle supplier families;
- practical steering/EPS hardware families while preserving a mechanical steering path;
- brake rotors/calipers/hydraulic hardware that fit the current corner envelope;
- keep ABS/ESC as a supplier-calibrated vehicle system rather than a generic marketplace pump.

Then continue sequentially into Phase 6 and Phase 7 rather than inventing unrelated sourcing categories.

## Critical working rule: save before moving on

Research is not considered complete merely because it appeared in chat.

> **No research block counts as complete until the useful findings are committed to GitHub, preferably merged into `main`.**

This rule was adopted after concern that long research runs could otherwise be lost with a chat/session boundary.

## Mission-style limitation learned in this chat

“Mission style” means: work autonomously and aggressively **during the active turn/session**, make decisions, research, write docs, open PRs, and merge sound changes without needless interruption.

It does **not** mean work continues in the background after the turn/session ends. If the chat goes quiet for hours, no work is occurring during that gap.

A future session should state this plainly rather than implying asynchronous/background execution.

## Alibaba evidence discipline

Alibaba is a discovery catalog, supplier map, OEM/ODM lineage source, and possible purchasing channel. It is not the engineering authority.

Durable rules:

- seller != manufacturer;
- manufacturer engineering data outranks marketplace metadata;
- “Grade A,” “DOT approved,” CE/ECE badges, wattage/capacity claims, and marketing categories are leads, not proof;
- exact model/revision matters;
- generic ESS hardware does not become traction-automotive hardware because voltage/current/channel count fits;
- generic airbags, ABS/ESC controllers, or undocumented VCUs do not become road-intent components because a listing exists;
- prefer manufacturer-direct Alibaba channels where possible;
- preserve multiple suppliers and substitution interfaces;
- documentation/serviceability/local recovery matter alongside price.

The JBD HV V3 BMS was a canonical example: Alibaba numbers looked plausible, but JBD's own documentation explicitly said it does not support motive-power/EV integration, so it was rejected for road traction use.

## Supplier outreach rule

A complete Wave-1 RFQ packet already exists in `docs/ALIBABA_RFQ_WAVE1.md`, and Issue #28 tracks the future supplier-document campaign.

However:

> **No supplier has been contacted yet, and no supplier should be contacted during the current sourcing mission.**

Wait until the roadmap-driven requirements are sufficiently consolidated so outreach can say:

- here is the vehicle envelope;
- here is the electrical/thermal/mechanical duty;
- here are the exact interfaces and documents required;
- recommend the correct configuration for those requirements.

Rawsuns CAD remains important, but the request should happen after this requirements/narrowing phase rather than interrupting it.

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
- local North American replacement availability is required;
- Alibaba may win initial price;
- 205-series is generally disliked;
- 215/225 can be good but are not hard requirements.

The wheel diameter follows brake clearance. Study 16 in first; use 17 in if the validated brake package requires it.

### Human-machine interface

> **The computer does not own the vehicle.**

Frequent/basic controls default to knobs, switches, stalks, levers, pedals, and other tactile hardware.

Loss of infotainment, a phone, app, network, or cloud service must not remove ordinary vehicle operation.

### Convenience electrification

Mechanical/manual is acceptable and often preferred when cheaper/simpler/serviceable:

- manual windows are acceptable baseline;
- mechanical/keyed locks are acceptable baseline;
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
- “if it slips, it grips.”

A rear unit must tolerate full mechanically possible road speed while inactive, or have a validated disconnect/freewheel architecture.

## Key Revision-A findings already durable

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

READ2624 only saves about 2 kg and its published 10,000-rpm ceiling corresponds to roughly 70–85 mph depending on tire diameter. Therefore Revision A carries a second READ2982-sized rear zone as the conservative/commonality baseline unless a smaller rear unit proves a real coast-drag/efficiency/packaging advantage.

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

Major sourcing and Revision-A research through the earlier mission is already in `main`, including:

- Alibaba sourcing ledger and coverage audit;
- procurement queue;
- Wave-1 RFQ packet;
- e-axles;
- OBC/DC-DC/PDU;
- J3400 charging;
- BMS;
- cells;
- HV safety plumbing;
- thermal/HVAC;
- steering/EPS;
- brakes/ABS/ESC;
- suspension;
- visibility;
- seats/restraints;
- wheels/tires/recovery;
- body controls/doors;
- driver commands/instrumentation;
- low-voltage/CAN/diagnostics;
- safety automation;
- Revision-A interface, windshield, e-axle, rear-e-axle, EVCC, steering, occupant, cell, BMS, J3400 inlet, thermal, brake-corner and BDU/PDU envelopes.

The old closeout document correctly said **broad supplier archaeology** had reached diminishing returns. That does **not** mean stop the user's active roadmap-driven sourcing mission. The current instruction supersedes that interpretation:

> **Keep following the roadmap and narrow the real candidate hardware through Alibaba where doing so advances the vehicle. Do not pivot into supplier outreach yet.**

## New-chat startup instruction

A new chat should begin by reading:

1. `docs/ALIBABA_MISSION_HANDOFF.md` (this file)
2. `docs/ROADMAP.md`
3. `docs/WHAT_GOES_IN_THE_FIRST_MULE.md`
4. `docs/ALIBABA_PROCUREMENT_QUEUE.md`
5. the relevant detailed sourcing document for the subsystem currently being worked.

Then resume **Phase 5 roll/steer/stop candidate narrowing** in mission style.

Do not ask Pete to reconstruct this history unless a genuinely new decision requires his authority.
