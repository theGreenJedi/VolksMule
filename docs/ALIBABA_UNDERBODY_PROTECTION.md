# Alibaba underbody protection — skid plates, splash shields and wheel liners

Research current as of **2026-09-01**.

This document continues the VolksMule roadmap sourcing mission underneath the vehicle.

The important distinction is:

> **Battery/crash protection is structural engineering. Splash, aero and sacrificial skid panels are service hardware.**

Alibaba is useful for both fabrication intelligence and later stable-CAD manufacturing, but marketplace `battery armor` language is not a substitute for impact/load-path analysis.

---

## 1. Prototype-1 underbody layers

Study the underbody as separate functional layers:

1. **battery enclosure / structural pack protection** — engineered as part of the pack/body system;
2. **structural skid/load-transfer members** where genuine rock/obstacle impacts must bypass vulnerable components;
3. **removable sacrificial skid panels** protecting motors, BDU/service hardware and exposed pack surfaces;
4. **light splash/aero/service shields** keeping water, salt and debris away from connectors and cavities;
5. **wheel-well liners and mud flaps** controlling spray/gravel;
6. **localized guards** for coolant lines, HV cable and other routed services.

These layers should not be merged into one huge bonded undertray that must be destroyed for routine service.

---

# 2. Alibaba EV skid-plate market

Alibaba currently has extensive bolt-on aluminum underbody guards for production EVs including BYD, Tesla, Changan, Xpeng and others.

Current examples include:

- roughly **2.5–2.7-mm aluminum-alloy** battery/motor cover plates;
- thicker/heavier off-road-style plates advertised up to ~8 mm on some vehicle-specific products;
- bolt-on sections using existing OEM mounting holes;
- multi-piece motor/battery protection kits;
- custom CNC/stamped sheet-metal guard manufacturing.

Typical prices range from tens of dollars for light guards to hundreds for multi-piece/heavy aluminum systems.

### What this proves

- custom low-volume aluminum guard fabrication is commercially routine;
- replacement bolt-on sections are practical;
- Alibaba/China can be a strong later production source once CAD stabilizes.

### What it does NOT prove

A plate advertised as `battery protection` does not establish:

- rock-strike energy capacity;
- puncture resistance;
- battery intrusion margin;
- mount load capacity;
- crash interaction;
- fatigue life;
- fire/thermal-event behavior;
- effect on pack cooling/venting.

### Verdict

> **GREEN fabrication channel / RED as unverified structural engineering.**

---

# 3. Battery protection architecture

The removable LFP pack already has its own engineered enclosure.

External underbody protection should therefore be designed so that a strike load is intentionally managed through known structure rather than simply pressing a thin sheet directly into the pack floor.

Possible arrangement:

- strong perimeter/crossmember structure tied to the safety cell/subframes;
- protected standoff gap under the battery enclosure;
- replaceable skid plate spanning between strong points;
- local reinforcement under highest-risk zones;
- drainage/cleaning paths;
- inspection access after a strike.

### Hard rule

> **A sacrificial skid plate should fail before an expensive battery enclosure where practical, but it must not deform into the cells.**

Exact thickness/alloy/corrugation waits for structural impact analysis.

---

# 4. Motor / e-axle guards

Front and rear e-axles sit near road/debris exposure and can benefit from local guards.

Desired design:

- bolt-on;
- separate from the e-axle casting;
- clearance for motor/inverter cooling;
- drainage;
- no trapped mud/salt pocket;
- service openings for oil/fill/drain points where applicable;
- removal without disturbing suspension alignment;
- formed ribs/beads where they improve stiffness efficiently.

### Sourcing mode

Mule #1:

- local laser/waterjet/bend fabrication is likely fastest while geometry moves.

Stable revision:

- Alibaba drawing-based sheet-metal/aluminum manufacturer becomes attractive.

### Verdict

> **DESIGN + FABRICATE.**

---

# 5. BDU / HV service-zone guards

High-voltage service components need stone/splash protection but also excellent technician access.

Do not hide the transparent BDU/PDU philosophy under a permanent undertray.

Use:

- small removable guard panels;
- captive/reusable fasteners where practical;
- obvious labels/access boundaries;
- shielded connector/cable routes;
- service panel removable independently from battery or suspension.

### Verdict

> **LIGHT SERVICE SHIELD, not structural mystery cover.**

---

# 6. Wheel-well liners

Alibaba currently exposes both replacement and custom-manufactured PP/PE fender liners.

Current custom listings support:

- polypropylene / polyethylene;
- injection molding;
- drawing/OEM geometry;
- splash/debris protection;
- integrated fastener bosses/features.

### Prototype strategy

Injection-mold tooling does not make sense while body/suspension geometry is still moving.

For Mule #1, study:

- thermoformed HDPE/PP;
- simple sheet plastic panels;
- flexible rubber sections where steering/jounce clearance is tight;
- locally fabricated prototypes.

Later stable CAD can move to Chinese injection/thermoform production.

### Design requirements

- full 34-in tire steering/jounce clearance;
- access to strut/brake/steering service points;
- drainage;
- abrasion resistance;
- replaceable clips/screws;
- no hidden dirt/salt traps;
- protection of exposed connectors/harnesses.

### Verdict

> **LOCAL PROTOTYPE / ALIBABA PRODUCTION LATER.**

---

# 7. Splash / aero panels

Flat underbody panels can reduce spray and drag, but serviceability wins over aerodynamic perfection on Prototype 1.

Use separate zones rather than one enormous panel:

- front splash panel;
- battery/skid region;
- rear-drive splash/guard region;
- small local aero deflectors if testing demonstrates value.

Materials can include:

- PP/HDPE for splash panels;
- aluminum for hotter/impact-prone areas;
- fiber-reinforced thermoplastic later if it earns cost/tooling.

### Rule

Every panel should have an actual job.

> **No underbody panel exists merely because modern cars have underbody panels.**

---

# 8. Mud flaps

Mud flaps are excellent boring hardware for a vehicle expected to see snow, gravel and occasional off-road conditions.

First study:

- flexible rubber/thermoplastic flap;
- simple bolted replaceable bracket;
- enough clearance that reverse travel through snow/mud does not tear the body apart;
- no decorative molded running-board integration.

Alibaba and local truck/accessory suppliers have immense commodity depth.

### Verdict

> **BUY COMMODITY / simple bracket.**

---

# 9. HV cable and coolant-line guards

Routing should first put cables/hoses out of harm's way.

Where crossing/exposure is unavoidable, use local removable shields.

Requirements:

- guard cannot abrade line/cable;
- maintain bend-radius requirements;
- water/salt can escape;
- inspection remains possible;
- no sharp edges;
- fasteners cannot protrude toward battery/HV insulation;
- shield is cheaper/easier to replace than the protected service.

### Verdict

> **DESIGN ROUTE FIRST; ADD LOCAL GUARD ONLY WHERE NEEDED.**

---

# 10. Fasteners and service panels

Underbody hardware should use a deliberately small fastener family.

Study standardization around:

- corrosion-protected metric bolts;
- captive nuts/rivnuts only where appropriate and inspectable;
- quarter-turn/captive panel fasteners for genuinely frequent access only;
- replaceable plastic clips for liners/splash shields;
- no dozen proprietary clip types.

### Service rule

The owner should not need a diagram to remember which of 37 visually identical screws is 3 mm longer.

---

# 11. Current sourcing shortlist

| Function | First path | Mode | Blocker |
|---|---|---|---|
| Structural battery skid/load path | VolksMule engineering | DESIGN | impact/crash/pack geometry |
| Replaceable battery skid panel | local Mule-1 fabrication; Alibaba stable-CAD fabrication later | DESIGN + BUY/FABRICATE | structural mounts/thickness analysis |
| Front/rear e-axle guard | drawing-based aluminum/steel fabrication | DESIGN + BUY | e-axle/cradle CAD |
| BDU/HV service shield | simple removable sheet/polymer panel | DESIGN + FABRICATE | final service-zone layout |
| Wheel liners | thermoformed local prototype; Alibaba PP/PE production later | DESIGN + BUY | tire/suspension/body geometry |
| Splash/aero shields | PP/HDPE/aluminum panels | DESIGN + BUY | underbody routing/service access |
| Mud flaps | common flexible rubber/thermoplastic | BUY | wheel-opening geometry |
| Cable/hose guards | local formed guards | DESIGN + FABRICATE | final route/exposure |
| Underbody fasteners/clips | small standardized metric/clip family | BUY | panel material/service frequency |

---

# 12. What not to buy

Reject as engineering shortcuts:

- generic `EV battery armor` with no load/impact data;
- skid plate whose mounting bolts go only into weak cosmetic sheet metal;
- one-piece bonded undertray blocking battery/HV/service access;
- thick/heavy plate chosen only because `more mm = safer`;
- decorative off-road bash plates with no controlled load path;
- liners that require suspension removal for routine replacement;
- skid panels that cover battery vents/drains or trap salt/mud.

---

# 13. Current architecture recommendation

Treat the underbody as a **serviceable layered protection system**:

> **Strong structure where impact loads must go. Replaceable skid plates where damage is expected. Cheap splash/liner pieces where debris control is the job.**

This keeps actual battery safety in VolksMule engineering while taking full advantage of Alibaba's inexpensive fabrication and molded-plastic ecosystem once geometry is stable.

---

## Sources reviewed

Public research current as of **2026-09-01**:

- current Alibaba EV battery/motor skid-plate listings for BYD, Tesla and other EVs;
- current Alibaba custom CNC/stamped automotive skid-plate fabrication listings;
- current Alibaba custom PP/PE fender-liner and underbody splash-panel manufacturing listings;
- current Alibaba replacement fender-liner/undertray catalogs.

Marketplace safety/impact claims are not treated as validated engineering evidence.
