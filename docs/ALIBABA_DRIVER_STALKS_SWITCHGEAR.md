# Alibaba driver stalks and switchgear screen

Research date: **2026-09-01**

This document closes the sourcing-architecture question around Prototype 1's steering-column stalks and nearby physical switchgear.

The existing project rule remains:

> **Buy solved mechanisms. Own the body interface and the control logic.**

And, more importantly:

> **The computer does not own the vehicle.**

The objective is not to reproduce a modern multifunction steering-column control module. It is to obtain durable, ordinary automotive human controls for turn signals, lighting and wipers without importing an unnecessary proprietary body computer or network dependency.

---

## 1. Functional split

### Left stalk

Preferred functions:

- turn signal left / right;
- high beam / low beam command;
- momentary headlamp flash.

Possible later functions only if they remain simple:

- front fog lamp command if fog lamps are fitted.

Do not add cruise, audio, phone, menu navigation or unrelated convenience controls merely because a donor stalk contains them.

### Right stalk

Preferred functions:

- front wiper OFF / intermittent / low / high as the final wiper system supports;
- front washer momentary command;
- rear wiper / washer only if rear-glass geometry and rear visibility justify it.

### Hazard switch

The hazard warning switch should **not** be buried in a stalk function.

Carry a separate, dedicated and visually obvious physical hazard button on the dashboard / center control area.

This preserves immediate operation independent of steering-wheel position and keeps one of the most important emergency controls obvious to any driver.

---

## 2. Electrical architecture — the stalk is a command device, not the body computer

Preferred signaling order:

1. **discrete low-current contacts**;
2. **documented passive resistor ladder** if it meaningfully reduces wiring;
3. **documented LIN/CAN** only if a complete switch family clearly wins on packaging, durability or availability and VolksMule owns the interface documentation.

The stalk assembly should command transparent downstream logic rather than directly become the owner of vehicle functions.

Examples:

- turn stalk -> VolksMule-owned flasher / lighting logic -> lamp outputs;
- high-beam command -> relay / protected output -> compliant headlamp module;
- wiper command -> relay or documented local speed controller -> wiper motor;
- washer command -> ordinary relay / output -> washer pump.

The wiper motor's self-park behavior should remain local and understandable.

### Why low-current contacts are preferred

A low-current command layer lets the final switch survive without carrying every lamp or motor load through delicate stalk contacts. It also permits:

- standard relays / replaceable output modules;
- easier fault isolation;
- simple alternate switches;
- thinner steering-column wiring;
- future substitution without redesigning the complete vehicle network.

---

## 3. ChuangJia / ChonKia — current first supplier-family study

The project has already screened **ChuangJia / ChonKia** as an automotive mechanism manufacturer covering:

- door locks;
- handles;
- window regulators;
- ignition locks;
- automotive combination switches.

The company's current material describes automotive combination switches integrating functions such as turn signal, wiper and lighting control and states an IATF 16949 automotive-production basis.

Manufacturer reference:

- https://www.chonkia.com/
- https://www.chonkia.com/products/combination-switches/

### Why it fits

This family is attractive because VolksMule already has a reason to understand the manufacturer for other simple body mechanisms. If the same supplier can provide a durable, electrically transparent combination-switch family, it reduces supplier discovery without forcing functional integration.

### Current status

> **CARRY supplier family / exact switch OPEN.**

Do not choose an application-specific switch until the column, connector and signaling requirements exist.

---

## 4. Zhejiang Jinhao — strong alternate manufacturer benchmark

**Zhejiang Jinhao Auto Parts** currently presents a dedicated automotive switch portfolio including:

- turn-signal switches;
- combination switches;
- ignition switches;
- power-window switches;
- lock assemblies.

The company states:

- OE-manufacturer development support;
- IATF 16949 production for original equipment;
- ISO 9001 aftermarket production;
- more than 500 product models;
- in-house R&D / product development and inspection capability.

Reference:

- https://zjjhparts.com/

### VolksMule use

Jinhao is a good alternate for:

- an existing simple application switch that happens to fit;
- a manufacturer-level electrical / durability benchmark;
- potential custom low-volume switch development later if exact geometry warrants it.

Again, supplier claims are a starting point for document verification, not qualification by themselves.

---

## 5. Zhejiang Wanchao — road-intent combination-switch benchmark

**Zhejiang Wanchao Electric** provides another useful benchmark for what a real automotive combination-switch manufacturer looks like.

Current manufacturer material describes:

- automotive combination switches;
- ignition locks;
- function switches;
- body controllers and related vehicle electronics;
- production dating to 1991;
- IATF 16949 certification history;
- supply relationships with Chinese vehicle manufacturers.

References:

- https://zj-wanchao.en.made-in-china.com/product/ZdPfWBRDEUhc/China-FAW-Car-Parts-Combination-Wiper-Switch-Using-in-Dfsk-F507L.html
- https://zj-wanchao.en.made-in-china.com/product/odcaCBwbStfq/China-for-Hyundai-Elantra-Auto-Parts-Combination-Switch-93410-2D110.html

Wanchao is useful mainly as an **automotive-quality benchmark / alternate manufacturer path**. Its portfolio also illustrates the exact architectural danger VolksMule is avoiding: combination-switch suppliers increasingly offer body controllers, PEPS, electronic steering-column locks and networked integration as one ecosystem.

Those capabilities may be useful to other vehicles. They do not need to become VolksMule dependencies.

---

## 6. Alibaba market depth — sourcing is not the blocker

Alibaba currently exposes a large market for:

- combination wiper / turn-signal switches;
- separate 12-V / 24-V wiper controls;
- OEM-replacement steering-column stalks;
- truck / commercial-vehicle combination switches;
- simple multi-position rotary and rocker wiper controls.

Current category references:

- https://www.alibaba.com/countrysearch/CN/combination-switch-assembly.html
- https://autopart.alibaba.com/product/switch-assy-combination
- https://autopart.alibaba.com/product/universal-wiper-switch

Many listings are inexpensive and available at low MOQ.

That proves the mechanism class is commoditized. It does **not** mean the cheapest application-specific replacement stalk should define the vehicle.

The actual selection problem is interface quality:

- physical mounting;
- return / cancel mechanism;
- detent quality;
- contact logic;
- environmental durability;
- connector availability;
- service replacement depth.

---

## 7. Turn-signal cancellation

Prototype 1 should retain ordinary automatic turn-signal cancellation after completing a steering maneuver.

Preferred approaches:

1. mechanical cancellation cam / ring integral to the column / switch family;
2. a documented, mechanically simple cancellation interface that VolksMule can reproduce.

Avoid making turn-signal cancellation dependent on infotainment or cloud software.

If a final switch uses an electronic cancellation strategy based on steering-angle data, it must still be deterministic, locally diagnosable and documented; mechanical cancellation remains the simplicity baseline.

---

## 8. Clock spring / steering-angle / airbag separation

The stalk decision must not accidentally freeze:

- steering-wheel airbag electronics;
- steering-angle sensor;
- clock spring;
- steering-wheel buttons;
- restraint-system supplier.

Modern donor columns often bundle these systems physically.

VolksMule should therefore prefer a stalk assembly that can be mounted around the column while keeping:

- restraint wiring;
- clock spring;
- steering-angle sensing;
- EPS / column mechanics

as independently defined interfaces.

A donor switch that only works when attached to its proprietary steering-column control module is a poor baseline even if the stalk itself feels excellent.

---

## 9. Contact-load strategy

Do not require a stalk to directly switch every downstream load.

Before exact selection, document:

- contact current rating at 12 VDC;
- inductive-load rating where relevant;
- minimum switching current if signals feed electronics;
- contact material;
- expected cycle life;
- connector terminal rating;
- transient protection requirements.

Prefer to use the stalk as a low-current input to relays / protected outputs for:

- headlamps;
- wiper motor speed selection;
- washer pump;
- other meaningful inductive loads.

This makes replacement switches easier to substitute and keeps electrical heat out of the steering column.

---

## 10. Environmental / durability gates

Any road-intent stalk family must eventually provide or survive validation for:

- automotive cabin temperature range;
- vibration;
- humidity / condensation;
- dust contamination;
- switch-cycle life;
- detent retention over life;
- contact resistance over life;
- connector retention;
- chemical exposure from hand oils / cleaners;
- labeling wear;
- abnormal electrical loads / transients appropriate to its interface.

A seller listing saying “OEM quality” is not enough.

---

## 11. What to reject

Reject a candidate if it requires:

- proprietary BCM authorization merely to operate lamps or wipers;
- undocumented CAN / LIN messages;
- a donor steering-column control module with unrelated vehicle functions;
- cloud / VIN coding for ordinary replacement;
- an inseparable clock-spring / airbag / steering-angle architecture unless the complete system has independently earned its place;
- capacitive / touch controls for turn signals or wipers;
- cruise / audio / menu complexity with no Prototype-1 job;
- a unique connector that cannot be sourced separately.

---

## 12. Current interface target

The first wiring / column study should assume:

### Left stalk inputs

- TURN_LEFT;
- TURN_RIGHT;
- HIGH_BEAM_LATCH or LOW/HIGH state as final switch defines;
- HIGH_BEAM_FLASH momentary.

### Right stalk inputs

- WIPER_OFF;
- WIPER_INT;
- WIPER_LOW;
- WIPER_HIGH;
- WASH_FRONT momentary;
- REAR_WIPER / REAR_WASH only if retained.

### Separate dash input

- HAZARD.

These are logical requirements, not mandated connector pins. The exact switch may encode them using discrete contacts or a documented passive network.

---

## 13. Supplier questions — hold for later outreach

Supplier outreach remains intentionally deferred.

When geometry and electrical interfaces are mature, ask the surviving ChuangJia / Jinhao / Wanchao-class candidates for:

1. exact mechanical drawing / CAD;
2. steering-column mounting dimensions;
3. cancellation-cam interface;
4. complete connector and pinout;
5. discrete / resistor / LIN / CAN signaling method;
6. protocol documentation if networked;
7. contact ratings and load type;
8. electrical and mechanical cycle-life data;
9. temperature / vibration / humidity qualification;
10. connector manufacturer and mating connector;
11. IATF certificate for the manufacturing site;
12. sample MOQ;
13. production and replacement horizon;
14. whether the same functions can be supplied without a proprietary steering-column control module.

No supplier message needs to be sent during this mission pass.

---

# Current verdict

### Driver stalk architecture

> **CARRY — physical dual-stalk architecture.**

- left: turn + high/low/flash;
- right: wiper + washer;
- rear wiper optional only if useful;
- hazard: dedicated separate dash button.

### Electrical interface

> **CARRY — discrete / passive low-current command layer first.**

Documented network signaling is allowed only if it genuinely improves the vehicle and remains locally owned and replaceable.

### Supplier path

> **CARRY ChuangJia / ChonKia as first existing project family; carry Jinhao and Wanchao as alternate automotive-manufacturer benchmarks.**

### Exact part

> **OPEN.**

Blocked legitimately on:

- steering-column outside diameter / mounting geometry;
- turn-cancel interface;
- clock-spring / restraint / steering-angle layout;
- wiper system command requirements;
- lamp-output architecture;
- connector / harness packaging.

This is no longer a sourcing gap. It is a geometry and interface-definition task.
