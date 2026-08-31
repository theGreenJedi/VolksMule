# What rules our SUV has to follow

This is the working federal applicability map for **VolksMule Prototype 1**.

The point is not to collect regulation numbers. The point is to know, before we shop for parts, what the finished vehicle must actually prove.

> **Requirements first. Parts second.**

This file is a living engineering map, not legal advice and not a claim of certification. Applicability must be rechecked against the live regulations for the vehicle's actual date of manufacture.

**Baseline checked: 2026-08-30.**

---

## The SUV we are talking about

For this pass, Prototype 1 means:

- **Federal working classification:** Multipurpose Passenger Vehicle (MPV).
- **Use/body target:** compact two-seat utility SUV, philosophically similar to a first-generation Honda CR-V but not a copy.
- **Seats:** two designated seating positions, one row.
- **Propulsion:** battery electric.
- **Road speed:** normal highway-capable vehicle, not a low-speed vehicle.
- **Drive:** primary axle plus automatic on-demand second-axle traction — **if it slips, it grips**.
- **Body:** fixed roof, conventional windshield, normal doors/hatch unless later changed.
- **Brakes:** conventional light-vehicle service brakes, expected hydraulic friction brakes with regenerative braking integrated around them.
- **Wheels:** single wheels, not dual-wheel axles.
- **Working GVWR ceiling:** **3,500 kg / 7,716 lb**.
- **Expected production scale:** small-volume original manufacturer, fewer than 5,000 U.S. vehicles per year, unless the project grows beyond that.

The MPV classification must be genuine. Under 49 CFR 571.3, an MPV carries 10 or fewer people and is either built on a truck chassis or has **special features for occasional off-road operation**. Four-wheel drive by itself is not a substitute for actually designing those features.

VolksMule may eventually support truck, van, or other bodies. Those finished vehicles would get their own classification and applicability review. We are not trying to make one magical certification cover every possible body.

---

## Status words

- **APPLIES** — Prototype 1 is squarely in the standard's application as currently conceived.
- **APPLIES LATER** — the standard covers us, but the mandatory production date is in the future.
- **CONDITIONAL** — depends on a design choice we have not frozen.
- **EQUIPMENT** — primarily a regulated component/material we should buy compliant rather than reinvent.
- **N/A** — not applicable to the current Prototype 1 assumptions.
- **VERIFY** — likely answer is known, but a final classification, weight, configuration, or model-year decision must close it formally.

---

# 1. Rules the SUV clearly has to meet

| Rule | Plain-English job | Status | What it means for VolksMule |
|---|---|---|---|
| **FMVSS 101** | Controls, telltales, indicators | APPLIES | Driver controls, warnings, symbols and illumination must follow the standard. |
| **FMVSS 102** | Drive/reverse/park and rollaway behavior | APPLIES | Selector logic and interlocks cannot be improvised. |
| **FMVSS 103** | Windshield defrost/defog | APPLIES | HVAC must clear the required windshield area. |
| **FMVSS 104** | Windshield wiping/washing | APPLIES | Wiper geometry, sweep and washer performance matter. |
| **FMVSS 106** | Brake hoses | EQUIPMENT | Prefer compliant, documented commodity hose assemblies. |
| **FMVSS 108** | Lamps and reflectors | APPLIES | Headlamps, brake lamps, turn signals, markers/reflectors and placement become packaging inputs. |
| **FMVSS 110** | Tires, rims and loading information | APPLIES | GVWR/GAWR, tire load capacity, placards and wheel/tire choices must agree. |
| **FMVSS 111** | Rear visibility | APPLIES | Mirrors and rear-visibility system requirements must be designed in. |
| **FMVSS 113** | Hood latch | APPLIES IF HOOD FITTED | A conventional obstructing hood needs compliant retention/latching. |
| **FMVSS 114** | Theft protection and rollaway prevention | APPLIES | Start authorization, park behavior and rollaway prevention need a defined design. |
| **FMVSS 124** | Accelerator return | APPLIES | Accelerator control must return safely after specified failures. |
| **FMVSS 126** | Electronic stability control | APPLIES | ESC is part of the base vehicle architecture, not an optional app. |
| **FMVSS 135** | Light-vehicle braking | APPLIES if GVWR <= 3,500 kg / 7,716 lb | This is a major reason to keep Prototype 1 under the working GVWR ceiling. |
| **FMVSS 138** | Tire pressure monitoring | APPLIES | Design for TPMS with ordinary serviceable sensors where possible. |
| **FMVSS 141** | Minimum sound for quiet vehicles | APPLIES | A BEV needs the required low-speed pedestrian alert sound. |
| **FMVSS 201** | Occupant protection in interior impact | APPLIES | Dash, pillars, trim and interior geometry are safety systems. |
| **FMVSS 202a** | Head restraints | APPLIES | Seat/head-restraint selection and geometry must be validated together. |
| **FMVSS 203** | Steering control impact protection | APPLIES | Steering wheel/column choice cannot be treated as a simple mechanical fit. |
| **FMVSS 204** | Steering-control rearward displacement | APPLIES | Front crash structure and steering-column packaging interact. |
| **FMVSS 205** | Safety glazing | APPLIES | Use compliant marked automotive glazing. |
| **FMVSS 206** | Door locks, latches and retention | APPLIES | Door/hatch hardware and structure need compliant retention. |
| **FMVSS 207** | Seating systems | APPLIES | Seats, tracks and mounts must meet strength requirements. |
| **FMVSS 208** | Occupant crash protection | APPLIES | Belts, frontal airbags, sensors, reminders and crash behavior are one restraint system. |
| **FMVSS 210** | Seat-belt anchorages | APPLIES | Belt mounting loads are structural requirements, not trim details. |
| **FMVSS 212** | Windshield mounting in crash | APPLIES to our conventional SUV configuration | Glass, adhesive/flange design and body structure interact. |
| **FMVSS 214** | Side-impact protection | APPLIES | Door, sill, seat, battery and side structure must be designed as a crash system. |
| **FMVSS 216a** | Roof-crush resistance | APPLIES to our fixed-roof SUV | Roof, pillars and body structure need a real load path. |
| **FMVSS 219** | Windshield-zone intrusion | APPLIES to our conventional SUV configuration | Front structure must control intrusion toward the windshield/cabin. |
| **FMVSS 225** | Child-restraint anchorages | APPLIES at our intended weight | A two-seat car still has a front-passenger tether requirement; see the dedicated note below. |
| **FMVSS 226** | Ejection mitigation | APPLIES to our fixed-roof/normal-door SUV | Side glazing/restraint/body choices must satisfy ejection mitigation. |
| **FMVSS 302** | Flammability of interior materials | APPLIES | Upholstery, trim, insulation and coverings need compliant materials. |

---

# 2. Rules we should design for now even though their mandatory date is later

## FMVSS 127 — automatic emergency braking

**Status: APPLIES LATER.**

FMVSS 127 applies to passenger cars, MPVs, trucks and buses at or below 10,000 lb GVWR. Vehicles generally must comply beginning **September 1, 2029**. The standard defines a small-volume manufacturer as an original manufacturer producing fewer than 5,000 vehicles annually for sale in the United States, and gives small-volume manufacturers, final-stage manufacturers and alterers **one additional year**.

For the currently imagined VolksMule production scale, plan around **September 1, 2030** as the outside small-volume mandatory date unless the rule changes or our production scale changes.

**Design consequence now:** leave room, power, networking, braking authority and diagnostic interfaces for forward-collision warning and AEB. Do not package the front of the vehicle in a way that makes a compliant sensing system impossible later.

## FMVSS 305a — electric powertrain integrity

**Status: APPLIES LATER, and it is foundational.**

FMVSS 305a applies to highway-capable vehicles using electric propulsion above the specified high-voltage thresholds. For vehicles at or below 10,000 lb GVWR, mandatory applicability begins **September 1, 2027**; small-volume manufacturers, final-stage manufacturers and alterers receive one additional year.

For a small-volume VolksMule at our intended weight, design to **305a now** and assume mandatory compliance by **September 1, 2028**.

It covers more than crash isolation. It reaches normal operation and post-crash hazards including electric shock, fire, explosion, gas venting, energy-storage retention and charging/drive-away safety. Battery packaging, HV disconnects, venting, service isolation and crash structure therefore belong in the architecture from day one.

## FMVSS 208 — enhanced seat-belt warnings

The previously noted 2026 front-seat deadline is stale. NHTSA's April 2026 interim final rule moved the enhanced seat-belt warning compliance date to **September 1, 2028**, with optional early compliance and an additional year for multi-stage manufacturers and alterers.

Prototype 1 has no rear seating positions, so the rear-seat warning portion does not create phantom rear-seat hardware. The driver and front outboard passenger warning architecture still matters.

---

# 3. The two-seat child-seat gotcha

Do **not** mark FMVSS 225 N/A just because VolksMule has no rear seat.

NHTSA has interpreted S4.4(c) to require a vehicle with **no forward-facing rear designated seating position** to have a **tether anchorage at each front forward-facing passenger seating position**.

That creates an early design interaction:

- the passenger-seat structure needs a compliant tether load path;
- passenger airbag strategy matters;
- lower LATCH anchorages at a front passenger position have additional airbag/on-off-switch restrictions;
- therefore we should decide the front-passenger child-restraint/airbag strategy before freezing the seat, dashboard, restraint controller or body anchor points.

This is exactly the kind of obscure requirement the checklist is intended to expose before metal is cut.

---

# 4. Regulated equipment we should usually buy rather than invent

These standards primarily point us toward established suppliers and validated materials/components.

| Rule | Item | Working strategy |
|---|---|---|
| **FMVSS 106** | Brake hoses | BUY compliant assemblies; design replaceable interfaces. |
| **FMVSS 116** | Brake fluid | BUY specified compliant fluid if hydraulic architecture uses it. |
| **FMVSS 139** | New pneumatic radial tires for light vehicles | BUY mainstream compliant tires with broad replacement availability. |
| **FMVSS 205** | Glazing | BUY marked compliant automotive glazing or have glass produced to the applicable spec. |
| **FMVSS 209** | Seat-belt assemblies | BUY a compliant production restraint assembly; do not invent webbing/buckles/retractors for Prototype 1. |
| **FMVSS 302** | Interior materials | Source materials with test evidence; validate our finished use. |

A supplier's compliant part does **not** automatically certify our installation. Mounting geometry, structure, interfaces and system behavior remain our responsibility.

---

# 5. Rules that depend on choices we have not frozen

| Rule | Status | Trigger |
|---|---|---|
| **FMVSS 118** — power-operated windows/roof/partitions | CONDITIONAL | Applies if we use covered power-operated openings. A production SUV probably will, so design as if it will apply. |
| **FMVSS 105** — hydraulic/electric brake systems for heavier vehicles | N/A if we hold GVWR <= 3,500 kg | Becomes the relevant brake regime for an MPV above the FMVSS 135 weight ceiling. |
| **FMVSS 301** — liquid-fuel-system integrity | N/A for pure BEV | Revisit if we add a gasoline/diesel range extender or another qualifying liquid-fuel system. |
| **FMVSS 403/404** — platform lifts | N/A | Revisit only if a platform lift is fitted. |
| **49 CFR Part 568** — multistage manufacture | CONDITIONAL | Depends on whether VolksMule is built/certified in one stage or completed from an incomplete vehicle. |

---

# 6. Rules we can close as not applicable to this SUV unless the architecture changes

The reason belongs in the record; “not our problem” is not enough.

- **FMVSS 121** — air brake systems: N/A; Prototype 1 is a light vehicle without air brakes.
- **FMVSS 122 / 122a / 123** — motorcycle brake/control rules: N/A; four-wheel MPV.
- **FMVSS 125** — warning devices supplied as equipment: not a base-vehicle certification target unless supplied in a covered way.
- **FMVSS 129** — new non-pneumatic tires: N/A unless we choose that tire technology.
- **FMVSS 131** — school-bus pedestrian safety: N/A.
- **FMVSS 136** — heavy-vehicle ESC: N/A at our intended weight/class; FMVSS 126 is the relevant ESC rule.
- **FMVSS 217 / 217a / 220 / 221 / 222 / 227** — bus/school-bus requirements: N/A.
- **FMVSS 218** — motorcycle helmets: N/A to the vehicle.
- **FMVSS 223 / 224** — rear impact guards/protection for heavy trailers/trucks: N/A to this light MPV.
- **FMVSS 303 / 304** — CNG systems: N/A.
- **FMVSS 307 / 308** — hydrogen systems: N/A.
- **FMVSS 401** — interior trunk release: applies to passenger cars with trunks; our MPV/hatch cargo configuration is not that vehicle type.
- **FMVSS 500** — low-speed vehicles: N/A by design; VolksMule is intended to be a normal highway-capable vehicle.

Child-restraint standards in the 213 family principally regulate child-restraint products. We are not planning a built-in child restraint. Our vehicle-side requirement is primarily FMVSS 225 plus the restraint/airbag interactions in FMVSS 208.

---

# 7. Three weight numbers we should not cross casually

## 7,716 lb / 3,500 kg

This is the **FMVSS 135 light-vehicle brake ceiling for MPVs/trucks/buses**. Going above it pushes the vehicle into a different brake-standard regime.

**VolksMule decision:** make **<= 7,716 lb GVWR a hard working architecture constraint** unless a compelling engineering reason appears to change it. A CR-V-scale two-seat EV should be nowhere near this ceiling if we are doing our job well.

## 8,500 lb / 3,855 kg

This is an important FMVSS 225 child-restraint-anchorage applicability threshold for MPVs/trucks. We are expected to be far below it, so **225 applies** rather than disappearing.

## 10,000 lb / 4,536 kg

This is the major light-vehicle boundary used across many FMVSS, including ESC, AEB, TPMS, quiet-vehicle sound, interior impact, side impact/ejection and electric-powertrain requirements.

VolksMule Prototype 1 should remain comfortably below it.

A separate **6,000 lb** threshold appears in some NHTSA certification-label wording for MPVs/trucks; that is a documentation detail to track, not a reason to engineer the vehicle around 6,000 lb.

---

# 8. Being an MPV changes some rules, but it does not let us skip safety

One useful consequence of a genuine MPV classification is that the federal bumper standard in **49 CFR Part 581** is aimed at passenger motor vehicles other than MPVs. On the current MPV assumption, Part 581 is expected to be **N/A**.

That does **not** mean “no bumper engineering.” Crash energy management, pedestrian/vehicle compatibility, lamps, body protection, recovery points and practical low-speed damage remain VolksMule engineering requirements even when Part 581 itself does not govern the finished MPV.

Classification must follow the actual vehicle. We will not add cosmetic “off-road” decoration merely to obtain a regulatory label.

---

# 9. Rules for being a manufacturer, not merely rules for the car

Even a perfectly engineered physical vehicle cannot simply be sold without the manufacturer layer.

## NHTSA / DOT

- **49 CFR Part 565** — VIN requirements.
- **49 CFR Part 566** — manufacturer identification.
- **49 CFR Part 567** — certification labels and manufacturer self-certification.
- **49 CFR Part 568** — multistage manufacture, if we use that path.
- **49 CFR Part 573** — safety defect/noncompliance reporting and recall responsibility.
- **49 CFR Part 576** — record retention where applicable.
- **49 CFR Part 577** — owner notification for defects/noncompliance.
- **49 CFR Part 579** — Early Warning Reporting duties, including the duties that remain for low-volume manufacturers.
- **49 CFR Part 541** — theft-prevention/parts-marking applicability must be screened for the final line and production plan.
- **49 CFR Part 583** — parts-content labeling applicability/exemptions must be checked for vehicle class and production volume.

NHTSA uses **manufacturer self-certification**. There is no ordinary federal pre-approval certificate that substitutes for our own reasonable engineering basis and test evidence.

## Fuel-economy classification/reporting

Because an MPV may fall into the non-passenger/light-truck fuel-economy framework, screen the applicable NHTSA fuel-economy provisions, including Parts **523, 525, 526, 529, 533, 536 and 537**, against our final configuration and production volume.

Being battery electric does not make this paperwork vanish.

---

# 10. EPA still has a job even though there is no tailpipe

For a production BEV, we still need to map and execute:

- manufacturer registration in EPA's **Engines and Vehicles Compliance Information System (EV-CIS)**;
- the applicable vehicle/test-group certification path;
- required light-duty certification data;
- fuel-economy/range testing and data;
- Fuel Economy and Environment label information;
- model-year reports;
- any small-volume provisions that actually apply.

We document exemptions or special provisions only when we have verified them. We never assume “electric” means “EPA does not care.”

---

# 11. State road legality is a second map

Federal manufacture/certification and state titling/registration are different layers.

For the first physical prototype we will separately choose the first state and map:

- assembled/homebuilt/experimental title path;
- inspections;
- VIN assignment/verification interaction;
- insurance;
- temporary movement/testing permits;
- any state equipment rules that survive federal preemption.

Successful registration of one prototype is **not** evidence that a production VolksMule satisfies federal manufacturing law.

---

# 12. What this tells engineering right now

We can already make several decisions without choosing a single supplier:

1. **Target MPV, but earn the classification.** Build genuine occasional-off-road capability rather than paperwork theater.
2. **Keep GVWR <= 7,716 lb.** There is no reason for a compact two-seat Mule to wander into the heavier brake regime.
3. **Treat ESC, ABS/brake integration and future AEB as one architecture problem.** Do not select a brake controller that makes FMVSS 127 impossible later.
4. **Treat seats + belts + airbags + steering column + child tether + body structure as one restraint/crash system.** They cannot be independently shopped and bolted together at the end.
5. **Design the battery enclosure and HV system to 305a now.** Retrofitting post-crash electrical/fire safety later would be foolish.
6. **Buy regulated commodity equipment whenever sensible.** Belts, hoses, tires, glazing, lighting and similar mature parts should lead us into existing supplier ecosystems.
7. **Keep safety-critical vehicle functions independent of cloud or infotainment.** Compliance and basic vehicle control must remain local.
8. **Document every interface so parts can be substituted.** A compliant part should not become a permanent supplier prison.

---

# 13. What is still genuinely unresolved

- [ ] Freeze target curb weight, payload, GVWR and GAWR.
- [ ] Write the actual MPV/off-road feature rationale for Prototype 1.
- [ ] Freeze first intended production/model year.
- [ ] Confirm one-stage vs multistage manufacturing strategy.
- [ ] Confirm expected annual U.S. production volume for every small-volume provision.
- [ ] Decide power-window architecture and close FMVSS 118.
- [ ] Decide exact passenger-airbag / child-tether / optional lower-anchor strategy.
- [ ] Decide body opening/door/hatch configuration and recheck 206/226 details.
- [ ] Map exact test procedures and pass/fail criteria for every APPLIES row.
- [ ] Build the supplier map for every regulated commodity system.
- [ ] Choose the first prototype state and map its title/testing route.
- [ ] Re-run this entire applicability review immediately before any production certification decision.

---

# Primary live sources

Use the live regulations as authority. These are working starting points:

- 49 CFR 571.3 — vehicle definitions: https://www.ecfr.gov/current/title-49/subtitle-B/chapter-V/part-571/subpart-A/section-571.3
- 49 CFR Part 571 — Federal Motor Vehicle Safety Standards: https://www.ecfr.gov/current/title-49/subtitle-B/chapter-V/part-571
- FMVSS 127 — automatic emergency braking: https://www.ecfr.gov/current/title-49/subtitle-B/chapter-V/part-571/subpart-B/section-571.127
- FMVSS 135 — light vehicle brake systems: https://www.ecfr.gov/current/title-49/subtitle-B/chapter-V/part-571/subpart-B/section-571.135
- FMVSS 225 — child restraint anchorage systems: https://www.ecfr.gov/current/title-49/subtitle-B/chapter-V/part-571/subpart-B/section-571.225
- FMVSS 305a — electric powertrain integrity: https://www.ecfr.gov/current/title-49/subtitle-B/chapter-V/part-571/subpart-B/section-571.305a
- NHTSA manufacturer information: https://www.nhtsa.gov/vehicle-manufacturers
- EPA vehicle certification: https://www.epa.gov/ve-certification

---

## The point

This is the first real answer to **“What rules does our SUV have to follow?”**

It is not the end of compliance work. It is the map that lets us do the next work in the right order:

> **Rule -> requirement -> proof -> supplier search -> BUY / ADAPT / DONOR / DESIGN.**

And then we repeat until every box has an answer.

> **Build a vehicle that doesn't suck.**
