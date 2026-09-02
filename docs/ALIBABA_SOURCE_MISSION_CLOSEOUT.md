# Alibaba sourcing — public-data mission closeout and engineering handoff

Updated: **2026-09-01**

This file defines the boundary between useful sourcing research and the engineering work that must now make the candidate systems coexist inside Prototype 1.

> **Broad Alibaba catalog archaeology is complete. Roadmap-driven public-data sourcing is now complete to the level the current vehicle requirements allow. Exact parts remain intentionally open where geometry, loads, regulatory integration or supplier-original engineering data are still missing.**

That distinction matters.

An exact part number remaining open does **not** mean the sourcing mission failed. In many rows, selecting an SKU before the vehicle has the required geometry or load data would be false precision.

---

## 1. What is closed

The following activity is now closed unless a new engineering problem creates a real sourcing question:

- generic keyword wandering;
- proving that e-axles, BMSs, OBCs, dampers, hubs, springs, connectors, HVAC hardware, switches, clusters, lamps, seats, seals and other solved component classes exist;
- collecting endless equivalent marketplace listings after a credible supplier/manufacturer path is established;
- selecting a component merely because its face dimensions or price look convenient;
- treating seller marketing as engineering evidence;
- reopening settled architecture because Alibaba contains a more complicated gadget.

The supplier ecosystem and sourcing architecture are documented across the `ALIBABA_*` research files and consolidated in:

- [`ROADMAP_SOURCING_BOM.md`](ROADMAP_SOURCING_BOM.md)

---

## 2. Late roadmap gaps now closed at the sourcing-architecture level

After the original broad-discovery audit, four useful public-data gaps remained. They are now resolved.

### Simple cabin HVAC air box

Current direction:

- compact single-zone architecture;
- BEU-404-class package as a useful prototype benchmark;
- Hubei Meibiao as a stronger road-intent/custom HVAC engineering benchmark;
- physical fan / temperature / mode control retained;
- positive defrost/defog required;
- exact box waits for cowl/dashboard/windshield geometry.

Detailed screen:

- [`ALIBABA_CABIN_HVAC_BOX.md`](ALIBABA_CABIN_HVAC_BOX.md)

### Front thermal stack

Current direction:

- separately replaceable coolant radiator, refrigerant outdoor exchanger, fan/shroud and stone protection;
- HBS as an Alibaba-accessible automotive heat-exchanger manufacturing path;
- Hubei Meibiao as the stronger custom/road-intent engineering benchmark;
- ordinary A/C condenser duty is **not** assumed to prove reversible heat-pump outdoor-exchanger duty;
- exact cores wait for the thermal model, refrigerant cycle and front package.

Detailed screen:

- [`ALIBABA_FRONT_THERMAL_STACK.md`](ALIBABA_FRONT_THERMAL_STACK.md)

### Physical steering-column stalks

Current direction:

- physical dual stalks;
- left = turn + high/low/flash;
- right = wiper + washer;
- dedicated separate hazard button;
- discrete/passive low-current command signals preferred;
- documented CAN/LIN only if it earns its complexity;
- ChuangJia/ChonKia first existing supplier-family study, with Jinhao/Wanchao manufacturer benchmarks;
- exact switch waits for column/cancel/clock-spring and harness geometry.

Detailed screen:

- [`ALIBABA_DRIVER_STALKS_SWITCHGEAR.md`](ALIBABA_DRIVER_STALKS_SWITCHGEAR.md)

### Independent instrument cluster

Current direction:

- conventional driver binnacle;
- modest central information display rather than a dashboard-wide consumer computer;
- dedicated/persistent critical telltales;
- documented CAN data plane;
- no infotainment dependency;
- no propulsion/brake/steering authority merely because the cluster displays those systems;
- Wuhan Green Electronic Instruments as the first Alibaba-accessible EV/heavy-vehicle manufacturer study;
- E408-style mixed architecture as a useful benchmark;
- exact model waits for the FMVSS 101 telltale matrix, sight lines and ECU interface definitions.

Detailed screen:

- [`ALIBABA_SIMPLE_INSTRUMENT_CLUSTER.md`](ALIBABA_SIMPLE_INSTRUMENT_CLUSTER.md)

---

## 3. Supplier outreach remains deferred

Supplier outreach is **still intentionally deferred**.

The project now knows the right kind of component and credible supplier path for essentially every solved subsystem, but several high-impact suppliers still need questions that depend on internal vehicle decisions.

Opening conversations before those questions are mature would create noise, duplicate requests and supplier-led architecture.

The rule remains:

> **Research first. Define what VolksMule wants. Contact suppliers later with one coherent requirement package.**

The prepared RFQ material remains useful as a staging area, not an instruction to send messages immediately.

---

## 4. What remains genuinely open — and why Alibaba cannot solve it

The remaining high-impact unknowns are now dominated by engineering dependencies:

1. first integrated vehicle packaging CAD;
2. actual front/rear suspension hard points;
3. READ2982 output / mount / installation CAD;
4. hub spline / bolt pattern / wheel-end choice;
5. axle loads and CG;
6. brake hydraulic and thermal calculations;
7. REPT 171-Ah detailed power / compression / thermal data;
8. pack current and fault architecture;
9. exact 12-V worst-case load budget;
10. cabin HVAC integration geometry;
11. front thermal loads, stacked-core airflow and final refrigerant topology;
12. restraint / crash integration;
13. windshield / body / wiper geometry;
14. door and hatch geometry;
15. steering-column / clock-spring / turn-cancel geometry;
16. final FMVSS 101 telltale matrix and cluster sight-line definition;
17. underbody impact / load-path analysis;
18. cargo / roof structural load definition;
19. final VCU I/O, safety state machines and message ownership.

Searching another hundred Alibaba listings cannot answer those questions.

---

## 5. What the next internal mission should produce before supplier outreach

### A. Revision-A interface freeze

Build the first coherent internal interface package for:

- vehicle envelope and hard-point coordinate system;
- occupant H-points / eye points;
- front/rear e-axle envelopes;
- wheel-end / brake / tire envelope;
- steering rack / column envelope;
- battery voltage/current/thermal envelope;
- J3400 inlet and charging architecture;
- front thermal stack and cabin HVAC zones;
- windshield / cowl / wiper envelope;
- seat / restraint package;
- 12-V load budget;
- CAN ownership / major message families;
- physical driver-control layout.

### B. First integrated packaging CAD

Use the real candidate families already found to expose conflicts:

- occupants vs battery;
- crash structure vs steering;
- e-axles vs suspension travel;
- tires vs steering angle / body;
- battery vs ground clearance;
- front thermal stack vs crash/service space;
- HVAC box vs cowl / windshield / passenger space;
- cluster / wheel / driver sight lines;
- restraints vs pillars / roof / doors;
- cargo/sleeping platform vs rear structure.

The purpose is conflict discovery, not styling perfection.

### C. Engineering question packets

Only after those internal interfaces mature, convert the existing supplier question lists into compact, non-duplicative packets for the suppliers whose original data is actually needed.

---

## 6. Eventual supplier-document campaign — staged, not yet sent

When the internal package is mature, the highest-impact document requests are likely to include:

- **Rawsuns** — READ2982 installation CAD, mounting, spline/output, cooling, CAN and speed/coast data;
- **REPT BATTERO** — 171-Ah / 150-Ah BEV cell engineering, compression, power and thermal data;
- **Sumcont** — alternate e-drive engineering package;
- **Dilong** — OBC/DC-DC/PDU topology, CAN and electrical windows;
- **MIDA** — J3400 EVCC protocol / interoperability package;
- **Ligoo / Miaoyi** — BMS channel, CAN, safety and local-service documentation;
- **Yonggui / Chilye / Hongfa** — exact HV interconnect / MSD / contactor data after fault-current sizing;
- **Zhuzhou Elite** — EPS/rack/column data after steering geometry exists;
- **Aotecar / Meibiao / HBS-class thermal suppliers** — exact thermal maps/CAD only after loads and cycle topology exist;
- **restraint / ESC safety-system suppliers** — only with a coherent vehicle package suitable for system engineering.

This list is a future sequencing note, not outreach authorization.

---

## 7. Sample purchases remain gated

Do not buy large/high-cost components because research has identified them.

A sample earns purchase only when:

1. its role is defined;
2. the interface is understood enough to use it;
3. missing supplier documents are either available or unnecessary for the intended test;
4. it does not prematurely lock adjacent geometry;
5. there is a concrete bench or vehicle test planned.

Commodity items can still be purchased locally or through Alibaba when the BOM reaches an exact need, but that is procurement—not another sourcing-discovery mission.

---

## 8. Architecture safeguards remain unchanged

Still rejected as generic marketplace answers:

- safety-cell architecture;
- mixed restraint systems;
- generic airbags;
- ABS/ESC without vehicle calibration support;
- ESS BMS hardware pretending to be automotive merely because voltage matches;
- undocumented central vehicle computers;
- structural-pack dependency;
- cloud-required basic operation;
- proprietary multifunction modules whose failure removes unrelated basic functions;
- components whose convenient dimensions damage whole-vehicle geometry.

And the computer still does not own the vehicle.

---

## 9. Definition of sourcing completion

A roadmap sourcing block is complete when it has:

1. a clear requirement;
2. one or more credible supplier/manufacturer paths;
3. manufacturer evidence beyond marketplace copy where available;
4. known missing data;
5. local replacement / interchange implications;
6. a BUY / DONOR / ADAPT / DESIGN verdict;
7. a purchase gate;
8. durable documentation in GitHub.

Exact SKUs may remain intentionally open until loads, hard points, voltage/current windows or regulatory requirements exist.

That is not incomplete work. It is disciplined sourcing.

---

# Current verdict

> **BROAD ALIBABA DISCOVERY: COMPLETE**
>
> **ROADMAP PUBLIC-DATA SOURCING: COMPLETE TO CURRENT ENGINEERING MATURITY**
>
> **EXACT PART SELECTION: OPEN WHERE REAL ENGINEERING DATA IS MISSING**
>
> **SUPPLIER OUTREACH: DEFERRED**
>
> **NEXT INTERNAL PHASE: REVISION-A INTERFACE FREEZE + FIRST INTEGRATED PACKAGING CAD**

Alibaba has done the job it can do without allowing suppliers or marketplace inventory to design the vehicle for us.

The next progress comes from making the already-found systems coexist inside one coherent Mule.