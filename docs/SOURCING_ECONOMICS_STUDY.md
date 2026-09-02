# VolksMule sourcing economics study — prototype-scale supplier strategy

Updated: **2026-09-01**

Status: **screening result / architecture lesson**

This study preserves the first explicit cost test performed against the reconciled VolksMule sourcing BOM after the broad Alibaba/public-data sourcing mission.

It is intentionally not a purchase order, production BOM, supplier quote package or final vehicle-cost forecast. Its purpose was to ask a simpler and more revealing question:

> **If the current sourcing architecture were interpreted literally as roughly one prototype-scale purchase for each externally sourced BOM line, what would the market ask us to spend before we even built the vehicle?**

The answer exposed an economic problem early enough to change course without spending the money.

---

## 1. Screening assumption

The reconciled master sourcing BOM contained **145 tracked line items**.

For this exercise, **14 pure VolksMule design/architecture rows** were removed from the procurement count, leaving a working assumption of:

**145 total tracked rows - 14 design-only rows = 131 sourcing/procurement targets**

This is deliberately simplified.

A sourcing row is not necessarily one physical piece. For example:

- an LFP-cell row ultimately becomes many cells;
- a wheel or brake row ultimately becomes multiple physical pieces;
- connector, seal, cable and fastener rows expand into many individual parts;
- some system rows may later collapse into one integrated donor/application assembly;
- some current rows may disappear entirely after architecture consolidation.

The question here was not "what does one complete VolksMule cost?"

The question was:

> **What happens economically if we continue treating these 131 sourcing targets as independent prototype-scale purchases?**

---

## 2. Working cost ledger

The first-pass screening ledger produced the following category totals:

| Area | Working subtotal |
|---|---:|
| Front/rear drive | $31,205 |
| Structure/body hardware & prototype fabrication | $6,370 |
| Charging/onboard power | $5,250 |
| BMS/HV safety/distribution | $4,030 |
| Seats/restraints | $3,130 |
| Thermal/HVAC | $2,354 |
| Low-voltage/controls | $1,650 |
| Brakes | $1,495 |
| Visibility/lighting | $1,150 |
| Steering | $1,120 |
| Suspension/wheel ends | $1,060 |
| Safety automation | $1,000 |
| Wheels/tires/recovery | $920 |
| Battery-cell/pack hardware* | $590 |
| Utility/roadside | $430 |
| Diagnostics/infotainment | $330 |
| **Total** | **$62,084** |

Arithmetic check:

```text
31,205
+ 6,370
+ 5,250
+ 4,030
+ 3,130
+ 2,354
+ 1,650
+ 1,495
+ 1,150
+ 1,120
+ 1,060
+ 1,000
+   920
+   590
+   430
+   330
= 62,084 USD
```

`*` The battery-cell/pack line is intentionally misleading if interpreted as a complete pack cost because this screening exercise treated each BOM sourcing row as one purchasing target. A real pack multiplies the cell line many times and adds the true pack quantities of compression hardware, cooling, interconnects, sensing, etc.

---

## 3. Prototype execution allowance

The parts-only screening total was then rounded upward to a practical "what cash would need to exist if someone tried to execute this cart?" allowance of **$75,000**.

The difference is:

```text
75,000 - 62,084 = 12,916 USD
```

That is:

```text
12,916 / 62,084 = 20.8%
```

So the $75,000 figure was approximately a **20.8% allowance** above the screening ledger for fragmented freight, prototype/sample premiums, duties/taxes, price movement and other procurement friction.

It still did **not** include a defensible allowance for all fabrication labor, engineering labor, tooling, rework, failed parts, validation, compliance/certification work, complete harness quantities, every fastener/terminal/hose/fitting, or the real expanded quantity of every BOM family.

Therefore **$75,000 was not a credible complete Prototype-1 build cost. It was already an economic warning before those additional costs were added.**

---

## 4. The clearest market-force signal: prototype e-axle pricing

The largest visible distortion came from prototype-scale drive-unit pricing.

At the time of this study, the Alibaba listing for the Rawsuns READ2982 showed:

- **1-49 sets: $14,000 per set**;
- **50+ sets: $8,500 per set**.

Reference:

- https://arabic.alibaba.com/product-detail/55kw-110kw-EV-Conversion-Kit-350V-1601793304301.html
- manufacturer family reference: https://www.rawsuns.com/ev-transaxle/electric-axle/

If the conservative symmetric front/rear READ2982 study were interpreted as two prototype-scale purchases:

```text
2 x 14,000 = 28,000 USD
```

Relative to the $62,084 working ledger:

```text
28,000 / 62,084 = 45.1%
```

So **two prototype-priced e-axles alone represented about 45.1% of the entire screening total**.

This is not evidence that READ2982 is a bad product. It is evidence that buying many automotive subsystems independently at prototype/sample economics is a bad vehicle-cost architecture.

---

## 5. Other price anchors used to sanity-check the scale

The exercise also checked publicly visible prototype/small-quantity prices for representative carried components and categories. Examples current around the study date included:

- REPT 3.2-V 150-Ah LiFePO4 cells surfaced around **$31-$32.10/cell, MOQ 4** on Alibaba category listings;
- Dilong 6.6-kW OBC examples ranged from approximately **$840 sample pricing on Alibaba** to **$1,142-$2,000** across Dilong's own retail listings depending on configuration;
- NF 5-kW high-voltage coolant-heater listings surfaced around **$405-$500** at prototype quantity;
- a Bender iso175 automotive insulation-monitoring device was listed by New Eagle at **$805** for quantity 1-9.

References:

- https://www.alibaba.com/showroom/150ah-battery-cell.html
- https://www.alibaba.com/product-detail/Dilong-EV-Car-Onboard-Charger-Module_1600205177158.html
- https://www.powerdilong.com/collections/dilong-6-6kw-onboard-charger-obc
- https://www.alibaba.com/product-introduction/Popular-Model-5KW-PTC-Heater-Automotive_1600927237767.html
- https://store.neweagle.net/shop/electric-hybrid/hv-accessories/bender-isometer-iso175c-1-insulation-monitoring-device-imd/

These anchors do not validate every line in the ledger to quotation precision. They validate the **order of magnitude and the underlying market behavior**: prototype-scale automotive hardware can carry economics radically different from mass-market replacement parts or production-volume component pricing.

---

## 6. What failed

The failed hypothesis was:

> **A vehicle can remain economically sensible if most major subsystems are independently sourced as credible automotive-grade prototype/sample components from specialized suppliers.**

The screening result says that is not a satisfactory default strategy for VolksMule.

Repeated prototype pricing across more than one hundred independent sourcing decisions accumulates faster than any individual component looks alarming.

The failure mode is systemic:

- prototype/sample premiums are paid repeatedly;
- separate suppliers duplicate margins, freight and integration burden;
- custom or low-volume interfaces create further cost;
- engineering and validation obligations remain with VolksMule anyway;
- the resulting pile of parts can approach or exceed the purchase price of complete mass-produced vehicles before Prototype 1 is assembled.

---

## 7. What succeeded

**The sourcing exercise itself was not a failure.**

It succeeded at exactly the job early sourcing research should perform: it exposed market forces before money was committed.

No $75,000 cart was purchased.

Instead, public pricing and the reconciled BOM revealed that the then-current sourcing architecture would likely produce an economically irrational one-off vehicle.

The important result is therefore:

> **The strategy test failed; the experiment succeeded.**

Finding this on paper is dramatically cheaper than discovering it after fabrication begins.

---

## 8. New economic design rule

VolksMule should not merely ask whether a component is technically credible, serviceable, open and replaceable.

It must also ask:

> **Does this sourcing decision inherit real mass-production economics, or are we paying prototype economics for a problem the existing vehicle/industrial ecosystem has already solved at scale?**

The preferred future sourcing hierarchy becomes:

1. **Mass-market application/donor ecosystems** where one common platform can collapse several independent sourcing lines while preserving replaceability and documentation.
2. **Commodity/new components** where production economics already exist: cells, contactors, connectors, relays, pumps, cable, seals, hardware, etc.
3. **VolksMule-specific design/fabrication only where the interface or architecture genuinely must belong to the project.**
4. **Specialized prototype-scale automotive purchases only where no economically superior mass-produced path satisfies the requirement.**

"No donor car" must not be confused with "no donor-system economies."

VolksMule can remain its own vehicle while deliberately inheriting high-volume service ecosystems for wheel ends, brakes, steering, seating, HVAC, glazing or other systems where doing so improves the whole vehicle.

---

## 9. Required follow-on study

Before Revision-A interfaces are frozen around the current sourcing map, the BOM should undergo an explicit **economic-collapse pass**.

The next cost study should no longer price "one of each sourcing row."

It should:

- expand each retained row to actual Prototype-1 quantities;
- collapse rows that can be satisfied by one common donor/application assembly or ecosystem;
- remove double-counted functions contained inside integrated components;
- distinguish new commodity purchases from used/remanufactured/mass-market replacement parts;
- include freight and realistic prototype fabrication;
- identify the handful of genuinely bespoke/high-cost components;
- produce an actual one-vehicle hardware BOM estimate.

A useful architecture should show a credible path toward a complete Prototype-1 hardware BOM that is **materially below the cost of simply purchasing a complete new manufactured vehicle with comparable capability**.

If it cannot, the architecture should be changed before expensive physical integration begins.

---

# Verdict

> **PUBLIC-DATA SOURCING RESEARCH: SUCCESSFUL**
>
> **INDEPENDENT PROTOTYPE-SCALE SUPPLIER STRATEGY: ECONOMICALLY UNSATISFACTORY**
>
> **SCREENING LEDGER: $62,084 PARTS-ONLY UNDER THE 131-TARGET SIMPLIFICATION**
>
> **EXECUTION ALLOWANCE USED FOR THE THOUGHT EXPERIMENT: ~$75,000**
>
> **MONEY SPENT TO DISCOVER THE PROBLEM: ESSENTIALLY ZERO**
>
> **NEXT ECONOMIC MISSION: COLLAPSE THE BOM AROUND MASS-PRODUCTION ECONOMICS BEFORE FREEZING REVISION A**

This is exactly why VolksMule researches before it buys.