# Alibaba source mission closeout

Closeout date: **2026-08-31**

This file marks the engineering boundary between the first VolksMule Alibaba/Chinese-supplier sourcing mission and the next supplier-document / vehicle-integration mission.

It exists so future work does not accidentally return to endless marketplace browsing after the sourcing questions have already been answered.

> **Alibaba has done its first job. The next missing information lives with suppliers or in our own engineering.**

---

## 1. Mission question

The original mission was effectively:

> Follow the Prototype 1 roadmap/checklist and determine whether the required vehicle systems can be sourced through Alibaba / Chinese supplier ecosystems, what supplier families are credible, what should be bought versus adapted/designed, and where marketplace hardware is the wrong answer.

That mission is now complete enough to stop.

---

## 2. What has been established

Dedicated sourcing screens now exist for all major Prototype 1 BUY / DONOR / ADAPT categories, including:

- e-axles;
- onboard charger / DC-DC / PDU;
- J3400 charging communication and inlet architecture;
- automotive BMS;
- LFP cells/modules;
- HV contactors / fuse / HVIL / MSD / connectors / isolation monitoring;
- thermal / HVAC;
- steering / EPS;
- friction brakes / ABS / ESC;
- suspension corners / hubs / springs / dampers;
- windshield/glazing / lights / mirrors / wipers / rear visibility;
- seats / belts / airbags / restraint-system sourcing boundary;
- wheels / tires / spare / recovery;
- doors / latches / handles / seals / body controls;
- accelerator / selector / key / cluster;
- 12-V wiring / CAN / diagnostics / VCU boundary;
- required safety automation;
- V2L / utility AC power;
- structure / cradle / battery-enclosure fabrication strategy.

The sourcing mission also established where **not** to use generic marketplace hardware:

- safety-cell geometry;
- mixed restraint components;
- generic ABS/ESC units without calibration support;
- ESS BMSs presented as EV BMSs;
- generic airbags;
- solar/ESS inverter hardware on the road-vehicle traction bus without automotive evidence;
- undocumented central vehicle controllers;
- overseas fabrication of geometry-changing Mule #1 weldments before CAD stabilizes.

---

## 3. Supplier ecosystem verdict

A credible supplier ecosystem exists for essentially every solved subsystem needed by Prototype 1.

Current high-impact supplier leads include:

- **REPT BATTERO** — automotive BEV LFP cells;
- **EVE** — secondary cell-manufacturer path;
- **Rawsuns** — READ-series e-axles and RDA-series utility inverter;
- **Sumcont** — alternate integrated drive-unit path;
- **Dilong** — OBC / DC-DC / PDU families;
- **MIDA / RNL** — EVCC / PLC / ISO 15118 charging controller;
- **Phoenix Contact** — J3400 inlet benchmark;
- **Hongfa** — automotive HV contactors;
- **Yonggui** — HV connectors / MSD / HVIL / high-voltage boxes;
- **Chilye** — alternate Alibaba-accessible HV interconnect / MSD path;
- **Ligoo** — strongest current road-intent BMS lead;
- **Suzhou Miaoyi / Mewyeah** — Alibaba-native motive-power BMS alternate;
- **Aotecar** — EV compressor / thermal-system components;
- **NF / EVLINK-class suppliers** — HV coolant/PTC heaters;
- **Zhuzhou Elite** — EPS;
- **APG / WBTL-Bethel-class suppliers** — vehicle-calibrated brake/ESC path;
- **Songyuan / Jinheng** — integrated restraint-system supplier path;
- **Wayou / Jieou** — accelerator pedal and physical selector;
- relevant Tier-1 / IATF supplier families for hubs, springs, dampers, glazing and conventional hardware.

This is a supplier map, not a final BOM.

---

## 4. Revision-A public-data mining completed after the broad sourcing audit

After broad marketplace discovery reached diminishing returns, the mission continued long enough to convert public manufacturer data into realistic Revision-A packaging inputs.

Current focused Revision-A screens now include:

- whole-vehicle interface envelopes;
- common windshield candidates;
- READ2982 front-drive-unit envelope;
- conservative rear-e-axle envelope;
- MIDA EVCC envelope;
- steering / EPS envelope;
- occupant / manual-seat envelope;
- REPT cell mechanical envelope;
- SAE J3400 inlet envelope;
- automotive BMS physical envelope;
- thermal / HVAC packaging envelope;
- brake-corner envelope;
- transparent BDU / PDU envelope.

Useful public-data blockers reduced include:

- actual J3400 inlet dimensions and lock/manual-release behavior;
- actual 150-Ah REPT compression requirements and compressed dimensions;
- e-axle road-speed compatibility checks;
- realistic BMS controller volume;
- realistic thermal-module/chiller/compressor volume;
- realistic compact-SUV brake rotor conflict envelopes;
- realistic contactor/fuse/IMD/MSD classes and BDU space.

---

## 5. Important engineering conflicts discovered

The mission did more than find parts. It exposed architecture questions early.

### Rear e-axle speed

READ2624's published 10,000-rpm limit is too restrictive as a permanently coupled rear unit across much of the current 28–34-in tire envelope.

Revision A therefore carries READ2982-sized rear packaging until coast-drag/disconnect data proves a smaller rear unit is worth the compromise.

### BMS is not zero-volume

A centralized 120S-class controller can consume roughly a 400 × 160 × 60-mm component envelope before service/harness allowance. Distributed automotive BMS remains attractive but needs supplier CAD.

### Thermal integration can fit without a thermal octopus

Aotecar-class integrated thermal hardware fits comfortably at the vehicle scale, but a luxury four-zone cabin HVAC box is explicitly unnecessary for a simple two-seat Mule.

### Brake clearance may decide 16 versus 17 in wheels

Revision A carries up to ~320-mm front / ~310-mm rear rotor conflict envelopes. Study 16-in wheels first; use 17 in if validated brake/caliper clearance requires it.

### Pack-current architecture needs reconciliation

The detailed REPT 150-Ah baseline publicly documents less continuous cell current than would be needed to exploit both READ2982 units at their combined rated power in a simple 120S1P arrangement.

This means final engineering must reconcile at least one of:

- higher-power 171-Ah or alternate cell data;
- parallel cell/string architecture;
- intentional continuous-power limits;
- different cell/module selection.

Do **not** freeze the main fuse/contactor rating until that is resolved.

---

## 6. What public browsing can no longer answer reliably

The remaining high-value gaps are supplier-controlled or vehicle-engineering-controlled.

### Supplier-controlled data

Need original documents for exact quoted revisions, including:

- **Rawsuns READ2982** — STEP/CAD, mounting points, output/CV spline geometry, centerlines, coolant ports, inverter/HV range, CAN/DBC, coast/drag/overspeed data;
- **rear e-axle options** — equivalent CAD plus inactive/coast/disconnect behavior;
- **REPT 171-Ah** — full application specification, compression, terminals, venting, cooling face, current limits, life/thermal data;
- **Ligoo / Miaoyi BMS** — master/slave CAD, CAN/DBC, contactor/precharge/HVIL/isolation responsibilities, local service/reflash;
- **Dilong** — exact 2-in-1 / 3-in-1 revision CAD, PDU topology, CAN, current ranges, serviceability;
- **MIDA** — exact J3400 revision, drawing/STEP, CAN/DBC, interoperability evidence, offline configuration/recovery;
- **Yonggui / Chilye** — exact connector/MSD CAD and application data;
- **Hongfa** — final contactor application recommendation after current/fault profile;
- **Aotecar** — current E-series compressor CAD and simple two-seat/single-zone HVAC-box options;
- **Zhuzhou Elite** — rack/EPS CAD and calibration/interface package;
- **Wayou/Jieou** — pedal/selector drawings and signal interfaces;
- road-intent brake/ESC and restraint suppliers — vehicle-development/calibration requirements.

More generic web searching cannot substitute for these files.

### VolksMule engineering data

Need our own work for:

- actual axle loads;
- CG height;
- suspension hard points;
- brake-force/thermal calculations;
- battery current/fault study;
- pack cell/string architecture;
- BDU branch/fuse/contactors final ratings;
- first whole-vehicle packaging CAD;
- crash/restraint integration;
- final tire/wheel/hub geometry;
- vehicle control state machines;
- FMVSS validation plan.

---

## 7. Supplier outreach has NOT happened yet

As of this closeout:

> **No Wave-1 supplier outreach has been sent.**

GitHub Issue #28 remains the campaign tracker and its supplier-contact items remain unchecked.

This is intentional. The source mission was allowed to finish before opening supplier conversations so the requests could be informed, consistent and complete.

The paste-ready technical request package is already stored in:

- [`ALIBABA_RFQ_WAVE1.md`](ALIBABA_RFQ_WAVE1.md)

The first purpose of outreach is **engineering documents**, not price negotiation or large component purchases.

---

## 8. Recommended outreach order

Start with the suppliers that unblock the greatest amount of packaging/electrical work.

### Wave 1A — architecture blockers

1. **Rawsuns** — READ2982 CAD/application package + rear-drive alternative + RDA350 utility-inverter documentation.
2. **REPT BATTERO** — 171-Ah and 150-Ah full automotive application packages.
3. **Dilong** — 2-in-1 OBC/DC-DC and 3-in-1 PDU documentation.
4. **MIDA / RNL** — J3400 EVCC CAD/interface/interoperability package.
5. **Ligoo / Miaoyi** — automotive BMS mechanical/interface packages.

### Wave 1B — HV safety plumbing

6. **Yonggui / Chilye** — connector/MSD/HVIL application packages.
7. **Hongfa** — contactor application recommendation after supplying our provisional voltage/current/fault envelope.

### Wave 1C — chassis/direct driver interfaces

8. **Zhuzhou Elite** — EPS/rack package.
9. **Wayou/Jieou** — accelerator/selector package.
10. Brake/ESC and restraint suppliers once the first vehicle hard points/mass model can support a meaningful vehicle-level discussion.

Rawsuns is first because the missing drive-unit geometry currently blocks front/rear cradle, CV, suspension and service-removal packaging simultaneously.

---

## 9. Sample-buy rule remains unchanged

Do not buy major hardware just because the sourcing mission is closed.

Samples only after the applicable document gate clears.

Likely early low-risk samples may include:

- a few verified automotive cells;
- accelerator pedal / physical selector;
- HV connectors / MSD / contactors;
- selected thermal pumps/valves/heater;
- development BMS hardware;
- utility inverter only after its public specification discrepancy is resolved.

Large items such as e-axles wait until CAD proves they belong.

---

## 10. Definition of done

The Alibaba source mission is complete when all of these are true:

- every Prototype 1 sourcing category has been screened;
- credible supplier families or intentional DESIGN paths exist;
- known marketplace traps are documented;
- public manufacturer data has been mined far enough to create useful Revision-A envelopes;
- remaining high-value unknowns require supplier-original data or VolksMule engineering;
- supplier outreach questions are already prepared;
- no purchase is being forced by lack of research.

All of those conditions are now met.

---

# Closeout verdict

> **ALIBABA SOURCE MISSION: COMPLETE**

The next mission is not more sourcing archaeology.

It is:

> **Supplier-document outreach → replace provisional boxes with original CAD/interfaces → build the first integrated packaging model.**

Alibaba remains an active supplier channel and price/supply reference throughout the project, but broad discovery is no longer the critical path.
