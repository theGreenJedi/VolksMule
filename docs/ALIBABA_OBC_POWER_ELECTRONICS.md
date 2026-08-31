# Alibaba OBC / DC-DC / PDU candidate screen

Research date: **2026-08-31**

This document screens the next packaging-critical VolksMule Prototype 1 subsystem after the first e-axle pass: **AC onboard charging, HV-to-12-V conversion, and high-voltage distribution**.

Nothing here is a frozen part selection.

The Prototype 1 architecture currently calls for:

- roughly 400-V-class traction battery;
- SAE J3400 vehicle inlet;
- AC onboard charging;
- DC fast-charge capability;
- conventional 12-V low-voltage ecosystem;
- locally diagnosable and serviceable electronics;
- safety-critical operation independent of cloud services.

The most attractive sourcing direction is an integrated **OBC + DC/DC + PDU** assembly if integration saves mass, wiring, connectors and custom HV engineering **without hiding the interfaces we need to own**.

---

# Important architecture boundary

An OBC is not the whole charging system.

For VolksMule, keep these roles conceptually separate even if a supplier later integrates some of them:

1. **Vehicle inlet** — physical SAE J3400 connector, lock/release, temperature sensing and HV conductors.
2. **Vehicle-side charge-control / communications** — control-pilot/proximity and whatever communications/control hardware the final AC/DC J3400 implementation requires.
3. **OBC** — converts external AC to traction-battery DC for AC charging.
4. **DC-fast-charge path** — routes charger-supplied HV DC to the battery through the required contactors, sensing, isolation, HVIL and protection architecture rather than through the AC OBC power stage.
5. **HV-to-12-V DC/DC** — maintains the conventional 12-V bus from the traction battery.
6. **PDU** — distributes/protects HV branches to drive units, HVAC, OBC/DC charging path and other loads.

Therefore **do not buy an OBC assuming that "CAN controlled" means it already solves SAE J3400 vehicle communications.** That interface must be documented separately.

---

# Candidate 1 — Dilong CDU8KM64 family

**Status: FIRST-TIER ALIBABA CANDIDATE — DOCUMENTATION GATE**

Manufacturer:

- Dilong New Energy Technology
- https://en.dilongkeji.com/

Manufacturer product reference:

- https://en.dilongkeji.com/html/product/51.html

Alibaba discovery reference:

- https://www.alibaba.com/countrysearch/CN/dilong.html

## Manufacturer-published headline specifications

| Item | Published value |
|---|---|
| Integration | OBC + DC/DC + PDU, 3-in-1 |
| OBC power | 6.6 kW |
| DC/DC power | 1.5 kW |
| LV output | 14 V or 28 V variants |
| HV input family | manufacturer page lists 200–850 VDC family window for DC/DC side |
| OBC HV output family | manufacturer page lists 250–850 VDC family window |
| AC input | 85–264 VAC |
| Control | CAN |
| Protection | IP67 |
| Cooling | liquid-cooled family |
| Envelope | approximately 501 × 380 × 150 mm |

The Chinese manufacturer page for the same series describes CAN 2.0B communications and identifies it as a liquid-cooled 6.6-kW OBC + 1.5-kW DC/DC + PDU assembly.

Alibaba currently surfaces Dilong directly as a supplier, including 6.6-kW OBC + 1.5-kW 14-V DC/DC 400-V-class combo products at prototype-scale MOQ in some listings.

## Why it is interesting

- actual manufacturer appears reachable through Alibaba rather than only a reseller;
- integrated unit removes multiple HV connectors and separate housings;
- 14-V / 1.5-kW output aligns naturally with the Mule's intentionally ordinary 12-V architecture;
- CAN control and fault reporting are explicitly part of the product family;
- IP67 and liquid cooling fit automotive packaging better than generic industrial converters;
- wide family voltage range means a 400-V-class pack is plausibly within an existing variant rather than requiring a bespoke design.

## Why it is not selected

The public data are not enough to answer:

- exact 400-V variant operating window and derating;
- unit mass;
- actual PDU topology and branch ratings;
- contactor/precharge content;
- HVIL architecture;
- isolation-monitoring interaction;
- AC inlet/control-pilot interface responsibilities;
- whether the OBC is galvanically isolated and under what test standard;
- CAN message documentation;
- diagnostic/reflash access;
- whether the product is automotive-qualified at the exact factory/product revision offered on Alibaba.

Also, Dilong's own site explicitly says headline parameters are for reference and that the detailed technical manual governs. That is exactly the correct sourcing discipline for VolksMule.

## Immediate RFQ request

Ask Dilong for the controlled technical manual and STEP model for the exact **400-V-class, 14-V, 6.6-kW OBC + 1.5-kW DC/DC + PDU** configuration.

Do not design around the Alibaba headline listing before receiving those documents.

---

# Candidate 2 — Dilong DA8KM22 2-in-1 family

**Status: STRONG FALLBACK / MODULARITY OPTION**

Manufacturer reference:

- https://www.dilongkeji.com/wap/html/product/detail/80.html

Published family characteristics include:

- 6.6-kW OBC;
- 1.5-kW DC/DC;
- 14-V / 28-V low-voltage variants;
- CAN 2.0B;
- air-cooled packaging;
- IP66;
- approximately 365 × 249 × 139 mm.

## Why keep a 2-in-1 option alive

A 3-in-1 is only better if the PDU portion matches our architecture.

If the integrated PDU forces undesirable branch ratings, contactor logic, non-serviceable fusing, proprietary HVIL behavior, or awkward packaging, a **2-in-1 OBC/DC-DC plus a VolksMule-controlled serviceable PDU** may be the better whole-vehicle solution.

This is a core project principle: fewer boxes is not automatically simpler if the interfaces become worse.

---

# Candidate 3 — Shenzhen Ovar 6.6-kW / 1.5-kW family

**Status: SECOND-SOURCE ALIBABA CANDIDATE — VERIFY MANUFACTURING DEPTH**

Alibaba currently surfaces Shenzhen Ovar New Energy Technology as a supplier of:

- 6.6-kW onboard chargers;
- 1.5-kW DC/DC converters;
- 2-in-1 OBC + DC/DC systems;
- 3-in-1 OBC + DC/DC + PDU systems;
- approximately 200–420-V high-voltage variants;
- CAN-bus products;
- air- and water-cooled configurations.

Discovery references:

- https://www.alibaba.com/board-battery-charger-suppliers.html
- https://www.alibaba.com/ev-charger-control-board-suppliers.html

## Why it matters

Even if Dilong ultimately proves stronger, Ovar demonstrates that the subsystem is not a single-supplier unicorn. Multiple Alibaba-accessible firms offer the same broad architecture.

That improves our chances of defining a **replaceable subsystem interface** rather than designing the Mule around one vendor forever.

## Open questions

- Is Ovar the original manufacturer for every surfaced model or integrating/rebranding some units?
- Exact factory quality certifications?
- Full CAN protocol availability?
- Mechanical CAD?
- PDU internal topology?
- automotive EMC/transient/environmental evidence?
- production support horizon?

Until those are answered, Ovar is a supplier lead rather than a component shortlist.

---

# Benchmark — VMAX 400-V 11-kW bidirectional OBC + 3-kW DC/DC

**Status: BENCHMARK, NOT YET AN ALIBABA SOURCING WIN**

Manufacturer:

- VMAX / Shenzhen VMAX New Energy
- https://vmaxpower.com.cn/

Reference:

- https://vmaxpower.com.cn/product_display.php?id=197

VMAX publishes a particularly useful benchmark for a modern 400-V integrated charging unit:

| Item | Published value |
|---|---:|
| OBC | up to ~11 kW class, with 6.6-kW single-phase capability |
| DC/DC | 3.0 kW |
| LV output | 9–16 V, nominal 14 V |
| HV range | 200–450 VDC |
| Bidirectional AC capability | yes, published |
| CAN | CAN 2.0B |
| Diagnostics | UDS support |
| Cooling | liquid |
| Weight | 6.5 kg |
| Volume | 3.8 L |
| Protection | IP67 |

## Why this matters even if we cannot buy it through Alibaba

It sets a **quality and packaging benchmark**.

A marketplace candidate should not win merely because it exists. We can now ask whether it is competitive with an OEM-oriented unit in:

- mass;
- volume;
- LV power;
- efficiency;
- diagnostics;
- bidirectional capability;
- thermal performance;
- interface openness.

Dilong's CDU8KM64 public envelope is much larger than the VMAX benchmark. That does not disqualify it — it may integrate more PDU hardware, use a different generation of power electronics, or be easier to procure/support — but it means we should **ask for weight and actual internal scope before celebrating integration**.

---

# Additional benchmark — Great Wall Power Technology 400-V bidirectional family

Manufacturer reference:

- https://www.gwpst.com/product/detail/1337.html

Great Wall Power Technology publishes 400-V-class bidirectional OBC/DC-DC families including 6.6-kW and ~11-kW charging architectures with 3-kW-class 12-V conversion.

This reinforces two useful conclusions:

1. **3-kW 12-V DC/DC is a realistic modern benchmark**, not an exotic request.
2. bidirectional-capable onboard power electronics are already an established product family, which matters to VolksMule's later external-power / V2H path.

Prototype 1 does not need to make bidirectional capability a blocker, but we should avoid unnecessarily closing the architecture door.

---

# 6.6 kW versus 11 kW — do not freeze yet

A 6.6-kW OBC is sufficient to prove a practical AC-charging Prototype 1 and is widely represented in Alibaba supply.

An ~11-kW-class unit can improve AC charging where the available supply and vehicle-side implementation support it, but may add cost, complexity or three-phase capabilities that are not useful in the intended North American use case.

Therefore the correct current requirement is not "must be 6.6 kW" or "must be 11 kW."

It is:

> **Select the simplest documented OBC family that provides useful North American AC charging, fits the final J3400 vehicle-side architecture, and does not compromise serviceability or DC-fast-charge integration.**

Compare actual charging use cases after pack capacity is narrowed.

---

# 1.5 kW versus 3 kW 12-V DC/DC — investigate load budget

Dilong/Ovar commonly surface ~1.5-kW LV converters.

OEM-oriented benchmarks publish ~3-kW units.

Before selecting either, build the 12-V worst-case continuous and transient load budget including:

- exterior lighting;
- wipers/washer;
- ABS/ESC electronics and hydraulic pump demand;
- EPS demand profile;
- radiator/HVAC pumps and valves;
- blowers;
- contactors and control electronics;
- seat/restraint electronics;
- cameras/sensors;
- horn;
- infotainment/general-purpose computer;
- 12-V accessory outlets;
- degraded-operation conditions;
- recharge current needed for the 12-V battery after start/wake events.

A 1.5-kW converter should not be chosen by habit if steering/brake/thermal transients make 3 kW materially safer or simpler.

Conversely, a 3-kW converter should not be installed merely because a benchmark offers it.

---

# PDU integration gate

The integrated PDU must expose enough information to prove that it fits our architecture.

Require at minimum:

- schematic/block diagram of HV distribution;
- branch count and continuous/peak current ratings;
- fuse type and replacement procedure;
- contactor manufacturer/model/rating;
- precharge resistor/contactor architecture;
- HVIL loop implementation;
- service disconnect relationship;
- DC fast-charge branch topology;
- front/rear inverter branches;
- HVAC/compressor/PTC branches;
- OBC branch;
- isolation spacing and dielectric test data;
- current/voltage sensing locations;
- crash-shutdown input behavior;
- manual service procedure;
- whether branch components are replaceable individually.

If a supplier will not document the PDU, **do not let 3-in-1 packaging turn into a black box.**

---

# OBC / DC-DC supplier RFQ

For Dilong, Ovar and future candidates, request:

1. Exact model/revision proposed for a ~400-V LFP passenger/light-MPV system.
2. Controlled electrical datasheet and STEP CAD.
3. Total mass, filled/installed if liquid cooled.
4. OBC AC input voltage/current/frequency envelope.
5. OBC DC output voltage/current/power map and thermal derating.
6. OBC efficiency map across voltage/load/temperature.
7. Galvanic-isolation architecture and dielectric/isolation test values.
8. Power-factor and harmonic performance.
9. DC/DC HV input range and 12-V output regulation range.
10. DC/DC continuous/peak current and transient response.
11. DC/DC efficiency and thermal derating.
12. CAN 2.0B / CAN-FD DBC or complete message specification.
13. UDS or other diagnostics, DTC list and service tooling.
14. Firmware update/recovery procedure and whether cloud/vendor credentials are required.
15. Wake/sleep/ignition behavior and quiescent current.
16. HVIL, interlock and crash-shutdown behavior.
17. Exact PDU schematic/block diagram and branch ratings.
18. Contactors, fuses, precharge hardware and serviceability.
19. Coolant flow, pressure drop and allowable inlet-temperature range.
20. Environmental, vibration, shock, salt/corrosion and ingress test reports.
21. EMC/EMI and automotive electrical-transient qualification.
22. Applicable functional-safety process/evidence.
23. IATF 16949 factory/site evidence.
24. Connector manufacturer/part numbers and mating connectors.
25. Vehicle-side charge-control responsibilities: does the unit directly process any inlet control-pilot/proximity signals, or does it expect a separate charge controller/VCU/BMS interface?
26. DC-fast-charge integration requirements and PDU path.
27. Sample MOQ, prototype price and lead time.
28. Production/support horizon and replacement-unit commissioning procedure.
29. Whether a 3-kW 14-V DC/DC option exists in the same family.
30. Whether a bidirectional OBC option exists using substantially the same mechanical/electrical interface.

---

# Current ranking

| Candidate | Alibaba accessibility | 400-V fit | Integration | Docs visible | Service/control potential | Current verdict |
|---|---|---|---|---|---|---|
| Dilong CDU8KM64 | Strong | Strong-looking; exact variant verify | OBC + 1.5-kW DC/DC + PDU | Good headline/manufacturer data | Promising CAN; details needed | **Investigate first** |
| Dilong DA8KM22 | Strong | Strong-looking | OBC + 1.5-kW DC/DC | Good | Promising | **Strong modular fallback** |
| Shenzhen Ovar family | Strong | 200–420-V listings exist | 2-in-1 / 3-in-1 | Marketplace-level | Unknown pending protocol/docs | **Second-source investigation** |
| VMAX 11-kW bidirectional | Not established through Alibaba in this sweep | Excellent | OBC + 3-kW DC/DC; related 3-in-1 family exists | Strong manufacturer data | CAN + UDS published | **Benchmark / possible later source** |
| Great Wall Power Technology | Not Alibaba target in this sweep | Excellent | 2-in-1 / 3-in-1 families | Strong manufacturer data | Verify | **Benchmark** |

---

# Current conclusion

Alibaba can plausibly supply the entire **OBC + HV-to-12-V conversion + PDU** block rather than forcing VolksMule to design power electronics from scratch.

The strongest immediate marketplace lead is **Dilong**, because we can connect an Alibaba-accessible seller/manufacturer to a real manufacturer product catalog and technical family.

But the benchmark comparison changed the question. We should not ask merely:

> Can Alibaba sell us a 6.6-kW charger?

We should ask:

> Can an Alibaba-accessible supplier give us an integrated automotive power unit whose mass, packaging, thermal behavior, diagnostics, documentation and serviceability are good enough that using it improves the whole Mule?

That is the bar.
