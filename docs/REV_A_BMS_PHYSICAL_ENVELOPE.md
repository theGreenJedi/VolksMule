# Revision-A automotive BMS physical envelope

This file turns the current BMS sourcing work into a physical packaging rule for Prototype 1.

It does **not** select a final BMS supplier. It prevents the battery enclosure from being designed as if battery management electronics have zero size, zero service clearance, or zero thermal/EMC needs.

> **The BMS protects the battery. It does not own the vehicle, owner service rights, or the pack enclosure geometry.**

---

## 1. Current road-intent supplier direction

The current sourcing screen keeps two automotive supplier paths alive:

- **Ligoo** — strongest road-intent lead on current evidence, with dedicated automotive Power-BMS families including 600-V, 800-V and 1000-V platforms;
- **Suzhou Miaoyi / Mewyeah** — strongest Alibaba-native motive-power BMS lead, with vehicle-specific series counts including SUV/truck products.

Ligoo's current public material confirms a real automotive business rather than an ESS product relabeled for vehicles. It publishes passenger-car/commercial-vehicle BMS families, IATF-class automotive quality positioning, and a global installed base exceeding 7.5 million units as of June 2026.

Independent 2026 Chinese installation data also places Ligoo among the largest third-party BMS suppliers in the passenger-vehicle market.

Exact mechanical drawings for the specific 400-V-class systems we would quote are **not yet public enough to freeze packaging**.

Therefore Revision A needs a conservative physical reserve.

---

## 2. Centralized benchmark: Orion BMS 2

Orion is not currently the preferred production supplier, but it is unusually useful as an **open/documented mechanical benchmark**.

For its 120–180-cell enclosure, Orion publishes an outline drawing approximately:

| Item | Public benchmark |
|---|---:|
| Length | **394.2 mm** |
| Width | **158.8 mm** |
| Maximum height / heatsink region | **~60.3 mm** |
| Supported cells in this enclosure family | 120–180 cells |

The 120-cell configuration therefore fits the same long enclosure family as the 180-cell unit.

This tells us something important:

> **A fully centralized 120S BMS can consume roughly a 400 × 160 × 60-mm electronics envelope before harness bend and service clearance.**

That is large enough to matter in a compact removable pack.

---

## 3. Revision-A dual-envelope strategy

Revision A should carry **two non-final BMS packaging concepts**.

### Concept A — centralized benchmark

Reserve a conservative gross service zone of approximately:

- **450 × 210 × 100 mm**;
- LV/CAN connector and harness bend room;
- cell-tap harness entry paths;
- current-sensor connection path;
- pack-service access;
- thermal airflow/conduction clearance as required;
- isolation from direct cell vent paths and coolant leaks.

This gross zone is **not** an Orion product dimension. It is a vehicle-level service envelope around the published Orion 120–180-cell benchmark.

### Concept B — distributed automotive master/slave

Preferred road-intent architecture may instead use:

- one compact BMS master/controller;
- multiple cell-monitoring/slave modules distributed near cell groups;
- separate current/voltage sensing;
- separate BDU/contactors/precharge/HVIL/isolation monitoring as the final supplier architecture requires.

Until Ligoo/Miaoyi supply exact drawings, reserve:

- one master zone approximately **250 × 200 × 80 mm**;
- several local slave-module zones approximately **150 × 100 × 40 mm each** as provisional placeholders;
- harness/service corridors between slaves and the master;
- physical separation from HV busbars where creepage/EMC demands it.

These are **VolksMule provisional CAD placeholders**, not claims about supplier dimensions.

---

## 4. BMS must not dictate cell count

The pack electrical architecture is selected first.

Current study remains around a **120S-class LFP pack**, because that aligns usefully with the current 400-V-class drivetrain/charging study and REPT 150/171-Ah energy levels.

But:

> **We do not choose 120S because Orion sells a 120-cell BMS or because an Alibaba listing says 120S/128S/132S.**

Final series count follows:

- cell operating-voltage limits;
- e-axle/inverter voltage windows;
- OBC output range;
- DC fast-charge operating range;
- HV component ratings;
- desired usable SOC window;
- thermal and fault behavior.

Then the BMS conforms to the pack.

---

## 5. Placement in the removable pack

Preferred BMS location should be:

- inside the removable battery assembly or on a serviceable protected electronics bay mechanically tied to it;
- accessible after pack isolation and removal of a bolted service cover;
- outside direct crash intrusion paths where practical;
- outside direct cell vent/plume paths;
- protected from coolant leakage;
- separated from high-current busbars enough to manage EMC and creepage/clearance;
- reachable without unstacking cell compression structures;
- replaceable without destructive adhesive removal.

### Do not bury it

Reject pack layouts where replacing the master BMS requires:

- removing dozens of cells;
- releasing structural cell compression unnecessarily;
- cutting welded pack structure;
- disturbing coolant cold plates that do not otherwise need service;
- vendor cloud authorization.

---

## 6. Harness architecture matters as much as the box

The physical penalty of a BMS is not only its enclosure.

Revision A must reserve:

- cell-voltage sense harnesses;
- temperature-sensor wiring;
- current-sensor wiring;
- CAN/CAN-FD lines;
- BDU/contactor/precharge command/status wiring;
- isolation-monitor interface;
- HVIL path;
- pack service/diagnostic connector;
- strain relief and connector service loops.

A centralized BMS can simplify module count but create long cell-tap harnesses.

A distributed BMS can shorten cell-tap wiring but increases local modules/connectors.

The final choice should minimize **whole-pack failure points and service burden**, not only controller volume.

---

## 7. Functional ownership boundary

### BMS should own or directly participate in

- cell-voltage monitoring;
- cell-temperature monitoring;
- SOC/SOH estimation;
- pack current measurement/validation;
- charge/discharge current and voltage limits;
- cell balancing;
- fault detection;
- contactor/precharge permission according to the final safety architecture;
- thermal requests;
- DTCs and pack-state reporting.

### BMS does not own

- steering;
- braking;
- driver access/start authorization;
- infotainment;
- charge-network accounts;
- body functions unrelated to battery safety;
- owner permission to read diagnostics or replace a failed module.

The VCU coordinates the vehicle. The BMS remains authoritative about battery safety.

---

## 8. Road-intent supplier gate

Before a Ligoo/Miaoyi-class unit can replace the provisional boxes, require:

- exact master/slave part numbers;
- dimensioned drawings and STEP files;
- cell-count configuration rules;
- supported cell-voltage range;
- pack-voltage range;
- current-sensor interface and range;
- isolation-monitor architecture;
- contactor/precharge/HVIL responsibilities;
- thermal-sensor count and type;
- balancing architecture and power;
- CAN/DBC/interface documentation;
- UDS/DTC documentation;
- local configuration/calibration tooling;
- offline firmware update and recovery;
- replacement commissioning procedure;
- environmental/EMC qualification;
- ISO 26262 / functional-safety evidence appropriate to the exact product;
- automotive manufacturing/traceability evidence;
- sample MOQ, price and lead time.

### Hard reject

Reject the road-intent BMS if:

- supplier only provides an app and marketing sheet;
- CAN protocol is withheld;
- replacement requires supplier cloud authorization;
- safety behavior is undocumented;
- exact automotive application is unclear;
- the product is actually ESS-only.

The earlier JBD HV-V3 screen remains the canonical example: matching voltage/cell count does not make an ESS BMS automotive.

---

## 9. Development BMS path remains separate

An open/development-friendly BMS such as ENNOID or a documented Orion configuration remains useful for:

- bench cell/module work;
- early contactor/precharge experiments;
- CAN gateway development;
- fault injection;
- thermal-control prototyping;
- closed-course mule development where appropriate.

That does **not** automatically make it the road-intent production choice.

The two-track strategy remains:

1. **transparent development hardware** so engineering can proceed;
2. **qualified automotive hardware** for the road-intent pack.

---

## 10. Revision-A conclusion

BMS physical packaging is no longer allowed to be a blank line in CAD.

Carry both:

### Centralized benchmark

> **~450 × 210 × 100 mm gross service zone**

based on Orion's documented 120–180-cell enclosure family.

### Distributed automotive placeholder

> **one ~250 × 200 × 80-mm master zone + several ~150 × 100 × 40-mm local slave placeholders**

until Ligoo/Miaoyi original drawings replace those estimates.

Current status:

> **PACKAGING BLOCKER REDUCED / EXACT ROAD-INTENT SUPPLIER CAD STILL REQUIRED / DO NOT FREEZE PACK LID OR HARNESS ROUTING YET**

---

## 11. Sources reviewed

Public research current as of **2026-08-31**:

- Ligoo New Energy current automotive Power-BMS product/platform material;
- current 2026 Chinese passenger-vehicle BMS installation rankings;
- Orion BMS 2 current product/configuration page;
- Orion BMS 2 mechanical drawing for the 120–180-cell enclosure family;
- existing VolksMule BMS sourcing screen in `ALIBABA_BMS_CANDIDATES.md`.
