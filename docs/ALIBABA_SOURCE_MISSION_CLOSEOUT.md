# Alibaba sourcing — broad-discovery closeout and roadmap continuation

Updated: **2026-08-31**

This file marks a narrower boundary than its original title implied.

> **Broad Alibaba catalog archaeology is complete. Roadmap-driven part sourcing is not.**

The first research pass proved that credible Alibaba / Chinese-supplier ecosystems exist for essentially every solved Prototype 1 subsystem and identified where generic marketplace hardware is the wrong answer.

That means we should stop asking vague questions such as:

> "Does Alibaba have EV suspension parts?"

But we should **continue walking the VolksMule roadmap subsystem by subsystem**, narrowing candidate hardware, supplier families, interchange opportunities, local-replacement paths, prototype pricing and purchase gates wherever public data can still improve the eventual BOM.

---

## 1. What is closed

The following activity is closed unless a new problem appears:

- generic keyword wandering;
- proving that e-axles, BMSs, OBCs, dampers, hubs, springs, connectors, etc. exist;
- collecting endless equivalent marketplace listings after the supplier class is already established;
- treating seller marketing as engineering evidence;
- chasing a part merely because it is inexpensive.

The broad supplier ecosystem is already documented in the detailed `ALIBABA_*` sourcing files.

---

## 2. What remains active

The active Alibaba mission is now:

> **Roadmap requirement → architecture constraint → candidate part/supplier family → manufacturer evidence → interchange/local-service check → BUY / DONOR / ADAPT / DESIGN verdict.**

This work can continue without supplier outreach.

Examples include:

- narrowing Gen-III hub/bearing families;
- comparing dampers and spring manufacturers against future corner-load/travel requirements;
- identifying proven rotor/caliper/donor families that fit the brake envelope;
- mapping CV/halfshaft suppliers once e-axle output geometry is known;
- identifying ordinary 12-V relays, fuse blocks, switches, washer systems, horns and service hardware when the BOM reaches them;
- tracking low-MOQ Alibaba sample paths and comparing them with local North-American replacement availability;
- identifying which commodity hardware should intentionally be bought locally even if Alibaba is cheaper.

The current Phase-5 continuation is documented in:

- [`ALIBABA_PHASE5_CHASSIS_CANDIDATES.md`](ALIBABA_PHASE5_CHASSIS_CANDIDATES.md)

---

## 3. Supplier outreach remains deferred

No supplier outreach is required for this continuation.

The prepared Wave-1 RFQ package remains stored in:

- [`ALIBABA_RFQ_WAVE1.md`](ALIBABA_RFQ_WAVE1.md)

Outreach should happen only when the project has extracted enough public information and internal requirements to ask focused questions rather than broad requests.

Until then:

> **Research first. Consolidate what VolksMule wants. Contact suppliers later.**

---

## 4. Architecture safeguards remain unchanged

Continuing Alibaba sourcing does **not** reopen settled project principles.

Still rejected as generic marketplace purchases:

- safety-cell architecture;
- mixed restraint systems;
- generic airbags;
- ABS/ESC without vehicle calibration support;
- ESS BMS hardware pretending to be automotive merely because voltage matches;
- undocumented central vehicle computers;
- structural-pack dependency;
- cloud-required basic operation;
- components whose fit damages whole-vehicle geometry.

And the computer still does not own the vehicle.

---

## 5. Definition of progress

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
> **ROADMAP-DRIVEN ALIBABA SOURCING: ACTIVE**
>
> **SUPPLIER OUTREACH: DEFERRED UNTIL REQUIREMENTS ARE MATURE**

The project should continue down the roadmap and squeeze useful sourcing knowledge out of public Alibaba/manufacturer data before opening supplier conversations.