# Alibaba LFP cell and module sourcing for Prototype 1

This document records the Prototype 1 sourcing screen for traction-battery cells and modules.

It follows the VolksMule battery architecture already chosen:

- 400-V-class;
- LFP-first;
- liquid-cooled;
- removable;
- non-structural;
- owner-serviceable at the pack/module level where technically reasonable.

The central sourcing rule is:

> **Buy automotive power cells from the cell manufacturer or a traceable authorized channel. Do not let Alibaba's 'Grade A' label become an engineering specification.**

## Executive verdict

| Cell path | Verdict | Why |
|---|---|---|
| REPT 150 Ah BEV LFP, manufacturer-direct | GREEN/YELLOW | Explicit BEV cell; REPT itself is on Alibaba with low MOQ; strong first RFQ/sample lead |
| REPT 171 Ah BEV LFP, manufacturer-direct | GREEN/YELLOW | Explicit BEV cell with useful capacity/energy-density window; ask REPT for Alibaba/direct sample path |
| EVE LF150, EVE's own Alibaba storefront | GREEN/YELLOW | Manufacturer-direct Alibaba path exists; power-cell family; exact passenger-vehicle qualification still to verify |
| EVE passenger-vehicle prismatic LFP family | GREEN/YELLOW | Serious automotive manufacturer; direct supplier relationship preferred over marketplace traders |
| CATL cells from unrelated Alibaba traders | RED/YELLOW | Useful market intelligence only until provenance and authorization are proven |
| 280–588 Ah ESS cells | RED as default traction architecture | Excellent storage products can still be the wrong road-vehicle cell format |
| Custom module around selected automotive cell | YELLOW/GREEN | Attractive if supplier gives drawings, cooling/compression requirements, and serviceable architecture |
| Sealed vendor pack that becomes structural/proprietary | RED | Conflicts with VolksMule architecture |

No exact cell is selected by this document.

## 1. Automotive power cell versus energy-storage cell

Alibaba frequently mixes application labels. A listing may say EV, solar, golf cart, forklift, UPS, and boat simultaneously. That is not an automotive qualification strategy.

The manufacturer product family is the first sieve.

### Prefer cells that the manufacturer itself classifies for:

- BEV passenger vehicles;
- passenger-car power batteries;
- motive-power EV use;
- automotive traction applications.

### Do not promote a cell merely because it has:

- LFP chemistry;
- the right voltage;
- a high Ah number;
- a low internal-resistance claim;
- a 'Grade A' seller label;
- UN38.3 paperwork;
- an Alibaba title containing the word EV.

## 2. REPT BATTERO — strongest immediate Alibaba-first candidate

**Status: GREEN/YELLOW — first supplier RFQ and sample path**

REPT is unusually interesting for this mission because:

1. it is a real high-volume battery manufacturer;
2. its official product catalog explicitly separates BEV cells from ESS cells;
3. REPT BATTERO itself has a verified Alibaba supplier presence;
4. the Alibaba supplier profile currently shows IATF 16949 and a large manufacturing/R&D footprint;
5. a manufacturer-direct Alibaba listing exists for the 150-Ah EV cell at prototype-friendly MOQ.

### REPT 150 Ah BEV LFP

Manufacturer engineering page:

- chemistry: LFP;
- nominal voltage: 3.2 V;
- capacity: 150 Ah;
- dimensions: 54 × 173 × 145 mm;
- mass: approximately 2.87 kg;
- cell energy density: 170 Wh/kg;
- listed application: BEV;
- advertised 10–80% fast-charge rate: 1.2C.

Official reference:
https://www.reptbattero.com/150ah-battery-cell/

Alibaba manufacturer-direct listing:
https://www.alibaba.com/product-detail/REPT-LFP150ah-EV-Lifepo4-Battery-Cell_1601407202160.html

Current marketplace listing characteristics observed during this screen:

- seller: REPT BATTERO Energy Co., Ltd.;
- model: EV150K;
- MOQ: 4 pieces;
- price shown at crawl time: about US$39.78 each at the smallest quantity tier;
- listing includes UN38.3/MSDS and other certification claims.

**Important:** the Alibaba application metadata on the same page is noisy and lists consumer, solar, toy, marine, forklift and other applications. Use REPT's official BEV product page as the engineering classification, not Alibaba's taxonomy.

### REPT 171 Ah BEV LFP

Manufacturer engineering page:

- chemistry: LFP;
- nominal voltage: 3.2 V;
- capacity: 171 Ah;
- dimensions: 60 × 194 × 112 mm;
- mass: approximately 2.94 kg;
- cell energy density: 188 Wh/kg;
- listed application: BEV;
- advertised 10–80% fast-charge rate: 1.5C.

Official reference:
https://www.reptbattero.com/171ah-battery-cell/

This is currently the most attractive paper candidate in the first screen because its capacity lands naturally in a useful Prototype 1 pack-energy window while remaining an explicitly BEV-oriented cell.

### REPT product-family evidence

REPT's current official cell catalog explicitly lists a BEV family at roughly:

- 106 Ah;
- 132.5 Ah;
- 141 Ah;
- 143.5 Ah;
- 150 Ah;
- 171 Ah;
- 175 Ah.

The same catalog separately lists much larger ESS/commercial formats. That separation is useful sourcing evidence.

Reference:
https://www.reptbattero.com/battery-cell/

### Why REPT gets first contact

A small project normally has trouble reaching a real traction-cell manufacturer. The manufacturer-operated Alibaba storefront changes that equation: Alibaba can become the commercial/prototype interface while the **manufacturer's own technical documentation remains the source of engineering truth**.

## 3. EVE — strong second automotive/manufacturer-direct path

**Status: GREEN/YELLOW — second RFQ path**

EVE is a major battery manufacturer with a dedicated power-battery business and official passenger-vehicle solutions.

Its current official material explicitly lists prismatic LFP cells for new-energy passenger cars and a passenger-vehicle battery platform covering BEV/PHEV/HEV applications.

Official references:
- https://www.evebattery.com/en/battery-system-development
- https://www.evebattery.com/en/passenger-vehicles

### EVE LF150 on Alibaba

EVE Energy Co., Ltd. itself currently operates a verified Alibaba supplier storefront and lists the LF150 traction/power cell.

Current listing data observed:

- model: LF150;
- nominal capacity: 150 Ah;
- nominal energy: approximately 483 Wh;
- mass: approximately 2.83 kg;
- standard charge/discharge: approximately 0.5C / 0.5C in the listing;
- application metadata includes electric-vehicle/forklift/motive applications.

Manufacturer Alibaba reference:
https://www.alibaba.com/product-detail/EVE-LF150-150Ah-3-2V-lifepo4_1601364437245.html

EVE verified supplier reference:
https://suppliers.alibaba.com/eve-energy-co-ltd_2206676910894

### Caution

EVE's Alibaba storefront also sells ESS-oriented cells, and marketplace reviews/metadata are not a substitute for a direct project specification. The RFQ must identify the exact cell revision and intended automotive use.

### EVE LF105 / smaller cells

EVE also directly lists LF105-class cells through Alibaba. These are useful packaging comparisons and may suit a lower-capacity pack or parallel architecture, but a 150–175 Ah 1P study currently looks cleaner for the expected Prototype 1 energy target.

## 4. CATL — benchmark, not current Alibaba purchase recommendation

**Status: YELLOW/RED through generic marketplace channels**

CATL remains an obvious automotive technology benchmark, but the current Alibaba search surface is dominated by unrelated trading companies advertising 'original CATL' cells for EV/solar/golf-cart/storage use simultaneously.

Examples found during this pass include third-party Shenzhen sellers claiming CATL 173-Ah cells and broad CATL-branded cell assortments.

The issue is not that every such cell is fake. The issue is that VolksMule needs evidence of:

- actual cell manufacturer;
- exact model/revision;
- manufacturing date;
- unused/new status;
- automotive intended application;
- traceable lot/serial/QR data;
- authorized resale path or manufacturer confirmation;
- matching and quality data.

Until that evidence exists, third-party CATL listings remain **market intelligence / possible bench material, not road-pack candidates**.

## 5. 'Grade A' is not a requirement

Alibaba uses 'Grade A' constantly, often without defining it.

VolksMule should never write a purchase specification that says only:

> Grade A cells

Instead require measurable evidence.

### Minimum lot documentation

- manufacturer name;
- exact cell model and revision;
- manufacturing plant if available;
- manufacturing date / lot;
- serial or QR traceability;
- nominal capacity and tolerance;
- DC resistance specification and test conditions;
- cell mass and dimensional tolerances;
- open-circuit voltage at shipment;
- capacity matching criteria;
- resistance matching criteria;
- self-discharge / retention criteria;
- warranty and rejection criteria;
- transport documentation;
- manufacturer datasheet for the exact revision.

If a supplier cannot define what its 'Grade A' claim means numerically, ignore the phrase.

## 6. UN38.3 is shipping evidence, not vehicle approval

UN38.3 is important for transport/shipping of lithium batteries. It is not proof that a cell is appropriate for a road-vehicle traction pack.

Likewise, generic CE / RoHS / UL badges on a marketplace page do not substitute for the automotive engineering evidence required by the finished vehicle.

Ask for the actual reports/certificates tied to the exact cell model and revision where relevant.

## 7. First pack-energy study window

No series count is frozen. These calculations are only useful to compare cell families before the final voltage window is reconciled with the e-axles, inverter, OBC, BMS, J3400 DC charging path, and thermal architecture.

### 150 Ah at 3.2 V

Cell nominal energy: approximately **0.480 kWh**.

- 120S1P: approximately **57.6 kWh** nominal;
- 132S1P: approximately **63.4 kWh** nominal.

With REPT's ~2.87-kg cell mass:

- 120 cells: ~344 kg / 759 lb of cells before enclosure, cooling, busbars, BMS, contactors, insulation and protection;
- 132 cells: ~379 kg / 835 lb of cells before pack overhead.

### 171 Ah at 3.2 V

Cell nominal energy: approximately **0.547 kWh**.

- 120S1P: approximately **65.7 kWh** nominal;
- 132S1P: approximately **72.2 kWh** nominal.

With REPT's ~2.94-kg cell mass:

- 120 cells: ~353 kg / 778 lb of cells before pack overhead;
- 132 cells: ~388 kg / 856 lb of cells before pack overhead.

### What this tells us

The 150–175 Ah automotive-prismatic class can plausibly cover roughly a **58–75 kWh nominal study band** using a simple 1P architecture in the likely series-count neighborhood.

That is useful because a 1P architecture reduces:

- cell count;
- parallel current-sharing uncertainty;
- busbar complexity;
- sensing complexity;
- failure diagnosis complexity.

It does not prove that 1P is final; power requirements and cell current limits still decide that.

## 8. Why giant ESS cells are not the default

A 280–588 Ah LFP cell can be an excellent energy-storage product and still be a poor VolksMule traction-cell choice.

Potential drawbacks include:

- larger physical dimensions dictating pack geometry;
- fewer packaging options around crash structure;
- heavier individual service pieces;
- thermal gradients across larger cell faces;
- current/power behavior optimized for stationary use rather than traction;
- compression/retention requirements poorly suited to our pack;
- marketplace sellers assuming 'big Ah' automatically means better EV cell.

REPT's own catalog illustrates the distinction clearly: its 588-Ah cell is explicitly listed for utility/C&I energy storage, while its 150/171-Ah cells are explicitly BEV products.

That is the sourcing sieve we should preserve.

## 9. Module versus raw-cell architecture

Prototype 1 should investigate two paths in parallel.

### Path A — manufacturer cell + VolksMule module

Pros:

- maximum packaging control;
- documented module geometry can remain ours;
- easier alternate-cell planning if interfaces are designed carefully;
- cooling and service access can fit the vehicle.

Cons:

- we own cell compression/retention;
- busbar design;
- sensing;
- dielectric protection;
- vent management;
- mechanical validation;
- assembly process.

### Path B — manufacturer-supplied automotive module

Pros:

- supplier already solves compression, busbars, cell retention and sampling;
- lower cell-assembly process burden;
- possibly better validated thermal/mechanical behavior.

Cons:

- module dimensions may dictate the car;
- module cooling interface may be proprietary;
- serviceability may be worse;
- supplier may only support OEM volumes;
- alternate sourcing can become harder.

### Working rule

Prefer the manufacturer module **only if it improves safety and engineering without making the vehicle captive to one nonserviceable package**.

## 10. Cell RFQ — REPT / EVE

Ask each manufacturer for the following for candidate BEV LFP cells in approximately the 140–180 Ah range.

### Commercial / provenance

1. Can you support prototype quantities of 8–20 cells, then roughly 130–150 matched cells for a prototype vehicle?
2. Can orders be placed through your official Alibaba storefront or another manufacturer-controlled channel?
3. Exact manufacturer legal entity and plant?
4. Exact model number and revision?
5. New production only, never used/pulled/rewrapped?
6. Production date / lot identification?
7. Per-cell serial/QR traceability?
8. Warranty/rejection process for prototype orders?
9. North American after-sales or engineering contact?

### Electrical

10. Nominal/minimum capacity and tolerance?
11. Recommended SOC operating window for long life?
12. Continuous charge/discharge limits versus temperature and SOC?
13. Pulse-current limits and durations?
14. DC resistance and measurement condition?
15. Peak/continuous power maps?
16. cold-temperature charge restrictions?
17. cycle-life data at relevant C-rates and temperatures?
18. self-discharge limits?

### Mechanical / thermal

19. Exact drawing with tolerances?
20. Cell mass tolerance?
21. Required face compression / clamping range?
22. Swelling/growth allowance through life?
23. Vent location and required clearance?
24. Recommended orientation constraints?
25. Cell surface temperature limits?
26. Preferred cooling surfaces and allowable gradients?
27. Terminal torque / welding recommendations?
28. Busbar material/interface guidance?

### Safety / qualification

29. Exact UN38.3 report for the model/revision?
30. Automotive qualification / customer application class?
31. Abuse/safety-test summary available under NDA?
32. Thermal-propagation data or module recommendations?
33. Manufacturing quality-system certificates and scope?
34. Can the supplier provide a recommended module design or sample module using the exact cell?

### Matching

35. Can the full pack lot be factory-matched?
36. What capacity spread is guaranteed within the lot?
37. What resistance spread is guaranteed?
38. Are all cells from one production lot/date range?
39. Can electronic matching data be supplied by serial number?

## 11. Incoming inspection plan

Before building a pack around any lot:

- verify count and shipping damage;
- photograph/record every serial/QR code;
- verify dimensions and mass statistically across the lot;
- verify open-circuit voltage distribution;
- measure DC resistance using one documented method;
- perform controlled capacity characterization on a representative sample using suitable battery-test equipment;
- track self-discharge on representative samples;
- compare results to manufacturer lot/matching data;
- reject suspect, swollen, damaged, relabeled or outlier cells;
- keep destructive/abuse qualification work with an appropriately equipped battery laboratory rather than improvising it in the workshop.

## 12. Cell interface should remain replaceable

The pack should avoid making ordinary cell/module service impossible through permanent structural bonding.

That does not mean cells must be individually swappable from under the vehicle. Safe service may require pack removal and opening in an appropriate work area.

But the design should avoid deliberately making one failed module mean:

> replace the entire vehicle.

## 13. Supplier ranking after this pass

### 1. REPT BATTERO 150/171-Ah BEV family

**First contact.**

Why:

- explicit BEV product classification;
- strong 150–175 Ah product range;
- manufacturer-direct Alibaba presence;
- prototype-friendly Alibaba MOQ on 150-Ah listing;
- verified Alibaba manufacturer profile;
- IATF 16949 shown on Alibaba supplier profile;
- U.S. after-sales capability is advertised on Alibaba's supplier discovery page;
- good packaging/energy-density numbers on paper.

### 2. EVE power/prismatic LFP family, especially LF150-class

**Second contact.**

Why:

- major automotive battery manufacturer;
- official passenger-vehicle LFP capability;
- manufacturer-operated Alibaba storefront;
- LF150 available directly through that storefront;
- broad future module/system capability.

### 3. Other automotive Tier-1 cell manufacturers

CALB, Gotion, CATL and others remain legitimate supplier/benchmark targets, but they should only enter the purchase shortlist through traceable manufacturer/authorized channels with low-volume support.

### 4. Alibaba third-party cell traders

Useful for:

- price discovery;
- availability intelligence;
- bench cells when provenance does not matter;
- discontinued/donor research.

Not the first choice for the road-intent traction pack.

## 14. Current conclusion

Alibaba can materially help VolksMule source **real automotive traction cells**, but only if we use it as the front door to the actual manufacturer rather than treating every seller's 'Grade A CATL/EVE' claim as equivalent.

The current strongest sourcing direction is:

> **Contact REPT directly through its verified Alibaba/manufacturer channels for 150-Ah and 171-Ah BEV LFP data/samples; contact EVE directly for its LF150/passenger-LFP family; keep roughly 150–175 Ah as the first packaging study band; keep exact series count and pack capacity open.**

Most importantly:

> **The cell must fit the car's safety, thermal, power, service and voltage architecture. The car does not get redesigned around whichever giant ESS cell Alibaba happens to discount this week.**

## Sources

- REPT BATTERO cell catalog: https://www.reptbattero.com/battery-cell/
- REPT 150-Ah BEV cell: https://www.reptbattero.com/150ah-battery-cell/
- REPT 171-Ah BEV cell: https://www.reptbattero.com/171ah-battery-cell/
- REPT verified Alibaba supplier: https://suppliers.alibaba.com/rept-battero-energy-co-ltd_2218527191658
- REPT 150-Ah manufacturer Alibaba listing: https://www.alibaba.com/product-detail/REPT-LFP150ah-EV-Lifepo4-Battery-Cell_1601407202160.html
- EVE passenger vehicles: https://www.evebattery.com/en/passenger-vehicles
- EVE power/prismatic LFP family: https://www.evebattery.com/en/battery-system-development
- EVE verified Alibaba supplier: https://suppliers.alibaba.com/eve-energy-co-ltd_2206676910894
- EVE LF150 Alibaba listing: https://www.alibaba.com/product-detail/EVE-LF150-150Ah-3-2V-lifepo4_1601364437245.html
