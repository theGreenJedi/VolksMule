# Revision-A SAE J3400 vehicle-inlet envelope

This file turns current **SAE J3400 vehicle-inlet hardware** into a practical Prototype 1 body/HV packaging envelope.

It does not freeze Phoenix Contact as the production supplier.

Phoenix Contact's current CHARX NACS/J3400 inlets are used here as a **high-confidence engineering benchmark** because they publish exact dimensions, current ratings, locking, temperature sensing, service connections, environmental ratings and standards claims.

> **Design the body around a standardized, replaceable charge inlet. Do not turn the charge port into bespoke body sculpture.**

---

## 1. Current benchmark

The strongest current physical benchmark is Phoenix Contact:

**CHARX NAI12-1AC80DC300-2,0C5 — item 1921180**

Published current data:

- AC/DC NACS / SAE J3400 vehicle inlet;
- rear-panel mounting;
- 80 A AC, 277 V AC;
- **300 A permanent DC**;
- up to **800 A DC boost** under defined conditions;
- 1000 V DC rated voltage;
- 12-V locking actuator;
- mechanical emergency release;
- lock-position recognition;
- two Pt1000 sensors at the DC contacts;
- IP67 inner-area claim;
- IP6K9K front-area claim when properly mated;
- more than 10,000 insertion/withdrawal cycles;
- detachable/serviceable HV and signal connections;
- SAE J3400 and IEC 62196-3 listed in current technical data;
- small-series MOQ 1 on current Phoenix listing.

The exact certification status of every claimed standard must still be confirmed for the purchased revision; the current page lists UL 2251 with a note that it is in preparation for this exact item.

---

## 2. Exact benchmark geometry usable in Revision A

Phoenix publishes:

| Item | 300-A J3400 benchmark |
|---|---:|
| Inlet width | **90.2 mm** |
| Inlet height | **90.2 mm** |
| Inlet depth | **146.85 mm** |
| Body bore/cutout bounding size | **73 × 73 mm** |
| Mounting | rear-panel |
| Mounting-hole diameter | **6.70 mm** |
| Fasteners | M6 |
| Frontal inclination allowed | **0–90°** |
| Assembly mass with published 2-m leads | **~4.92 kg** |

### Revision-A CAD reserve

Carry the actual inlet envelope plus service/harness margin rather than only the 90-mm face.

Initial gross zone:

- approximately **120 × 120 mm body-side face/service region**;
- at least **~175–200 mm inward depth study reserve** until exact cable routing/bend radius is modeled;
- accessible mechanical emergency-release path;
- removable trim/door access that does not require cutting or bonded body work;
- protected routing corridor from inlet to BDU/DC charge path and OBC AC path.

The extra packaging margin is not a Phoenix dimension. It is VolksMule service/routing allowance.

---

## 3. Why 300 A is the current rational benchmark

The larger Phoenix version offers 350 A permanent DC and uses heavier 95-mm² DC conductors.

The 300-A version uses **2 × 70 mm²** DC conductors and is already beyond the current cell-side charge needs we can justify.

### Against the detailed REPT 150-Ah baseline

The dated REPT CB54173145EA-150Ah specification publishes:

- 150 A maximum continuous charge at 25 °C;
- 300 A / 60-s peak charge.

Thus a 300-A permanent inlet is not the bottleneck in that baseline.

### Against current REPT 171-Ah marketing

Current REPT marketing gives 1.5C fast charging for the 171-Ah cell.

1.5C × 171 Ah = **256.5 A**.

Even if that rate is confirmed in the eventual engineering specification, a 300-A permanent inlet still provides useful current margin.

### Rule

> **Do not carry heavier 350-A/800-A hardware merely because a bigger number exists. The cell, pack, contactors, cable, thermal system and charging target decide the useful current.**

The 350-A family remains available if the final battery justifies it.

---

## 4. Cable envelope

The current 300-A Phoenix assembly publishes:

- DC power conductors: **2 × 70 mm²**;
- each DC conductor outside diameter: **17.90±0.3 mm**;
- PE conductor: **25 mm²**;
- PE outside diameter: **8.60±0.1 mm**;
- supplied lead length on the benchmark item: 2 m.

These are large, stiff conductors compared with normal LV harnesses.

### Packaging consequence

The charge-port location must be chosen with the **HV cable route** in mind, not just what looks nice on the quarter panel.

Prefer:

- short path to the BDU/DC fast-charge connection;
- broad bend radii;
- protected mounting clips and strain relief;
- no routing through wheel-tire jounce/steering envelopes;
- no sharp sheet-metal edges;
- no routine service operation requiring cable flex at the inlet body;
- accessible disconnect/service points.

Need Phoenix/supplier exact minimum static and dynamic bend-radius data before the body channel is frozen.

---

## 5. Locking and manual release

The benchmark inlet uses:

- **12-V, four-position locking actuator**;
- motor supply range **9–16 V**;
- typical lock motor current approximately 0.25 A;
- reverse current up to 1.5 A for limited duration;
- lock-position recognition;
- mechanical emergency release;
- heated locking-bolt feature promoted for cold-weather reliability.

This fits VolksMule's 12-V architecture naturally.

### Hard rule

The driver/service technician must have a **local physical method to release the connector after safe charge shutdown**.

The release may be behind a small service flap or reachable cable/lever, but must not require:

- a phone;
- a cloud account;
- infotainment boot;
- dealer authorization.

The EVCC/VCU must first make the HV system safe; the physical release then restores mechanical access.

---

## 6. Temperature sensing

Phoenix integrates **two Pt1000 sensors at the DC contacts**.

That is exactly the type of local sensing VolksMule should require.

The inlet/charging controller must be able to:

- measure both high-current contact temperatures;
- derate charge current before unsafe contact temperature;
- terminate charging on sensor failure/overtemperature according to a documented strategy;
- expose raw/processed temperatures and DTCs locally.

Phoenix's current technical data specifies a **100 °C DC-contact limit** in its environmental/current-derating note.

The exact current-vs-temperature map for the selected inlet must be retained in the vehicle service documentation.

---

## 7. Power and signal interfaces

The current Phoenix benchmark publishes three power paths that share the J3400 current-carrying interface:

- AC: L1 / N / PE;
- DC: DC+ / DC- / PE.

Signal side includes:

- control-pilot / communication conductors;
- proximity/coding behavior;
- PLC communication consistent with ISO 15118 / DIN 70121 architecture;
- separate plug-in signal and lock-actuator connectors.

The vehicle architecture still separates functions:

- **AC path → onboard charger**;
- **DC path → protected BDU/pack DC charge path**;
- **CP/PLC → MIDA-class EVCC**;
- **temperature/lock signals → locally documented vehicle control interfaces**.

The inlet does not become a mysterious all-in-one charger.

---

## 8. Serviceability is a selection criterion

Phoenix explicitly advertises **detachable HV and signal lines for maintenance** on the current J3400 family.

That behavior should become a VolksMule sourcing requirement regardless of final supplier.

Desired charge-port module:

- inlet removable from behind the body panel;
- HV connections safely disconnectable after pack isolation;
- LV/communication connectors separately replaceable;
- lock actuator serviceable;
- charge-port door/flap independent of inlet replacement where practical;
- no bonded one-piece quarter-panel charging assembly;
- no VIN/cloud pairing required to replace the physical inlet.

---

## 9. Body-location rules

Revision A may test multiple body locations, but each must satisfy:

1. connector can be inserted without extreme reach/crouch;
2. charge cable does not naturally cross a door opening;
3. inlet is protected from routine curb/brush impact;
4. inner cable run remains short and protected;
5. body water drainage cannot dump onto open HV interfaces;
6. emergency release is reachable;
7. inlet can be replaced without removing the battery pack;
8. rear/front collision structure does not turn the inlet into a direct intrusion spear;
9. access door remains simple and manually operable;
10. snow/ice can be cleared by hand.

A simple hinged manual flap is sufficient unless testing proves otherwise.

---

## 10. Standards boundary

Current SAE structure matters:

- **SAE J3400** covers the broader conductive-power-transfer system;
- **SAE J3400/2 (current 2025 revision)** covers dimensional definition of the NACS/J3400 connector and inlet.

Therefore an Alibaba inlet with a NACS-shaped face is not automatically a conforming SAE J3400/2 inlet.

### Final-supplier gate

Require for the exact quoted inlet:

- manufacturer identity;
- drawing showing J3400/2 mating geometry;
- current revision of claimed standards;
- exact test/certification evidence;
- contact-temperature sensing design;
- lock/manual-release design;
- HV conductor/interface details;
- durability/environmental evidence;
- CAD.

Phoenix is the current benchmark for the evidence quality, not necessarily the final purchase.

---

## 11. Current Revision-A status

The charge-port body envelope is no longer vague.

Revision A can now carry a credible benchmark around:

> **~90 × 90 × 147 mm inlet body + rear-panel mounting + 12-V lock/manual release + local contact-temperature sensing + large 70-mm² DC cable routing/service envelope.**

Current preferred benchmark current class:

> **300 A permanent DC**

Current reason:

> It already exceeds the charge current justified by both the detailed 150-Ah baseline and the current 171-Ah marketing candidate, while avoiding the extra cable/mass of the 350-A family unless later cell data demand it.

Status:

> **CARRY PHOENIX 300-A J3400 GEOMETRY AS REVISION-A BENCHMARK / FINAL SUPPLIER OPEN / EXACT BODY LOCATION STILL PACKAGING-DEPENDENT**

---

## 12. Sources reviewed

Public research current as of **2026-08-31**:

- Phoenix Contact CHARX NAI12-1AC80DC300-2,0C5, item 1921180;
- Phoenix Contact CHARX NAI12-1AC80DC350-2,0C5, item 1880532, for comparison;
- Phoenix Contact current NACS/J3400 product-family information;
- SAE J3400/2_202505 scope/current revision information;
- current REPT 150/171-Ah evidence summarized in `REV_A_REPT_CELL_ENVELOPE.md`.

The Alibaba/supplier-level inlet search remains in [`ALIBABA_J3400_CHARGING.md`](ALIBABA_J3400_CHARGING.md).
