# What goes in the first Mule

This file is the first subsystem skeleton for **VolksMule Prototype 1**.

It does not pick exact part numbers yet. It decides what kinds of systems belong in the vehicle, what design direction we are taking, what we should buy from existing suppliers, and what we should refuse before packaging work begins.

> **Choose the right kind of thing before choosing the exact thing.**

This is intentionally not perfect. It is a scaffold for future engineering. Change it when testing, regulation, supply, or a clearly better architecture gives us a reason.

---

# 1. The basic vehicle architecture

Prototype 1 should be:

- a compact two-seat battery-electric MPV/SUV;
- roughly first-generation-CR-V scale;
- front-primary drive with automatic on-demand rear traction;
- mechanically steerable;
- hydraulically stoppable;
- built around a welded steel safety structure with replaceable bolt-on modules around it;
- powered by a non-structural removable battery pack;
- understandable and diagnosable without a manufacturer cloud account.

The vehicle should feel normal to drive. The unusual engineering should mostly disappear into good behavior.

---

# 2. Structure — DESIGN the safety cell, BUY the solved hardware

## What belongs

A **welded steel central safety structure** with:

- defined front, side, roof and rear crash load paths;
- bolt-on front subframe/cradle;
- bolt-on rear subframe/cradle;
- bolt-on or otherwise individually replaceable exterior panels where practical;
- conventional replaceable hinges, latches and fasteners;
- non-structural battery enclosure mounted within/protected by the vehicle structure;
- service access designed before cosmetic closure panels.

This is closer to a modular unibody/safety-cell philosophy than a traditional heavy body-on-frame truck.

## Why

A compact vehicle benefits from the packaging efficiency and crash load paths of a unified safety structure, while bolt-on subframes let us replace suspension, steering, drive units and damaged corner assemblies without condemning the entire shell.

## What does not belong

- giant one-piece structural castings that make collision repair dependent on factory-scale replacement methods;
- a battery pack that must remain installed to make the body structurally whole;
- permanent structural bonding where ordinary welding/bolting provides a better service path;
- cosmetic panels that require cutting the vehicle apart to replace them.

---

# 3. Body — simple doors, useful access, no powered theater

## What belongs

- two conventional front doors;
- useful side access to the cargo/tool area, preferably conventional rear side doors if packaging and crash engineering support them;
- one large rear cargo opening/hatch or door;
- manual door operation;
- normal exterior handles that work without electricity;
- replaceable weather seals;
- roof-rack hard points;
- documented front and rear recovery/tow points.

The exact rear-door/hatch arrangement stays open until crash structure and cargo packaging are modeled.

## What does not belong

- powered sliding doors unless a real use case appears;
- powered liftgate as a base requirement;
- flush motorized door handles;
- frameless glass merely for appearance;
- panoramic glass roof.

---

# 4. Suspension — independent, ordinary, repairable

## What belongs

- independent suspension at all four wheels;
- steel or aluminum control components selected for availability and durability rather than fashion;
- conventional coil springs;
- conventional replaceable dampers;
- ordinary bushings and ball joints where practical;
- replaceable hubs/bearings;
- bolt-on front and rear suspension cradles;
- enough travel for real rough-road use;
- anti-roll bars only as required by handling/ESC development.

The exact front and rear geometry remains open until candidate components and packaging are compared.

## What does not belong

- air suspension;
- adaptive electronic dampers as a base requirement;
- active anti-roll systems;
- giant wheels with short sidewalls;
- bespoke wheel bearings/hubs when mass-market equivalents work.

**Wheel rule:** use the smallest common wheel diameter that safely clears the final brakes and gives us useful tire sidewall.

---

# 5. Steering — rack and pinion with a real mechanical connection

## What belongs

- conventional rack-and-pinion steering;
- collapsible steering column;
- electric power assist;
- a continuous mechanical steering path from steering wheel to road wheels;
- steering-angle sensing required for ESC/AEB integration;
- a rack/column/assist system that can be diagnosed locally and replaced without vendor authorization.

Column-assist versus rack-assist EPS stays open until load, packaging, supplier access and control requirements are compared.

## What does not belong

- steer-by-wire as the primary steering architecture;
- steering that stops working because the infotainment computer is down;
- proprietary steering modules that cannot be replaced or calibrated outside one OEM ecosystem when avoidable.

---

# 6. Brakes — friction brakes are the safety system; regen helps

## What belongs

- four-wheel hydraulic disc brakes;
- ABS;
- electronic stability control;
- an ESC/AEB-capable hydraulic pressure-control system;
- regenerative braking coordinated with friction braking;
- a real friction parking brake with mechanical retention;
- replaceable commodity pads, rotors, hoses and caliper service parts where possible.

The brake pedal and hydraulic friction system remain the foundation. Regeneration may improve efficiency and feel, but the vehicle must stop correctly when regenerative braking is unavailable.

A cable-operated mechanical parking brake is the simplicity preference unless packaging/testing produces a better answer.

## What does not belong

- a brake-by-wire-only system with no robust hydraulic fallback for Prototype 1;
- proprietary consumables;
- regen tuning that changes basic brake response unpredictably between battery states.

---

# 7. Drivetrain — two independent e-axles, Honda behavior without Honda hardware

## What belongs

### Front

A **primary front electric drive unit/e-axle** handles ordinary driving.

### Rear

A **secondary rear electric drive unit/e-axle** supplies additional traction automatically when useful.

The two axles do not need a mechanical driveshaft between them.

The rear system should spend normal driving in the lowest-drag state practical for the chosen motor/e-axle, then contribute automatically when slip, acceleration demand, stability control, thermal load sharing, or another validated control reason calls for it.

> **If it slips, it grips.**

## Why

This preserves the behavior we liked in the old Honda system while using EV architecture to remove the mechanical coupling problem entirely.

## What stays open

- permanent-magnet versus induction versus another motor technology;
- exact front/rear power split;
- whether the rear unit needs a mechanical disconnect;
- exact inverter and reduction ratios;
- torque-vectoring behavior beyond what ESC requires.

## What does not belong

- four-wheel drive that requires routine mode selection;
- a permanent “sport AWD” philosophy that burns energy merely to keep both axles active;
- a transfer case and long mechanical propshaft unless evidence somehow proves them superior.

---

# 8. Battery — 400-V-class, LFP-first, removable and non-structural

## What belongs

A **400-V-class liquid-cooled LFP battery pack** is the working choice for Prototype 1.

Why LFP first:

- strong thermal/overcharge stability;
- long cycle-life potential;
- lower-cost cathode materials;
- appropriate tradeoff for a utility vehicle where durability and safety matter more than maximum energy density.

Why 400-V class first:

- enough voltage for a compact vehicle;
- broad component and service ecosystem;
- lower integration complexity than jumping directly to an 800-V architecture;
- does not prevent meaningful DC fast charging.

The exact pack voltage and capacity remain open until motor, inverter, range, mass, charging and thermal studies are done.

## Pack architecture

- pack is bolted/removable from the vehicle;
- pack is not required to complete the body's crash structure;
- modules/cell groups are serviceable after safe pack removal when technically reasonable;
- dedicated service disconnect;
- liquid cooling/heating;
- isolation monitoring;
- contactors and precharge;
- crash-triggered HV shutdown;
- protected venting paths;
- underside impact protection;
- no exposed HV service work during ordinary vehicle maintenance.

## What does not belong

- cell-to-body structural adhesive as the default repair philosophy;
- a sealed “replace the whole car” battery;
- choosing pack capacity before we understand the vehicle's real energy use.

---

# 9. Charging — use the North American standard

## What belongs

- **SAE J3400** vehicle inlet;
- AC charging through an onboard charger;
- DC fast-charging capability;
- charge-port and communication hardware that can be diagnosed locally;
- physical charge-release/service provisions that do not depend on a phone app.

SAE J3400 covers both AC and DC conductive charging through the same coupler family and is the working North American direction for Prototype 1.

## Utility-power export also belongs

VolksMule is a utility vehicle. It should eventually be able to power useful external equipment.

Prototype architecture should therefore reserve a path for:

- 120-V AC power output;
- useful tool/worksite loads;
- later higher-power or bidirectional/V2H capability if standards, cost and safety make it sensible.

Exact export power and bidirectional charging are not frozen for Prototype 1.

---

# 10. Low-voltage electrical — stay boring on purpose

## What belongs

- conventional **12-V low-voltage architecture**;
- ordinary replaceable 12-V battery;
- HV-to-12-V DC/DC converter;
- serviceable fuse/relay/power-distribution hardware;
- sealed automotive connectors where exposed;
- documented CAN/CAN-FD network for vehicle controls;
- separation between safety-critical vehicle networks and infotainment/general-purpose computing;
- accessible diagnostic connector and documented diagnostics;
- local hardwired fallback behavior for essential systems where practical.

A future architecture may find a reason for 48 V. Prototype 1 does not need to adopt it merely because newer luxury vehicles do.

## What does not belong

- basic lights, locks, charging or vehicle start depending on cloud connectivity;
- undocumented proprietary network messages as the only diagnostic method;
- a central touchscreen computer whose failure disables the whole vehicle.

---

# 11. Controls — buttons where buttons are better

## What belongs

Dedicated physical controls for at least:

- hazard lamps;
- turn signals;
- headlights;
- wipers/washers;
- defrost/defog;
- basic cabin temperature/fan control;
- gear/drive selection;
- parking brake;
- horn.

A screen may handle navigation, media, deeper diagnostics and configuration. It is not the only way to operate the car.

There must be a local way to unlock and start/use the vehicle without a cloud account or phone service.

## What does not belong

- touchscreen-only wipers or defrost;
- subscription-locked hardware already installed in the vehicle;
- remote account authentication required to perform ordinary service.

---

# 12. Climate control — heat pump plus a boring backup

## What belongs

- heat-pump HVAC for efficient heating/cooling;
- positive windshield defrost/defog performance;
- resistive/PTC backup heat sufficient to preserve defrost and cabin safety when heat-pump operation is unavailable or ineffective;
- battery thermal conditioning integrated into the thermal plan;
- replaceable pumps, valves, sensors and service ports where practical.

The system should favor common automotive refrigerant components and straightforward hose routing over an exotic all-in-one thermal octopus unless a major whole-vehicle benefit is proven.

---

# 13. Seats and restraints — BUY a proven system, do not invent explosives

## What belongs

- two manually adjustable front seats;
- integrated head restraints as required by the final seat choice;
- three-point belts with pretensioners/load management as required;
- frontal airbags;
- side/ejection restraint hardware required by the final design;
- passenger occupancy/child-restraint strategy coordinated with FMVSS 208/225;
- front-passenger child-seat tether provision as required by the two-seat configuration;
- supplier/donor restraint components with traceable specifications and validation data.

The seat, belt, airbag, sensors, controller and crash structure are treated as one safety system.

## What does not belong

- custom-built airbag inflators;
- power/memory/massage seats as base hardware;
- installing a donor airbag because the connector happens to fit.

---

# 14. Glass, lights, mirrors and wipers — buy the regulated commodity

## What belongs

- compliant laminated windshield;
- compliant side/rear glazing;
- conventional mirrors plus the required rear-visibility camera/system;
- standardized replaceable headlamp modules where practical;
- commodity tail/turn/brake lamp modules or easily replaceable subassemblies;
- ordinary wiper motor/linkage/blades;
- ordinary washer pump/nozzles.

These are areas where suppliers already know the rules. We should adapt the body to proven equipment when the compromise is small rather than inventing optics, glass chemistry, or wiper motors.

## What does not belong

- bespoke sealed lighting assemblies that cost thousands of dollars to replace;
- styling that forces tiny rear glass or terrible natural visibility;
- camera-only mirrors unless a compelling reason develops.

---

# 15. Wheels, tires and roadside recovery — assume the owner might be far from help

## What belongs

- common wheel diameter and bolt pattern where possible;
- real tire sidewall;
- common load-rated all-season/all-terrain tire sizes;
- full-size or functionally equivalent spare tire solution;
- jack and wheel-changing tools;
- normal lug hardware;
- front and rear recovery points;
- towing/recovery procedure documented in the vehicle.

## What does not belong

- giant low-profile wheels;
- tire sizes unique to one model;
- an aerosol sealant can as the only answer to a destroyed tire.

---

# 16. Safety automation — enough to be safe and legal, not a rolling data center

## What belongs

- ABS;
- ESC;
- TPMS;
- rear visibility camera;
- pedestrian alert sound;
- AEB/forward-collision sensing architecture in time for the applicable production requirement;
- sensors required to make the above systems work reliably.

Simple cruise control is acceptable if easy to implement safely.

## Not a Prototype 1 requirement

- automated lane centering;
- hands-free highway driving;
- self-parking;
- driver-facing surveillance cameras unless an actual safety requirement forces them;
- autonomous driving hardware installed “just in case.”

The Mule should not carry expensive sensors and computers without a job.

---

# 17. Software — local, documented, replaceable

## What belongs

Separate roles for:

- vehicle control unit;
- battery management system;
- front/rear inverter controls;
- ABS/ESC/brake controller;
- restraint controller;
- body controller/power distribution;
- instrument display;
- infotainment/general-purpose computer.

Safety-critical control must not depend on infotainment or internet access.

We should document:

- CAN/CAN-FD messages we control;
- connector pinouts;
- firmware versions;
- calibration data and procedure;
- offline update/recovery method;
- diagnostic trouble codes;
- replacement/pairing procedure.

Signed firmware and secure boot are compatible with owner control if the owner has a documented recovery/update path. Security should stop attackers, not owners.

---

# 18. Things that explicitly do not belong in Prototype 1

Unless evidence later changes the decision:

- rear passenger seats;
- steer-by-wire;
- brake-by-wire-only foundation;
- air suspension;
- adaptive dampers;
- active anti-roll hardware;
- structural battery pack;
- megacast structural body sections;
- panoramic glass roof;
- flush powered door handles;
- powered liftgate;
- giant wheels/low-profile tires;
- touchscreen-only essential controls;
- cloud-required starting, charging, diagnosis or service;
- subscription-locked installed hardware;
- autonomy hardware without an actual requirement;
- proprietary consumables when ordinary alternatives exist.

This is not anti-technology. It is anti-complexity-without-a-job.

---

# 19. First sourcing strategy

| System | Working strategy |
|---|---|
| Safety cell/body structure | **DESIGN** |
| Front/rear subframes | **ADAPT or DESIGN** around proven suspension/drive hardware |
| Suspension corners | **BUY / DONOR / ADAPT** |
| Steering column/rack/EPS | **BUY / DONOR / ADAPT** |
| Friction brakes | **BUY / DONOR / ADAPT** |
| ABS/ESC hydraulic controller | **BUY / DONOR**, integrate carefully |
| Front/rear e-axles | **BUY / DONOR / ADAPT** |
| Battery cells/modules | **BUY** |
| Battery enclosure/integration | **DESIGN** |
| BMS | **BUY or open/controlled platform**, integrate/document |
| Charge inlet | **BUY** |
| Onboard charger/DC fast-charge interface | **BUY / ADAPT** |
| HVAC compressor/heat-pump parts | **BUY / ADAPT** |
| Seats/restraints/airbags | **BUY / DONOR as a validated system** |
| Glass | **BUY**, custom shape only if necessary |
| Lighting | **BUY compliant modules** |
| Latches/hinges/wipers/mirrors | **BUY** |
| Vehicle-control integration/software | **DESIGN / DOCUMENT** |
| Exterior non-structural panels | **DESIGN for local/replaceable manufacture** |
| Brackets/ducts/covers/tool storage | **DESIGN; locally fabricate/print where sensible** |

---

# 20. What is still intentionally undecided

This skeleton is supposed to narrow the search without pretending we know everything.

Still open:

- exact suspension geometry and donor family;
- exact steering system;
- exact brake hardware and controller;
- motor technology and power ratings;
- exact battery voltage/capacity/module format;
- exact range target;
- exact charging power;
- exact thermal-loop topology;
- exact door/hatch configuration;
- exact wheel/tire size;
- exact AEB sensor stack;
- exact electronic controller vendors;
- exact body manufacturing method inside the steel-safety-cell principle.

Those become the next research/comparison tasks.

---

# 21. The decision test for every future component

A part belongs in VolksMule when it clears the hard requirement **and** improves the whole vehicle.

Ask, in order:

1. Does it satisfy the applicable safety/regulatory requirement?
2. Does it do the job well enough?
3. Is it reliable and understandable?
4. Can an owner obtain and replace it?
5. Can we document the interface?
6. Is there another supplier or a realistic adapter path?
7. Does it fit our compact/weight envelope without distorting the whole vehicle?
8. Does it create hidden software, pairing or subscription dependency?
9. Is the extra performance actually useful?
10. If it disappears in ten years, can the Mule survive?

Then choose the best **vehicle** answer, not the most impressive component.

> **Buy the commodity. Design the distinction. Orchestrate the whole machine.**

---

# Current technical anchors

These choices are working engineering judgments, not claims that a standard mandates the architecture.

- SAE J3400 defines the current North American conductive charging coupler framework for both AC and DC transfer.
- FMVSS 135 explicitly contains test treatment for EV regenerative braking; VolksMule will keep friction brakes capable of meeting the vehicle's braking obligations independently of useful regen availability.
- NHTSA's FMVSS 135 interpretation confirms the parking brake must be friction type with solely mechanical means to retain engagement.
- DOE/NREL literature identifies LFP's cost/cycle-life advantages and strong thermal stability while acknowledging its lower energy density and cold-weather tradeoffs. That is why LFP is the starting chemistry, not an unquestionable forever choice.
