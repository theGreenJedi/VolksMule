# VolksMule utility power / V2L sourcing screen

Research date: **2026-08-31**

VolksMule is a utility vehicle. Useful external AC power therefore belongs in the architecture.

This screen separates three things that are easy to blur together:

1. **Onboard vehicle-to-load (V2L)** — the vehicle powers tools/appliances directly from dedicated AC receptacles.
2. **Vehicle-to-vehicle (V2V) AC power** — a related optional export use case.
3. **Grid-interactive V2H/V2G** — the vehicle participates as a distributed energy resource with utility/grid requirements and additional communications/safety obligations.

The Prototype 1 priority is intentionally simple:

> **Give the Mule useful local AC power first. Preserve a path to bidirectional home/grid power later. Do not make V2H/V2G a blocker for the first vehicle.**

---

# 1. Standards context — V2L is not the same problem as V2G

SAE J3400_202409 defines the North American charging coupler family and permits either AC single-phase or DC power transfer through the coupler.

Reference:

- https://saemobilus.sae.org/standards/j3400_202409-north-american-charging-system-nacs-electric-vehicles

SAE J2847/5_202509 explicitly includes optional **AC vehicle-to-load (V2L)** and **AC vehicle-to-vehicle** use cases and discusses mode/output communication for vehicles with bidirectional onboard charging capability.

Reference:

- https://saemobilus.sae.org/standards/j28475_202509-communication-plug-vehicles-customers

By contrast, SAE J2836/3_202402 and J2847/3_202311 address the vehicle as a distributed energy resource, reverse power flow, and IEEE 2030.5-related grid/energy-management communication.

References:

- https://saemobilus.sae.org/standards/j28363_202402-use-cases-plug-vehicle-communication-a-distributed-energy-resource
- https://saemobilus.sae.org/standards/j28473_202311-communication-plug-vehicles-a-distributed-energy-source

## VolksMule implication

Prototype 1 does **not** need to solve utility-grid interconnection merely to run a saw, compressor, lights, laptop, camp equipment, or emergency loads.

The base architecture may therefore use a **dedicated HV-to-AC onboard inverter feeding vehicle receptacles**, independently of the J3400 charge communication path.

A later bidirectional OBC/J3400 implementation may eventually add standards-based export through the charge port, but the first useful AC outlet does not have to wait for that ecosystem.

---

# 2. Working Prototype 1 requirement

## Power class

Study **2–3 kW continuous 120 VAC / 60 Hz** as the first useful target.

Why:

- enough for meaningful hand tools and worksite/camping/emergency loads;
- substantially more useful than a token 400–1500 W outlet;
- avoids forcing a very large accessory inverter into the first package;
- keeps output well within a reasonable current draw from the traction pack;
- leaves room to move upward if packaging/cost evidence says 6 kW is easy.

This is a study target, not a freeze.

## Architecture

Preferred path:

**traction HV bus -> dedicated protected HV feed -> isolated vehicle DC/AC inverter -> protected 120-V branch -> physical receptacle(s)**

The utility inverter should not depend on the infotainment computer.

A physical enable switch is preferred, with the VCU providing only safety permission/interlocks and status.

## Why not 12 V -> 120 V at this power

A 3-kW load on a nominal 12-V bus implies roughly 250 A before conversion losses. That demands large copper, large fusing, high-current switching and an oversized low-voltage converter/battery path solely to turn the power back into AC.

For multi-kilowatt output, **direct traction-HV-to-AC conversion is the cleaner architecture**.

A small 12-V inverter remains acceptable for low-power accessory loads if useful, but it is not the preferred worksite-power architecture.

---

# 3. Strongest Alibaba-discovered lead — Rawsuns RDA350 family

Rawsuns publishes an onboard household-appliance inverter family for new-energy vehicles.

Manufacturer reference:

- https://www.rawsuns.com/on-board-household-appliance-inverter-1kw-20kw/

## RDA350-120-3KW

Current manufacturer page lists:

- nominal DC input: **350 V**;
- input range: **200–450 VDC**;
- output: **120 VAC / 60 Hz**;
- model designation: **RDA350-120-3KW**;
- operating temperature: **-40 to +55 C**;
- dimensions: about **365 x 230 x 104 mm**;
- weight: about **10 kg**;
- forced-air cooling;
- **CAN communication**;
- **IP65**.

### Important documentation discrepancy

The same manufacturer page identifies the model as `RDA350-120-3KW` but one output-power field in that row says **1000 W**.

That contradiction is not something VolksMule should silently correct.

**Purchase gate:** manufacturer-issued exact-model datasheet, label photo, continuous/pulse output rating and test report must resolve the discrepancy before a sample is ordered.

## Why this family is unusually attractive

The **200–450 VDC** input range is much more tolerant of a 400-V-class LFP pack's real operating window than an inverter that only begins operating at 400 V.

120 V / 60 Hz is already North-American-useful.

CAN provides a path for:

- enable/disable;
- fault reporting;
- output state;
- thermal status;
- controlled shutdown.

The inverter still needs to remain useful without infotainment or internet access.

### Verdict

**GREEN-YELLOW — CONTACT NOW / DOCS FIRST / SAMPLE AFTER DOCS.**

Rawsuns is currently the strongest direct Chinese/Alibaba-ecosystem lead for Prototype 1's onboard AC export function.

---

# 4. Alibaba marketplace evidence — Nanjing Pengtu 350-V / 120-V 3-kW inverter

Current Alibaba search results also expose a **3-kW onboard EV inverter** sold by **Nanjing Pengtu Power Supply Co., Ltd.**, described around:

- 350-V-class DC input;
- 110/120-V AC output;
- 3 kW;
- vehicle/outdoor-emergency-power use;
- current marketplace pricing around **US$560** at MOQ 10 in surfaced listings.

Discovery page:

- https://www.alibaba.com/wholesale/inverter-3000w-120v.html

This is interesting price evidence, but marketplace copy is not enough to establish:

- exact input voltage window;
- galvanic isolation;
- CAN protocol;
- continuous rating at temperature;
- environmental/vibration qualification;
- output waveform quality;
- ground/neutral architecture;
- fault behavior.

### Verdict

**YELLOW — RFQ / PRICE BENCHMARK.**

Do not assume the Pengtu listing is the same exact hardware as the Rawsuns manufacturer family just because Alibaba copy contains the Rawsuns name.

Ask Pengtu to identify the actual manufacturer/model and provide engineering documentation before considering a sample.

---

# 5. OEM-grade benchmark — Bel Power Solutions 350INV60

Bel Power Solutions provides a very strong benchmark for what a genuine vehicle HV-to-AC inverter looks like.

Manufacturer:

- https://www.belfuse.com/products/power-supplies/dc-ac-inverters/350inv60-series
- https://www.belfuse.com/products/power-supplies/dc-ac-inverters/350inv60-120-240-9g

## 350INV60-120-240-9G

Published specifications include:

- **240–430 VDC** input;
- nominal **350 VDC**;
- **6 kW** continuous;
- **120/240 VAC split-phase** output;
- **25 A** output;
- liquid cooling;
- CAN control;
- full galvanic isolation;
- IP65/IP67 enclosure;
- approximately 92% typical efficiency;
- -40 to +70 C published operating range on the product page;
- protection for overtemperature, output overvoltage/overcurrent and related faults;
- E-mark approval;
- explicitly marketed for hybrid/electric and on/off-highway vehicle applications.

This is almost electrically ideal for a 400-V-class Mule.

### The problem

Current distributor pricing is roughly **US$11,000 per unit** at low quantities, with factory-pack/minimum-order constraints in some channels.

Therefore it is best treated today as:

1. an engineering benchmark;
2. an available COTS fallback if budget ceases to matter;
3. proof that the architecture itself is conventional vehicle hardware.

### Benchmark requirement

A lower-cost Alibaba/Chinese candidate does not need every feature Bel has, but it should be compared against Bel for:

- isolation;
- environmental sealing;
- continuous-temperature performance;
- CAN control/status;
- input protection;
- output fault protection;
- EMC/vibration evidence;
- published connector/service information.

---

# 6. Lincoren — Chinese vehicle DC/AC module lead

Lincoren publishes DC/AC core modules aimed at new-energy vehicle manufacturers and mobile/off-grid integrators.

Reference:

- https://lincoren.com/collections/dc-ac-core-module-unit

Current public description includes:

- **3-kW and 6-kW** high-frequency modules;
- broad **200–900 VDC** input-family capability;
- **220-V pure sine-wave AC** output in the published family;
- automotive-grade integrated design claims;
- digital control;
- vehicle/mobile integration intent.

### Strength

The voltage range and 3/6-kW packaging philosophy are useful.

### Gap

The public family shown is 220-V oriented. Prototype 1 wants native **120 V / 60 Hz**, unless a 120/240 split-phase model is available.

### Verdict

**YELLOW — CONTACT FOR NORTH-AMERICAN VARIANT.**

Ask whether Lincoren can provide:

- 200–450-V-class input;
- 120 VAC / 60 Hz or 120/240 split phase;
- full galvanic isolation;
- CAN enable/status/diagnostics;
- sealed automotive enclosure;
- automotive EMC/vibration/environmental evidence;
- prototype quantities.

---

# 7. Generic Alibaba solar/RV inverters — RED for HV road-intent use

Alibaba contains thousands of inexpensive 3–6-kW pure-sine inverters, but most current results are:

- 12/24/48/60/72-V input;
- solar/off-grid oriented;
- RV/home oriented;
- CE/consumer-product claims;
- not designed to connect directly to a 300–450-V traction bus;
- not qualified for road-vehicle HV isolation, vibration, water ingress, crash shutdown or automotive EMC.

Examples can cost well under US$200.

That is not evidence that a road-intent 400-V accessory inverter should cost US$200.

### Verdict

**RED — do not connect a generic solar inverter directly to the traction battery.**

Such equipment may be useful on a stationary bench or via an isolated low-voltage source. It does not become automotive because the listing contains the word “car.”

---

# 8. Output-side safety architecture

The final AC outlet system must be engineered as an electrical power source, not as a decorative convenience socket.

Working requirements:

- pure sine-wave AC;
- physically protected receptacles;
- branch overcurrent protection;
- output short-circuit protection;
- ground-fault protection appropriate to the final topology/use case;
- defined neutral/ground bonding strategy;
- galvanic isolation from traction HV unless a validated alternative architecture explicitly supports the required safety behavior;
- no exposed energized contacts;
- water/dust protection suitable to outlet location;
- physical output enable/disable;
- clear AC-available status;
- automatic shutdown for inverter overtemperature, HV isolation fault, crash state, severe battery fault or invalid HVIL state;
- safe behavior when the vehicle is moved/placed in drive according to final use policy;
- documented load limits.

The exact receptacle/GFCI/breaker implementation must be checked against the electrical-product and vehicle requirements applicable at design freeze. Do not infer compliance from household-component markings alone.

---

# 9. Control philosophy

## Physical control

Preferred cabin/cargo interface:

**UTILITY AC — OFF / ON**

with a physical switch or keyed/tactile control.

The VCU may refuse activation when unsafe, but infotainment does not own the feature.

## Local telltales

At minimum provide deterministic indication for:

- AC enabled/ready;
- overload/fault;
- output unavailable because of vehicle/HV condition.

A richer screen may show watts, energy delivered and diagnostics. That display is optional convenience, not the enabling authority.

## No cloud

No account, subscription or internet connection is required to power a tool from the vehicle.

---

# 10. Relationship to J3400 / bidirectional charging

Do **not** fuse the dedicated V2L inverter and J3400 charging controller into one conceptual box merely because both move energy out of the battery.

Prototype 1 can use:

### Path A — local utility power

traction pack -> dedicated onboard DC/AC inverter -> 120-V receptacle(s)

### Path B — charging

J3400 inlet -> EVCC/OBC/DC-fast-charge path -> traction pack

### Future Path C — standards-based bidirectional charge-port export

traction pack -> bidirectional OBC or supported off-board inverter architecture -> J3400 interface -> home/grid/load equipment

Path C may eventually reduce the need for some dedicated inverter functions, but it should not make Path A dependent on unfinished grid/interoperability work.

---

# 11. Power-level study

## 1 kW

Pros:

- simple;
- smaller/lighter;
- passive/fanless options exist;
- sufficient for electronics, chargers, lighting and many small loads.

Cons:

- too limiting for a vehicle explicitly intended as a work/utility platform.

**Verdict:** acceptable minimum/fallback, not preferred target.

## 2–3 kW

Pros:

- meaningful tool capability;
- 120-V current roughly in ordinary branch-circuit territory;
- Rawsuns already exposes an exact 3-kW family;
- moderate HV current;
- likely best cost/utility compromise.

**Verdict:** **preferred first study.**

## 6 kW / 120-240 V

Pros:

- extremely useful;
- can support heavier tools and meaningful emergency loads;
- Bel demonstrates a mature vehicle implementation.

Cons:

- bigger thermal/cooling/package burden;
- more expensive hardware;
- output-distribution design becomes more substantial;
- may be needless for Prototype 1.

**Verdict:** architecture benchmark and desirable later option; do not force it into Prototype 1 without a favorable supplier/packaging trade.

---

# 12. RFQ — Rawsuns utility inverter

Ask specifically for **RDA350-120-3KW** and, if available, a 120/240-V variant.

Request:

1. exact current production datasheet and revision;
2. confirmation that continuous rated output is 3.0 kW and correction/explanation of the 1000-W website field;
3. DC input operating, startup, shutdown and derating voltage thresholds;
4. DC ripple/current specifications;
5. output voltage/frequency regulation;
6. total harmonic distortion versus load;
7. continuous/peak output current and overload time;
8. efficiency map versus HV voltage/load;
9. galvanic-isolation specification and dielectric test;
10. neutral/ground output topology;
11. insulation-monitor interaction requirements;
12. CAN protocol/DBC and boot/reflash method;
13. hardware enable input if available;
14. startup/shutdown sequencing;
15. reverse polarity / input surge / inrush behavior;
16. precharge requirement;
17. short-circuit, overload, overtemperature and output-fault behavior;
18. EMC test evidence;
19. vibration/shock evidence;
20. IP65 test evidence;
21. cooling airflow requirement and fan serviceability;
22. STEP/CAD drawing;
23. HV/LV/AC connector manufacturer and mating parts;
24. prototype price for 1–2 units;
25. 10/100/1000-unit price;
26. expected production continuity and lead time.

## Sample gate

Sample purchase becomes reasonable only after:

- 3-kW continuous rating is resolved;
- 200–450-V operation is confirmed for the exact sample;
- isolation/output grounding are documented;
- CAN or hard-enable interface is provided;
- fault shutdown can be bench tested safely.

---

# 13. RFQ — Nanjing Pengtu

Ask for its current **350-V-class 3-kW 110/120-V EV inverter**, but do not reference marketplace branding as proof of manufacturer identity.

Request the same technical package as Rawsuns plus:

- actual manufacturer name;
- exact model number and label photo;
- explanation of whether the product is Pengtu-designed or resold/OEM hardware;
- automotive qualification evidence;
- sample quantity below the marketplace MOQ 10 if possible.

The current marketplace price is useful as a negotiating/data point, not as an approved cost assumption.

---

# 14. Prototype bench validation

Before vehicle installation:

1. energize from an isolated/current-limited HV source appropriate to the unit;
2. verify startup/shutdown thresholds;
3. measure no-load power draw;
4. verify 120 V / 60 Hz regulation;
5. measure waveform/THD under resistive and nonlinear loads;
6. test 25%, 50%, 100% rated load;
7. test short overload/power-tool inrush;
8. verify output ground-fault/short-circuit response;
9. verify loss of CAN/enable behavior;
10. verify overtemperature shutdown/recovery;
11. verify HV undervoltage/overvoltage behavior;
12. test contactor/open-circuit shutdown behavior;
13. record conducted/radiated-noise issues around CAN, BMS and radio systems;
14. inspect thermal hotspots/connectors after sustained load;
15. verify inverter cannot backfeed an unintended circuit.

Only after bench validation should the module enter a closed-course Mule.

---

# 15. Current recommendation

### Prototype 1

**Preferred architecture:**

- dedicated **~3-kW traction-HV -> 120-V/60-Hz isolated inverter**;
- Rawsuns RDA350-120-3KW as first supplier RFQ;
- Nanjing Pengtu 3-kW 350-V/120-V listing as alternate/price lead;
- Bel 350INV60 as engineering benchmark, not cost target;
- Lincoren as alternate Chinese engineering conversation for a North-American output version;
- one or more protected vehicle AC receptacles;
- physical utility-power enable;
- no infotainment/cloud dependency.

### Later

Preserve pack/PDU/charging interfaces for:

- 120/240-V higher-power export;
- bidirectional OBC;
- J3400 V2L/V2V where useful;
- V2H/V2G/DER integration after the applicable SAE/IEEE/UL ecosystem and engineering requirements are deliberately addressed.

The governing principle is simple:

> **A Mule should be able to run useful equipment because it is a utility vehicle—not because a cloud service granted permission.**
