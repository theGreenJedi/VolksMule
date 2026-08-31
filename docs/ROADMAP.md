# Roadmap

This roadmap is intentionally ordered from understanding to commitment. It should prevent premature component shopping from becoming architecture by accident.

## Phase 0 — Write down the rules

- Establish `main` as the working/default branch.
- Record durable project principles.
- Add project-name and affiliation notice.
- Choose an explicit open-source licensing strategy before inviting broad reuse.
- Keep design decisions traceable.

## Phase 1 — Study what already works

- Document useful reference vehicles and mechanisms.
- Measure packaging, seating, cargo, suspension, steering, drivetrain, and service access where practical.
- Record what should be preserved as a principle and what should be discarded.
- Treat the Honda-inspired automatic on-demand traction behavior as a reference behavior, not a requirement to clone proprietary hardware.

## Phase 2 — Write down what the car needs

- Build and maintain [the master requirements checklist](WHAT_THE_CAR_NEEDS.md).
- Maintain [the working rules map for Prototype 1](WHAT_RULES_OUR_SUV_HAS_TO_FOLLOW.md).
- Use **MPV** as Prototype 1's working federal classification and prove that the finished design genuinely qualifies.
- Keep the working GVWR at or below **3,500 kg / 7,716 lb** unless a compelling engineering reason says otherwise.
- Identify every applicable federal safety, manufacturer, EPA, labeling, reporting, and state-road-use requirement.
- Turn every screened rule into APPLIES, APPLIES LATER, CONDITIONAL, EQUIPMENT, N/A, or VERIFY with a written reason.
- Write requirements as functions/performance first and components second.
- Define how each requirement will eventually be verified.
- Use the regulatory list as a map to existing suppliers that already build compliant components.

## Phase 3 — Decide what goes in the first Mule

- Use [the subsystem skeleton](WHAT_GOES_IN_THE_FIRST_MULE.md) as the working architecture.
- Choose the **kind** of solution before choosing exact part numbers.
- Keep a welded steel safety cell with bolt-on front/rear cradles and replaceable non-structural panels.
- Keep a real mechanical steering path with electric assist.
- Keep hydraulic four-wheel friction brakes as the stopping foundation, with ABS/ESC/AEB pressure control and regenerative braking layered around them.
- Use a front-primary electric e-axle and automatic on-demand rear e-axle.
- Start battery engineering around a removable, non-structural, liquid-cooled **400-V-class LFP** pack.
- Use SAE J3400 charging with both AC and DC capability.
- Keep the low-voltage/service ecosystem conventional at **12 V** unless evidence gives us a reason to move.
- Keep safety-critical vehicle control separate from infotainment/cloud systems.
- Prefer physical controls for essential driving, visibility, and climate functions.
- Explicitly refuse complexity that has no useful job.
- For each subsystem, record what is BUY, DONOR, ADAPT, DESIGN, and what remains intentionally undecided.

## Phase 4 — Make the chosen systems coexist

- Use [the working size and packaging envelope](HOW_BIG_THE_FIRST_MULE_SHOULD_BE.md) as the starting box.
- Keep Prototype 1 roughly first-generation-CR-V scale unless safety or engineering provides a concrete reason to move.
- Aim for a curb weight at or below **4,200 lb**, preferably below **4,000 lb**, and a working GVWR around **5,500 lb or less** while preserving at least about **1,000 lb payload**.
- Design for genuine occasional off-road geometry and protection rather than SUV styling alone.
- Preserve a two-seat utility interior with a flat cargo floor, useful tool storage, and a practical sleeping/work platform.
- Compare candidate subsystem families against the whole vehicle, not just their individual specifications.
- Reject a component if making it fit damages the vehicle more than its extra performance is worth.
- Establish battery packaging and crash-isolation constraints before freezing pack capacity.
- Produce first packaging CAD showing occupants, restraints, crash structure, suspension travel, battery, drive units, cargo space, service paths, ground-clearance geometry, axle loads, and turning circle.

## Phase 5 — Make it roll, steer, and stop

- Compare candidate suspension, steering and brake families inside the architecture already chosen.
- Prefer proven commodity parts when they meet requirements.
- Document loads, interfaces, replacement sources, calibration needs, and safety margins.
- Make substitution possible through documented interfaces rather than designing the car around one supplier part.
- Bench-test steering assist, brake actuation, ABS/ESC integration and parking-brake behavior before road testing.

## Phase 6 — Make it move and grip

- Compare front and rear e-axle candidates that support the chosen dual-e-axle architecture.
- Prototype slip detection and automatic rear-axle contribution logic.
- Tune normal driving so the secondary axle disappears until useful.
- Test transition behavior on low-friction surfaces at controlled speeds.
- Define degraded/failure modes and thermal limits.

## Phase 7 — Make the electricity behave

- Define 400-V-class pack voltage/capacity, cells/modules, BMS, HV isolation, contactors, charging and thermal architecture.
- Define the 12-V power distribution, CAN/CAN-FD networks, instrumentation and diagnostics.
- Ensure basic vehicle operation never depends on cloud services.
- Provide offline service/update/recovery paths.
- Publish wiring, connector, message and interface documentation.
- Preserve an architecture path for useful external AC power and later bidirectional/V2H capability without making it a Prototype 1 blocker.

## Phase 8 — Make a parts list people can actually use

- Build a BOM with alternates.
- For each subsystem, explicitly choose BUY, ADAPT, DONOR, or DESIGN.
- Publish CAD/drawings for locally manufacturable parts.
- Identify which parts are appropriate for additive manufacturing and which require conventional fabrication.
- Document tooling and assembly procedures.
- Record alternate suppliers and substitution interfaces wherever practical.
- Mark every component whose disappearance could immobilize the vehicle.

## Phase 9 — Prove it works

- Static structural checks.
- Brake and steering validation.
- Electrical fault testing.
- Battery and thermal safety testing.
- Regulatory verification tests as applicable.
- Low-speed closed-course drivability and traction testing.
- Progressive road testing only after prerequisite safety gates are satisfied.
- Record failures as engineering data rather than hiding them.

## Phase 10 — Make it repeatable

A successful VolksMule is not merely one working vehicle. The documentation should be good enough that another competent builder can understand the design, source parts or equivalents, reproduce the important assemblies, and know what still requires validation.
