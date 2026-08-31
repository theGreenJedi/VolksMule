# Alibaba Phase-7 12-V service hardware — make the electricity boring

Research current as of **2026-08-31**.

This document continues the roadmap-driven sourcing mission into:

> **Phase 7 — Make the electricity behave.**

This pass deliberately covers the ordinary low-voltage hardware around the previously defined 12-V/CAN architecture:

- fuse and relay centers;
- standard fuses and relays;
- sealed connectors;
- physical switchgear;
- keyed ignition/start authorization hardware;
- windshield wiper/washer hardware;
- horn;
- ordinary service wiring accessories.

The guiding rule is simple:

> **A 12-V electrical system should be understandable with a wiring diagram, a multimeter and ordinary hand tools.**

The computer does not own the vehicle.

---

## 1. Fuse and relay distribution

### Architecture

Prototype 1 should use passive, visible power distribution wherever practical:

- standard ATO/ATC/MINI/MAXI-style blade fuses as appropriate;
- ordinary replaceable automotive relays for suitable switched loads;
- labeled fuse/relay positions;
- removable cover with a printed map;
- accessible test points;
- separately serviceable high-current prefuses where appropriate;
- no mandatory software session merely to replace a fuse or relay.

A smart solid-state PDM is not forbidden, but it must prove a whole-vehicle advantage before replacing simple hardware.

### Alibaba market

Alibaba currently exposes more than **1,200 automotive fuse/relay-box products**.

Current low-MOQ examples include:

- Wenzhou Daiertek 6-way fuse/relay boxes;
- Yueqing Daier waterproof 6-way boxes;
- Dongguan Onegol 11-way waterproof ATC/ATO boxes at MOQ 1;
- Yueqing Chunqiao prewired 4-relay / 6-fuse boxes at MOQ 1;
- IATF-claimed OEM-style battery-terminal fuse boxes and related distribution components.

The useful lesson is not that one of these exact boxes should be frozen now. It is that passive automotive power distribution is inexpensive and deeply multi-sourced.

### Verdict

> **BUY commodity / layout remains VolksMule-owned.**

Carry two service zones rather than one giant body computer:

1. front/under-hood power distribution for pumps, fans, horn, wipers, lighting and chassis loads;
2. cabin/body fuse/relay zone for keyed power, cluster, HVAC controls, accessory outlets and ordinary body loads.

Final circuit count follows the wiring diagram.

Sources:

- https://www.alibaba.com/showroom/automotive-fuse-and-relay-box.html
- https://www.alibaba.com/wholesale/fuse-box-8-way-relay.html

---

## 2. Standard relays and fuses

Use recognizable service components where the duty allows it.

### Relays

Prefer common ISO-style automotive relay footprints for ordinary loads.

For each circuit verify:

- continuous current;
- inrush;
- inductive suppression;
- coil voltage/current;
- contact life;
- operating temperature;
- sealed versus cabin location;
- normally-open / normally-closed requirements.

Do not use a relay merely because its plastic case says 40 A.

### Fuses

Fuse sizing follows conductor ampacity, fault energy and load behavior—not the nominal load sticker alone.

Prefer a small number of common fuse families rather than a unique fuse type for every current range.

### Verdict

> **GREEN commodity. Buy by electrical specification and traceability, not logo/color.**

---

## 3. Sealed low-voltage connectors

### Architecture rule

VolksMule should intentionally standardize on a small connector vocabulary.

Likely classes:

- small sealed 2–6-way sensor/actuator connectors;
- medium sealed DT/Superseal-class connectors for ordinary under-hood loads;
- higher-current dedicated connectors where required;
- unsealed interior connectors only where the environment justifies them.

Alibaba currently has deep supply in TE/AMP Superseal-compatible and Deutsch DT/DTM-style families, including supplier/manufacturer pages with automotive/IATF claims and drawing-based harness capability.

### Sourcing rule

For safety-critical or high-consequence interfaces, the connector specification matters more than visual compatibility.

Require:

- exact terminal material/plating;
- current derating versus temperature;
- wire-size range;
- seal material;
- mating-cycle rating;
- terminal retention;
- IP/environmental qualification;
- genuine mating geometry;
- traceable terminals and crimp tooling.

A shell that merely resembles a Deutsch or Superseal connector is not sufficient evidence.

### Verdict

> **BUY standardized families. Alibaba is useful for harness/connector sourcing, but the interface specification stays ours.**

---

## 4. Physical switchgear

Pete's HMI preference and project canon are aligned:

- knobs;
- stalks;
- levers;
- rocker/toggle switches;
- tactile buttons;
- no touchscreen monopoly over basic functions.

Alibaba has an enormous inexpensive switch ecosystem. Current Daier/Daiertek examples include IP65/IP67/IP68 rocker and toggle switches, momentary center-off types and 12-V automotive/marine products with published mechanical-life ratings.

### Important boundary

Cheap physical does not automatically mean automotive-suitable.

#### Appropriate uses for robust commodity switches

- work lights;
- utility/V2L enable request;
- optional accessory circuits;
- service functions;
- auxiliary fan/pump manual test functions;
- recovery/service overrides where intentionally designed.

#### Higher evidence bar

For routine driving/visibility functions prefer a documented automotive switch or common donor family for:

- hazards;
- headlamp/beam control;
- turn-signal stalk;
- wiper/washer stalk;
- defrost;
- drive selector;
- keyed RUN/READY state.

These must remain tactile even if their electrical output is interpreted by a local controller.

### Reject

Generic marine-style multi-gang panels with USB chargers, voltmeters, RGB lighting and decorative labels are not a dashboard architecture merely because they are cheap.

### Verdict

> **BUY physical switchgear; use commodity rockers/toggles for suitable auxiliaries and automotive/donor switch families for core driving/visibility controls.**

Sources:

- https://www.alibaba.com/product-detail/DaierTek-Mini-Blue-Led-Rocker-Switch_1601154096395.html
- https://www.alibaba.com/product-detail/DPDT-Momentary-Toggle-Switch-3Way-ON_1601191582963.html
- https://www.alibaba.com/product-detail/12V-DPDT-Momentary-3-Position-Rocker_1601207231879.html

---

## 5. Physical keyed ignition / RUN authorization

The baseline remains:

> **LOCK/OFF → ACC → RUN/READY**

An EV does not need a spring-return START/crank position unless the chosen switch family includes it and we deliberately repurpose/ignore it.

Alibaba currently exposes conventional keyed automotive ignition switches and lock cylinders at very low unit prices. Current sourcing pages identify:

- Guangzhou Jinbiao Auto Parts — OEM-style Toyota/Nissan switch families with IATF 16949 / ISO 9001 claims;
- Secutor Corporation — long-running lock-cylinder / ignition-barrel specialist;
- multiple Chinese suppliers for ignition lock/key sets and starter switches.

### Preferred architecture

Separate concepts where practical:

1. mechanical key/lock cylinder;
2. electrical ignition switch;
3. local immobilizer/start-authorization logic only if required;
4. VCU safety checks before READY.

The key requests power/state. It does not directly energize the HV contactors without the normal safety chain.

### Service rule

A failed lock cylinder or electrical switch should be replaceable without:

- a phone;
- cloud authorization;
- infotainment;
- a subscription.

### Verdict

> **BUY/ADAPT a common physical keyed automotive switch family. No proximity-fob system is required.**

Source:

- https://autopart.alibaba.com/product/car-ignition-switch-with-key

---

## 6. Windshield washer system

A washer system is a solved commodity and should remain one.

Alibaba currently exposes many 12-V pumps around common Honda, Nissan, Toyota, Ford, Hyundai and other OEM fitments. Current supplier paths include:

- Ruian Lianzheng Autoparts Factory — washer pumps/nozzles/motors, current North-American sales exposure;
- Qeepei Auto — broad OEM-reference washer-pump catalog;
- Suzhou Aopec — common 12/24-V washer pumps alongside automotive relays/electrical components.

### Preferred architecture

Use a common grommet-mounted OEM-style pump and a simple molded reservoir.

The reservoir can be:

- donor/common vehicle part if packaging works;
- generic automotive reservoir;
- later drawing-based molded/fabricated part if necessary.

Do not create a unique pump interface.

### Verdict

> **BUY common pump/nozzles; ADAPT reservoir/hoses to body packaging. Prefer a locally cross-referenceable OEM pump.**

Sources:

- https://www.alibaba.com/wiper-washer-pump-suppliers.html
- https://www.alibaba.com/windscreen-washer-pump-suppliers.html

---

## 7. Wiper motor and linkage

The wiper system should be paired with the eventual common windshield geometry.

Alibaba currently exposes a broad supply of conventional 12-V passenger-car wiper motors. **Wenzhou Huihai Auto Parts Co., Ltd.** currently lists multiple OEM-reference 12-V motors for Nissan, Renault, Dodge/Jeep and other applications, with reported North-American market exposure.

### Preferred order

1. Once the windshield family is selected, find an existing vehicle's wiper motor/linkage/arms whose sweep fits the glass.
2. ADAPT mounting brackets if needed.
3. Retain common replaceable blades and arm attachments.
4. Use a custom linkage only if a common assembly cannot meet wipe area/packaging requirements.

Do not design a unique wiper motor.

### Verdict

> **DONOR/BUY complete known wiper motor/linkage family after windshield selection. Alibaba can provide inexpensive initial/replacement assemblies, but local interchange remains important.**

Source:

- https://www.alibaba.com/12v-dc-wiper-motor-specification-suppliers.html

---

## 8. Horn

The horn is a perfect example of a component that should never become architecture.

Alibaba has thousands of 12-V automotive horns, including waterproof disc/snail horn products. Current suppliers include Zhejiang Alpex, Guangzhou Lukasi, Yueqing Chsky and others.

### Requirement

Use a conventional legal road horn with:

- ordinary 12-V relay control;
- replaceable two-wire or similarly simple connection;
- corrosion-resistant bracket;
- no programmable novelty-sound dependency.

A common Hella/FIAMM/Denso-style local replacement may ultimately be more sensible than importing the production part.

### Verdict

> **GREEN commodity. Alibaba may win prototype price; local availability likely wins final service strategy.**

Sources:

- https://www.alibaba.com/horn-12-v-suppliers.html
- https://www.alibaba.com/countrysearch/CN/automobile-horn.html

---

## 9. 12-V battery

Do not overthink this.

Prototype 1 should use a conventional, locally available replaceable 12-V battery sized after LV load/crank-equivalent transient and sleep-current studies.

Alibaba sourcing offers little strategic advantage because:

- batteries are heavy to ship;
- local warranty/service matters;
- multiple North-American group sizes are ubiquitous;
- the whole point is easy field replacement.

### Verdict

> **BUY LOCAL. Alibaba not preferred.**

Exact group size remains packaging-dependent.

---

## 10. 12-V wiring accessories

Alibaba is appropriate for commodity production hardware once specifications exist:

- corrugated conduit;
- braided sleeving;
- heat shrink;
- adhesive-lined heat shrink;
- grommets;
- sealed splice components;
- P-clamps;
- harness clips;
- label sleeves;
- fuse pullers;
- relay sockets;
- terminal boots;
- ring terminals where properly specified/crimped.

But the harness itself should be built from VolksMule-owned drawings and wire tables.

### Rule

> **Harness manufacturing may be outsourced. Harness knowledge may not be.**

---

# 11. Phase-7 12-V shortlist

| Function | First path | Verdict | Freeze now? |
|---|---|---|---|
| Fuse/relay centers | Daier/Daiertek/Onegol/automotive-equivalent passive boxes | BUY | circuit count first |
| Blade fuses / ISO relays | standardized automotive families | BUY | ratings per circuit |
| Sealed LV connectors | DT/DTM/Superseal-class standardized set | BUY | connector vocabulary can be narrowed now; exact cavities later |
| Auxiliary switches | Daier/Daiertek-class IP-rated physical switchgear | BUY | function-specific later |
| Core stalks/hazard/wiper controls | common automotive/donor family | DONOR / BUY | steering-column/dashboard geometry first |
| Keyed ignition | common IATF/OEM-style physical key switch | BUY / ADAPT | lock/column packaging first |
| Washer pump | common OEM-fitment 12-V pump | BUY | windshield/reservoir packaging later |
| Wiper motor/linkage | common donor family paired to windshield | DONOR / BUY | windshield choice first |
| Horn | ordinary waterproof 12-V road horn | BUY / local-first | can select late |
| 12-V battery | local common group size | BUY LOCAL | LV load/space first |
| Harness clips/sleeving/grommets | drawing/spec-driven commodity | BUY | during harness design |

---

# 12. Architecture traps this pass rejects

- giant smart PDM controlling every body function without a compelling reason;
- proprietary solid-state fuse boxes that require vendor software for basic service;
- dozens of unrelated connector families;
- cheap illuminated marine panels becoming the dashboard;
- push-to-start/proximity hardware added merely because modern cars have it;
- unique washer pump/reservoir interfaces;
- unique wiper motor;
- programmable novelty horn as required road equipment;
- imported 12-V battery dependency;
- undocumented harnesses.

---

# 13. Roadmap consequence

The ordinary 12-V side is not a sourcing risk.

We can make it:

- cheap;
- locally serviceable;
- visually traceable;
- multi-sourced;
- owner-diagnosable;
- independent of infotainment/cloud.

That is exactly what this subsystem should be.

---

# 14. Next sourcing move

With Phase 5 chassis, Phase 6 drive support and the ordinary Phase 7 service hardware screened, the next useful artifact is no longer another isolated subsystem note.

Build a **roadmap sourcing BOM skeleton** that lists every Prototype-1 subsystem and records:

- requirement;
- sourcing mode (BUY / DONOR / ADAPT / DESIGN);
- preferred Alibaba/Chinese supplier path;
- local/North-American alternate;
- current candidate family;
- exact blocker before SKU selection;
- likely sample stage;
- serviceability/interchange requirement;
- regulatory/safety gate.

That BOM skeleton becomes the checklist we can continue filling as the roadmap matures—without contacting suppliers yet.