# What the car needs

This is the master requirements checklist for VolksMule.

The rule is simple:

> **Requirements first. Parts second.**

We do not start by shopping for a steering column, battery, brake caliper, airbag, lamp, or motor and then design the vehicle around whatever we happened to find. First we write down what the finished vehicle must do, what law requires, how we will prove it, and what VolksMule itself requires. Then we decide whether each need is best met by buying, adapting, borrowing from a donor, or designing something ourselves.

This is a living engineering checklist, not legal advice and not a declaration that VolksMule is certified. Every regulatory row must eventually be checked against the regulation in force on the vehicle's actual date of manufacture.

**Baseline date for this checklist: 2026-08-30.**

---

## The order of work

For every requirement:

1. **What must the vehicle do?**
2. **Why must it do that?** Federal rule, state rule, safety, VolksMule requirement, or some combination.
3. **How will we prove it works?** Test, inspection, analysis, supplier certification, documentation, or destructive validation.
4. **Can we buy a proven part that already does it?**
5. **Can we adapt a proven part without creating a bad dependency?**
6. **Only then: do we need to design our own?**

The default engineering bias is:

> **Buy the commodity. Design the distinction.**

The compliance list is also a supplier map. For many regulated systems, existing manufacturers already know the standards, test methods, documentation, and production controls. Before inventing a regulated component, look for companies already making one.

---

# Gate 1 — Decide what kind of vehicle this legally is

Do not freeze parts until this is resolved.

- [ ] Confirm intended seating capacity: **2 people**.
- [ ] Confirm intended propulsion: **battery electric** unless intentionally changed.
- [ ] Set target GVWR.
- [ ] Decide and document the federal NHTSA vehicle classification under 49 CFR 571.3.
  - [ ] Passenger car?
  - [ ] Multipurpose passenger vehicle (MPV)?
  - [ ] Truck?
- [ ] Document exactly which design features support that classification.
- [ ] Confirm whether the project is a one-stage manufacturer or uses incomplete/multistage vehicles.
- [ ] Set the intended first model year / manufacture date because future effective dates matter.
- [ ] Keep the one-off prototype/title path separate from the path for manufacturing vehicles for sale.

**Why this comes first:** FMVSS applicability changes with vehicle class, weight, configuration, and date. For example, the federal bumper standard in 49 CFR Part 581 applies to passenger motor vehicles other than MPVs. Classification is architecture, not paperwork.

---

# Gate 2 — Become a real vehicle manufacturer on paper

Before a vehicle can be manufactured for sale in the United States, the manufacturer must be able to identify it and take responsibility for it.

- [ ] Establish the legal manufacturer/entity that will certify the vehicle.
- [ ] Register manufacturer information with NHTSA under **49 CFR Part 566**.
- [ ] Obtain/establish the World Manufacturer Identifier process needed for VINs.
- [ ] Create a compliant 17-character VIN system under **49 CFR Part 565**.
- [ ] Submit VIN-decoding information on the required schedule.
- [ ] Design the permanent VIN marking/location.
- [ ] Design the certification label under **49 CFR Part 567**.
- [ ] Define GVWR and GAWR values that can actually be supported by tires, wheels, axles, brakes, structure, and testing.
- [ ] If manufacturing in multiple stages, resolve **49 CFR Part 568** responsibilities and documentation.
- [ ] Establish records that show why every applicable standard was certified.

NHTSA uses manufacturer self-certification. There is no general federal pre-approval stamp that makes the car legal; the manufacturer certifies that the finished vehicle conforms to every applicable FMVSS in effect on its manufacture date.

---

# Gate 3 — Make it steer, stop, see, and communicate safely

These are the major crash-avoidance and driver-control systems we must screen for applicability and satisfy where applicable.

| Need | Federal rule to screen | What this means for VolksMule | Status |
|---|---|---|---|
| Controls and telltales make sense | FMVSS 101 | Switches, warnings, symbols, illumination, indicators | [ ] |
| Drive/reverse/park behavior is safe | FMVSS 102 | Shift selection, interlocks, rollaway behavior | [ ] |
| Driver can clear the windshield | FMVSS 103 | Defrost and defog | [ ] |
| Driver can see in rain | FMVSS 104 | Wipers and washer | [ ] |
| Brake-system applicability | FMVSS 105 / 135 | Likely light-vehicle brake standard depends on class/GVWR; resolve explicitly | [ ] |
| Brake hoses survive and fit the system | FMVSS 106 | Prefer compliant commodity hose assemblies/interfaces | [ ] |
| Other drivers can see what we are doing | FMVSS 108 | Headlamps, tail lamps, brake lamps, signals, reflectors, CHMSL where applicable | [ ] |
| Tires and rims carry the rated load | FMVSS 110 / 119 / 120 / 129 / 139 as applicable | Choose ordinary, widely available tire/wheel standards where possible | [ ] |
| Driver can see behind the vehicle | FMVSS 111 | Mirrors and/or rear-visibility system requirements | [ ] |
| Hood cannot unexpectedly open | FMVSS 113 | If the body has a hood | [ ] |
| Vehicle resists theft/rollaway hazards | FMVSS 114 | Key/start logic, park/rollaway prevention as applicable | [ ] |
| Brake fluid is correct | FMVSS 116 | If hydraulic brake fluid is used | [ ] |
| Power windows cannot create avoidable injury | FMVSS 118 | If power windows/roof/partitions are used | [ ] |
| Accelerator returns safely | FMVSS 124 | Accelerator control and failure behavior | [ ] |
| Stability control meets required behavior | FMVSS 126 | Light-vehicle ESC if applicable | [ ] |
| Automatic emergency braking | FMVSS 127 | Design architecture now for the production-date requirement | [ ] |
| Tire pressure is monitored | FMVSS 138 | TPMS if applicable | [ ] |
| EV can be heard at low speed | FMVSS 141 | Pedestrian minimum sound for EV/hybrid operation | [ ] |

### VolksMule requirements beyond the federal floor

- [ ] Steering must remain mechanically understandable and serviceable.
- [ ] Brake operation must not depend on cloud connectivity.
- [ ] Basic propulsion, braking, steering, lighting, and visibility must survive loss of infotainment/general-purpose computing.
- [ ] Safety-critical controllers must have defined degraded modes.
- [ ] Diagnostic access must be documented.
- [ ] Replacement components should have multiple-source or adapter paths where practical.

---

# Gate 4 — Keep the people alive when something goes wrong

| Need | Federal rule to screen | What this means for VolksMule | Status |
|---|---|---|---|
| Interior surfaces manage occupant impact | FMVSS 201 | Instrument panel/interior impact zones | [ ] |
| Head restraints work | FMVSS 202a | Seat/head-restraint geometry and strength | [ ] |
| Steering wheel/column does not become a spear | FMVSS 203 | Steering control impact protection | [ ] |
| Steering system intrusion is controlled | FMVSS 204 | Rearward displacement in crash | [ ] |
| Windshield/windows use compliant glazing | FMVSS 205 | Safety glazing and markings | [ ] |
| Doors stay attached/latched appropriately | FMVSS 206 | Door locks, latches, hinges/retention | [ ] |
| Seats stay attached | FMVSS 207 | Seat and mounting strength | [ ] |
| Occupants are restrained in crashes | FMVSS 208 | Crash protection, frontal restraints/airbags, belt reminders | [ ] |
| Seat-belt assemblies are compliant | FMVSS 209 | Prefer already-certified commodity assemblies | [ ] |
| Belt anchorages stay attached | FMVSS 210 | Structural load paths and mounting | [ ] |
| Windshield remains properly mounted | FMVSS 212 | Crash retention where applicable | [ ] |
| Side impacts are survivable | FMVSS 214 | Side structure and occupant protection | [ ] |
| Roof resists crush | FMVSS 216a | Roof/body structure where applicable | [ ] |
| Windshield-zone intrusion is limited | FMVSS 219 | Front structure / cowl / powertrain packaging | [ ] |
| Child-restraint anchorage applicability is resolved | FMVSS 225 | Two-seat/one-row configuration must be checked, not guessed | [ ] |
| Occupants are protected from ejection | FMVSS 226 | Side glazing/curtain restraint/body configuration where applicable | [ ] |
| Interior materials resist rapid flame spread | FMVSS 302 | Upholstery, trim, insulation, coverings | [ ] |
| Electric powertrain remains safe after crashes | FMVSS 305 / 305a | HV isolation, battery retention, electrolyte/electrical hazards; design for 305a production timing | [ ] |
| A trapped person can escape a trunk | FMVSS 401 | Only if VolksMule has a trunk that meets applicability | [ ] |

### Restraint-system work package

- [ ] Choose the occupant package and seating reference points before selecting airbags.
- [ ] Map frontal, side, rollover, and ejection protection requirements.
- [ ] Search existing production restraint suppliers/systems before considering custom components.
- [ ] Treat airbags, inflators, pretensioners, crash sensors, control logic, and structural timing as one system.
- [ ] Define diagnostic and replacement procedures.
- [ ] Never treat an airbag with the right connector as a validated airbag system.

---

# Gate 5 — Keep the battery and high voltage from hurting people

- [ ] Select target high-voltage architecture.
- [ ] Select cell/module/pack strategy.
- [ ] Define service disconnects.
- [ ] Define contactor/precharge architecture.
- [ ] Define insulation/isolation monitoring.
- [ ] Define automatic HV disconnect after crash/fault.
- [ ] Protect HV cables from abrasion, crush, water, and service mistakes.
- [ ] Provide clear HV identification and service procedures.
- [ ] Define battery retention loads and crash envelope.
- [ ] Define thermal propagation detection/mitigation strategy.
- [ ] Define venting so a cell event does not intentionally vent into the passenger compartment.
- [ ] Define water ingress and immersion assumptions.
- [ ] Define charging interlocks so the vehicle cannot drive away while physically connected where required by the charging architecture.
- [ ] Validate against FMVSS 305/305a requirements applicable to the manufacture date.
- [ ] Identify all other electrical/fire standards required by suppliers, charging equipment, facilities, insurers, or jurisdictions even when they are not FMVSS.

---

# Gate 6 — Build the ordinary car systems people forget until they are missing

These may be regulated directly, indirectly, or simply necessary for a vehicle that does not suck.

## Driver environment

- [ ] Steering wheel and column
- [ ] Steering gear/rack
- [ ] Power steering, if used
- [ ] Accelerator pedal
- [ ] Brake pedal
- [ ] Parking brake control
- [ ] Drive/reverse/park selector
- [ ] Horn
- [ ] Speed display
- [ ] Odometer / required vehicle information
- [ ] Warning telltales
- [ ] Turn-signal control
- [ ] Hazard control
- [ ] Headlamp control
- [ ] Wiper/washer control
- [ ] Defrost/defog controls
- [ ] HVAC controls
- [ ] Rear visibility/mirror/camera display

## Chassis

- [ ] Main structure/frame/body shell
- [ ] Front crash structure
- [ ] Rear crash structure
- [ ] Side-impact structure
- [ ] Roof structure
- [ ] Suspension front
- [ ] Suspension rear
- [ ] Springs
- [ ] Dampers
- [ ] Control arms/links
- [ ] Uprights/knuckles
- [ ] Hubs/bearings
- [ ] Wheels
- [ ] Tires
- [ ] Service brakes
- [ ] Parking brake
- [ ] ABS hardware
- [ ] ESC-capable sensing/control hardware where required

## Body and weather

- [ ] Windshield
- [ ] Side glazing
- [ ] Rear glazing if used
- [ ] Doors
- [ ] Door latches/hinges
- [ ] Hood/frunk lid if used
- [ ] Cargo door/hatch/tailgate if used
- [ ] Weather seals
- [ ] Wipers
- [ ] Washer reservoir/pump/nozzles
- [ ] Exterior mirrors if used/required
- [ ] Drainage paths
- [ ] Corrosion protection
- [ ] Exterior lighting
- [ ] Reflectors
- [ ] Bumpers / energy management as classification requires

## Cabin

- [ ] Driver seat
- [ ] Passenger seat
- [ ] Seat tracks/adjusters
- [ ] Seat belts
- [ ] Belt anchorages
- [ ] Head restraints
- [ ] Airbags/restraint hardware
- [ ] Interior trim
- [ ] Instrument panel
- [ ] Floor/firewall barriers
- [ ] Heating
- [ ] Cooling/ventilation
- [ ] Defrost/defog air delivery
- [ ] Interior lighting
- [ ] Storage that does not become a crash projectile

## Propulsion

- [ ] Primary traction motor
- [ ] Primary inverter
- [ ] Reduction gear/differential
- [ ] Half-shafts/CV joints
- [ ] Secondary traction motor/axle solution
- [ ] Secondary inverter
- [ ] Slip detection
- [ ] Automatic second-axle engagement logic: **if it slips, it grips**
- [ ] Torque coordination
- [ ] Regenerative braking coordination
- [ ] Cooling loops
- [ ] Pumps/valves/radiators/chillers as needed
- [ ] Limp/degraded modes
- [ ] Mechanical tow/recovery behavior

## Low-voltage electrical

- [ ] 12 V or chosen LV battery architecture
- [ ] DC/DC converter
- [ ] Fuse/power distribution
- [ ] Grounding/bonding strategy
- [ ] Wiring harnesses
- [ ] Sealed connectors where needed
- [ ] CAN/vehicle network or chosen alternatives
- [ ] Gateway boundaries
- [ ] Service connector
- [ ] Diagnostic protocol
- [ ] Sleep/wake strategy
- [ ] Emergency power-down behavior

## Charging

- [ ] Charge inlet standard
- [ ] AC charging
- [ ] DC fast charging, if included
- [ ] Onboard charger, if required by architecture
- [ ] Charge communication
- [ ] Thermal management during charging
- [ ] Charge-door/inlet weather protection
- [ ] Charging-fault handling
- [ ] Owner-visible charging diagnostics

---

# Gate 7 — Rules outside the FMVSS list

FMVSS Part 571 is not the whole federal production problem.

- [ ] **49 CFR Part 541 — Theft prevention / parts marking.** Screen applicability and low-volume provisions.
- [ ] **49 CFR Part 565 — VIN requirements.**
- [ ] **49 CFR Part 566 — Manufacturer identification.**
- [ ] **49 CFR Part 567 — Certification.**
- [ ] **49 CFR Part 568 — Vehicles manufactured in two or more stages**, if applicable.
- [ ] **49 CFR Part 573 — Safety defect and noncompliance reporting / recall responsibility.**
- [ ] **49 CFR Part 575 — Consumer information**, including applicable new-vehicle labeling/information.
- [ ] **49 CFR Part 576 — Record retention**, where applicable.
- [ ] **49 CFR Part 577 — Owner notification for defects/noncompliance.**
- [ ] **49 CFR Part 579 — Early Warning Reporting.** Low-volume manufacturers still have defined duties even when full high-volume aggregate reporting does not apply.
- [ ] **49 CFR Part 581 — Federal bumper standard.** Determine applicability from final vehicle classification.
- [ ] **49 CFR Part 583 — Automobile parts content labeling.** Determine applicability/exemptions for the planned production volume and vehicle class.
- [ ] Determine any CAFE/fuel-economy reporting obligations applicable to the chosen classification and production plan.
- [ ] Establish a recall/contact/traceability process before customer vehicles exist.

---

# Gate 8 — EPA and energy/fuel-economy work

Being electric does not mean there is no EPA work.

- [ ] Register the manufacturer in EPA's **Engines and Vehicles Compliance Information System (EV-CIS)**.
- [ ] Determine the applicable EPA certificate-of-conformity pathway for the vehicle/test group.
- [ ] Establish required light-duty vehicle certification data.
- [ ] Establish EPA fuel-economy/range test plan.
- [ ] Produce the required Fuel Economy and Environment label data for new vehicles.
- [ ] Establish model-year reporting obligations.
- [ ] Track EPA greenhouse-gas/fuel-economy rules applicable to the chosen vehicle class and production volume.
- [ ] Document any small-volume provisions or exemptions; never assume them.

---

# Gate 9 — State road use is a separate layer

Federal manufacture/certification and state registration are different problems.

For the prototype:

- [ ] Choose the first state in which the prototype will be titled/registered.
- [ ] Determine that state's assembled/homebuilt/experimental vehicle path.
- [ ] Determine inspection requirements.
- [ ] Determine VIN assignment/verification interaction with the federal/manufacturer VIN plan.
- [ ] Determine insurance requirements.
- [ ] Determine equipment requirements not preempted by federal law.
- [ ] Determine temporary movement/testing permits before public-road testing.

For eventual production:

- [ ] Build a 50-state title/registration launch checklist.
- [ ] Identify state-specific EV fees, inspections, dealer/direct-sale constraints, and documentation requirements.

**Never use successful registration of one prototype as proof that a production vehicle complies with federal manufacturing law.**

---

# Gate 10 — Prove it instead of believing it

For each applicable regulation or VolksMule requirement, create a verification row containing:

- [ ] Requirement ID
- [ ] Plain-English requirement
- [ ] Exact regulation/source and revision date
- [ ] Applicability rationale
- [ ] Design solution
- [ ] Supplier/part number if purchased
- [ ] Alternate supplier/part if available
- [ ] Interface drawing/specification
- [ ] Verification method
- [ ] Test fixture/procedure
- [ ] Pass/fail criteria
- [ ] Test result/data location
- [ ] Person/entity responsible for signoff
- [ ] Open questions
- [ ] Change impact if this part is substituted later

The certification evidence should be reproducible. "The supplier said it was fine" is not a verification plan unless the supplier's certification actually covers our use and installation.

---

# Gate 11 — Decide buy, adapt, or design

Only after the requirement is understood:

| Decision | Use it when |
|---|---|
| **BUY** | Existing part satisfies the hard requirements and does not trap the architecture. |
| **ADAPT** | Existing part is close and a documented interface/adapter gets us there safely. |
| **DONOR** | A production vehicle subsystem provides validated behavior and can be integrated without unacceptable proprietary dependency. |
| **DESIGN** | Available parts fail a real VolksMule requirement or prevent the architecture from working. |

An 88% part available tomorrow can be better prototype engineering than a 100% custom part eight months from now **if the missing 12% is preference rather than a hard requirement**.

Prototype interfaces should allow substitution. Ideally the vehicle accepts today's 88% component, tomorrow's 95% component, and an eventual custom component through documented mechanical/electrical/software interfaces rather than redesigning the entire car.

---

# Gate 12 — Build a supplier map from the rules

Every applicable requirement should trigger a supplier search before custom design.

For each system:

- [ ] Find U.S. manufacturers already producing compliant components.
- [ ] Find suppliers serving multiple OEMs/platforms rather than one captive vehicle line.
- [ ] Record minimum order quantities.
- [ ] Record lead times.
- [ ] Record test/certification evidence available from the supplier.
- [ ] Record interface documentation available.
- [ ] Record whether replacement parts can be purchased without OEM authorization.
- [ ] Record whether software pairing/coding is required.
- [ ] Record at least one substitute where practical.
- [ ] Prefer ordinary fasteners, connectors, bearings, seals, hoses, and service tools.
- [ ] Mark components whose supplier disappearance would immobilize the vehicle.

The goal is not merely a bill of materials. It is a **bill of replaceable capabilities**.

---

# Things that are probably not VolksMule requirements — but must be explicitly closed out

A complete checklist includes the things we prove are **not applicable**.

- [ ] FMVSS 121 — air brakes: expected N/A unless architecture changes.
- [ ] FMVSS 122/122a/123 — motorcycles: expected N/A.
- [ ] FMVSS 131 — school-bus pedestrian equipment: expected N/A.
- [ ] FMVSS 136 — heavy-vehicle ESC: expected N/A if VolksMule remains a light vehicle.
- [ ] FMVSS 217/217a/220/221/222/227 — bus/school-bus rules: expected N/A.
- [ ] FMVSS 218 — motorcycle helmets: N/A to the vehicle.
- [ ] FMVSS 223/224 — rear impact guards/protection: expected N/A for the intended light vehicle, verify.
- [ ] FMVSS 301 — liquid-fuel-system integrity: expected N/A for a pure BEV; revisit if a liquid-fuel heater/range extender is introduced.
- [ ] FMVSS 303/304 — CNG: expected N/A.
- [ ] FMVSS 307/308 — hydrogen: expected N/A.
- [ ] FMVSS 403/404 — platform lifts: expected N/A unless one is fitted.
- [ ] FMVSS 500 — low-speed vehicles: **not the design target**; VolksMule should not become a 25-mph LSV merely to avoid full vehicle engineering.

Closing an item as N/A requires an applicability reason, not a shrug.

---

# Near-term regulatory dates we should design around

- **September 1, 2026:** enhanced front-seat belt warning requirements begin for new vehicles under the updated occupant-protection framework.
- **September 1, 2027:** FMVSS 305a electric-powertrain integrity reaches mandatory applicability.
- **2029 production horizon:** FMVSS 127 automatic emergency braking requirements are part of the light-vehicle design target; confirm exact phase-in/applicability for VolksMule's actual model year.

A prototype can precede a future standard. The architecture should not deliberately make the production vehicle obsolete before it exists.

---

# Definition of done for this checklist

This file is not "complete" because it has a lot of boxes.

It is complete when:

- [ ] Vehicle classification is frozen and justified.
- [ ] Every current FMVSS has been checked for applicability.
- [ ] Every applicable federal non-FMVSS manufacturer rule has been identified.
- [ ] EPA obligations are mapped.
- [ ] Prototype state-title/testing path is mapped.
- [ ] Every applicable requirement has a verification method.
- [ ] Every vehicle system has a sourcing/design strategy.
- [ ] Every safety-critical subsystem has failure/degraded behavior.
- [ ] Every selected component has an interface specification.
- [ ] Supplier-lock-in risks are visible.
- [ ] The checklist has been reviewed against the regulations in force for the intended manufacture date.

Then, and only then, the checklist becomes the basis for the parts search and prototype BOM.

---

# Primary starting sources

Use the live regulations as authority; these links are starting points for the working map.

- NHTSA, Federal vehicle safety / Part 571 overview: https://www.nhtsa.gov/ratings
- 49 CFR Part 571, Federal Motor Vehicle Safety Standards: https://www.ecfr.gov/current/title-49/subtitle-B/chapter-V/part-571
- NHTSA manufacturer certification/VIN guidance: https://www.nhtsa.gov/importing-vehicle/importation-and-certification-faqs
- NHTSA Early Warning Reporting: https://www.nhtsa.gov/vehicle-manufacturers/early-warning-reporting
- EPA light-duty certification and fuel economy: https://www.epa.gov/ve-certification/certification-and-fuel-economy-light-duty-passenger-cars-and-trucks
- EPA EV-CIS registration: https://www.epa.gov/ve-certification/how-register-engines-and-vehicles-compliance-information-system-ev-cis

---

## The point

VolksMule is not trying to redesign every part of a car.

We are trying to organize already-engineered components correctly enough to produce an open vehicle that is safe, legal, repairable, understandable, replaceable, owner-controlled, and useful.

> **Build a vehicle that doesn't suck.**
