# Alibaba body controls, doors, latches, and physical HMI

This document records the Prototype 1 sourcing screen for body controls, door mechanisms, latches, handles, hinges, weather sealing, and physical driver controls.

It follows two VolksMule rules:

> **Buy solved mechanisms. Own the body interface and the control logic.**

> **The computer does not own the vehicle.**

## Executive verdict

### Physical controls — GREEN

Alibaba and the broader Chinese automotive supplier ecosystem are strong sources for:

- rotary knobs and selectors;
- rocker and toggle switches;
- tactile push buttons;
- stalk-style switch assemblies;
- indicator lamps;
- waterproof switch panels;
- fuse / relay hardware;
- harness connectors;
- local body-control modules where documentation is available.

There is no engineering need to make Prototype 1 touchscreen-first merely to reduce switch count.

### Door locks / latches / handles — YELLOW to GREEN with qualification

Door mechanisms are mature and sourceable, but door retention is safety-regulated. FMVSS 206 covers door locks and door-retention components, including latches and hinges, with the purpose of reducing occupant-ejection risk.

Generic marketplace replacement parts are useful for donor and bench work. Road-intent parts should come from actual automotive suppliers that provide engineering drawings, material and coating specifications, durability data, load data, traceability, and vehicle-program support.

### Door hinges — YELLOW

Hinges are mechanically simple but structurally significant. Door mass, hinge spacing, sag, corrosion, crash deformation, and the body-side reinforcements remain vehicle-level engineering responsibilities.

### Weather seals — GREEN

Automotive bulb seals, pinch-weld seals, flocked glass-run channels, door aperture seals, and molded corner pieces are mature commodity products. Prefer profiles with broad supplier availability and simple attachment geometry.

## Baseline convenience philosophy

Prototype 1 does **not** require power windows or power locks.

The default study architecture is:

- manual window regulators / crank handles;
- mechanically keyed exterior entry;
- mechanical interior lock / unlock;
- mechanical interior door release;
- cable or rod linkage where practical;
- powered convenience features only when they win on total cost, packaging, reliability, or sourcing without adding a dependency.

This is a preference, not a prohibition. If an inexpensive powered mechanism is genuinely simpler as a complete system, it may still win.

An additional benefit is regulatory simplicity: FMVSS 118 is specifically the standard for **power-operated** window, partition, and roof-panel systems. Manual side windows avoid that power-window actuation layer. FMVSS 206 still governs the door lock/latch/hinge retention system, but does not require the locking mechanism to be electrically powered.

## Physical HMI architecture

Prototype 1 should have a tactile, glance-light control environment.

### Frequent controls should be physical

Prefer dedicated physical controls for:

- headlights / exterior lighting;
- turn signals;
- hazards;
- front and rear wipers / washers;
- temperature;
- blower speed;
- vent / defrost mode;
- heated-seat control if fitted;
- drive selection;
- parking brake / vehicle hold;
- door locks;
- window operation;
- mirror adjustment;
- cabin lighting;
- rear defrost.

### Screens are secondary

A display may provide:

- speed and required telltales;
- range / energy information;
- navigation;
- camera views;
- diagnostics;
- deeper configuration;
- entertainment.

The display should not be the sole path for basic vehicle operation.

### Local-control rule

A knob may command a microcontroller or CAN node when that improves packaging or wiring, but the human interface remains local and deterministic.

For a core function, failure of any of these should not unnecessarily remove control:

- infotainment computer;
- center display;
- phone;
- app;
- internet access;
- cloud account;
- remote server.

## Supplier screen

### 1. ChuangJia / ChonKia — door locks, handles, switches, window regulators
**Status: GREEN / first RFQ candidate**

Current company material describes a manufacturer founded in 1991 specializing in automotive door locks, door handles, combination switches, ignition locks, and window regulators. The company states that automotive production operates under IATF 16949 and that it supplies automotive manufacturers.

Why it fits VolksMule:

- integrated door-mechanism supplier rather than a simple reseller;
- lock + handle + switch + regulator capability;
- automotive quality-system evidence;
- potential to support both manual and powered studies;
- useful candidate for one engineering interface across multiple door mechanisms.

Required RFQ evidence:

- exact latch and striker load data;
- FMVSS 206 validation support / applicable test reports;
- latch cycle-life and door-slam durability;
- corrosion and water-ingress data;
- release effort and cable/rod geometry;
- mechanical interior emergency release;
- CAD / STEP files;
- manual regulator options and crank torque;
- service replacement availability;
- mechanically keyed exterior entry options.

Manufacturer reference: https://www.chonkia.com/

### 2. Changzhou CF Auto Parts — hinges
**Status: GREEN / hinge-manufacturer lead**

CF Auto Parts states that it has produced vehicle door hinge systems since 1988, keeps forging, stamping, CNC machining, and welding in-house, holds IATF 16949, and supplies the Chinese domestic automotive market as Tier 1 / Tier 2.

Why it fits:

- hinge specialization;
- in-house metal manufacturing;
- credible automotive quality-system path;
- custom hinge geometry is plausible once door mass and hinge axis are known.

Required RFQ evidence:

- hinge static and fatigue load capability;
- pin / bushing materials;
- corrosion coating / salt-spray results;
- allowable door mass and moment;
- sag / wear limits;
- FMVSS 206 support data;
- CAD / STEP files;
- replacement pin / bushing serviceability.

Manufacturer reference: https://www.cfautoparts.com/

### 3. ChuangJia or equivalent — combination switches
**Status: GREEN / physical-HMI supplier path**

Combination switches and local switch assemblies are preferable to forcing common driver inputs through a touchscreen. We should investigate stalk and rotary switch families with simple discrete or documented CAN outputs.

Required RFQ evidence:

- contact ratings / current capability;
- environmental sealing;
- cycle-life;
- detent force;
- connector and pinout;
- discrete vs CAN signaling;
- CAN message documentation if applicable;
- service replacement availability.

### 4. Dongguan Yujie and similar Alibaba switch manufacturers
**Status: YELLOW / commodity HMI source**

Alibaba currently surfaces large automotive-switch catalogs from manufacturers advertising IATF 16949, including rocker switches, battery disconnects, connectors, fuse hardware, and customizable switch panels.

These are attractive for non-safety-critical body functions and prototype panels, but supplier certification and exact component environmental ratings must be verified for each selected part.

Alibaba discovery reference: https://www.alibaba.com/supplier/car-kill-switch-supplier.html

### 5. Hebei Shida / Letu / Xinqiang — weather seals
**Status: GREEN / seal-development leads**

These manufacturers advertise IATF 16949 automotive sealing capability including:

- primary and secondary door seals;
- window glass-run channels;
- beltline seals;
- molded corners;
- tailgate seals;
- hood / cowl seals.

This is an excellent candidate family for custom-to-drawing or selected standard profiles.

References:
- https://www.shidarubber.com/
- https://www.letuautomotive.com/
- https://www.xinqiang-auto.com/

## Door-system architecture recommendation

### Prototype 1 baseline

Use a conventional front-hinged side door with:

1. two robust hinges;
2. one proven primary automotive latch / striker system;
3. mechanical exterior handle;
4. mechanical interior release;
5. keyed or otherwise purely local lock capability;
6. manual window regulator unless power proves the better total-system choice;
7. simple replaceable glass-run and aperture seals;
8. separate door-ajar switch / sensor;
9. ordinary fasteners and accessible adjustment points.

Avoid:

- frameless glass unless packaging proves it necessary;
- electronic-only exterior release;
- touch-sensitive hidden handles;
- motorized presenting handles;
- app-required entry;
- laminated control modules that make a latch impossible to diagnose locally;
- unique decorative switchgear that cannot be bought later.

## Why manual windows are attractive here

Manual windows are not being chosen for nostalgia. They are credible because they can reduce:

- motors;
- door wiring;
- door-jamb conductors;
- control modules;
- software states;
- switch compliance complexity;
- parasitic loads;
- failure modes;
- repair cost.

They also remain directly understandable: handle turns, glass moves.

Their disadvantages are real and should be measured:

- crank effort;
- reach from driver to passenger window;
- regulator packaging;
- slower operation;
- consumer expectation if the project ever becomes broader than Prototype 1.

For a two-seat vehicle, the passenger-window reach penalty is smaller than in a four-door vehicle, so manual operation deserves serious preference.

## Door-lock philosophy

Power central locking is optional.

The baseline should guarantee:

- mechanically operable interior release;
- mechanically operable lock state or local lock override;
- at least one non-cloud, non-phone method of exterior entry;
- a clear locked/unlocked state;
- emergency egress with dead 12-V power where practical.

If electric central locking is later added, it is layered on top of this basic ownership path rather than replacing it.

## Weather-seal philosophy

The best seal is not the fanciest profile. Prefer a system that:

- uses a small number of repeatable profiles;
- tolerates real body-production variation;
- drains water intentionally;
- is replaceable without destructive adhesive work where practical;
- can be sourced from more than one extrusion house;
- avoids unnecessary frameless-window precision.

## Validation gates

Before a door architecture freezes:

1. FMVSS 206 latch / hinge load requirements are mapped to the exact system.
2. Door sag is acceptable after cycle testing.
3. Interior release works with vehicle electrical power removed.
4. Exterior keyed / local access path works with vehicle electrical power removed.
5. Manual window effort and glass stability are acceptable across temperature range.
6. Seal compression and closing effort remain acceptable in winter conditions.
7. Water spray / rain testing shows controlled drainage and no cabin leakage.
8. Door-jamb wiring, if any, is minimized and serviceable.
9. Door can be removed / aligned with ordinary workshop tools.
10. Replacement latch, hinge, regulator, handle, and seal components remain independently purchasable.

## Sources / standards references

- 49 CFR 571.206 — Door locks and door retention components: https://www.law.cornell.edu/cfr/text/49/571.206
- 49 CFR 571.118 — Power-operated window, partition, and roof panel systems: https://www.law.cornell.edu/cfr/text/49/571.118
- ChuangJia Group: https://www.chonkia.com/
- CF Auto Parts: https://www.cfautoparts.com/
- Hebei Shida Seal Group: https://www.shidarubber.com/
- Letu Automotive: https://www.letuautomotive.com/
- Xinqiang Automotive: https://www.xinqiang-auto.com/

## Current conclusion

Alibaba is highly useful for body hardware and physical HMI, but the best outcome is not a collection of electronic gadgets.

The Prototype 1 target is deliberately simpler:

> **A door should open with a handle, lock with a local mechanism, and move its glass without needing a computer. A knob should do what its label says even when the screen is dead.**
