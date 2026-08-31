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
- Do not begin a serious prototype BOM until the major requirement gates are understood.

## Phase 3 — Make sure everything fits

- Define target dimensions, mass, payload, range, ground clearance, seating, cargo envelope, wheel/tire envelope, and service-access requirements.
- Establish battery packaging and crash-isolation constraints.
- Produce first packaging CAD.

## Phase 4 — Make it roll, steer, and stop

- Compare donor, fabricated, and hybrid chassis/suspension/steering/brake approaches.
- Prefer proven commodity parts when they meet requirements.
- Document loads, interfaces, replacement sources, and safety margins.
- Make substitution possible through documented interfaces rather than designing the car around one supplier part.

## Phase 5 — Make it move and grip

- Evaluate electric drivetrain architectures capable of the `if it slips, it grips` behavior.
- Prototype slip detection and second-axle engagement logic.
- Test transition behavior on low-friction surfaces at controlled speeds.
- Define degraded/failure modes.

## Phase 6 — Make the electricity behave

- Define low-voltage architecture, HV isolation, contactors, charging, instrumentation, diagnostics, and local vehicle control.
- Ensure basic vehicle operation never depends on cloud services.
- Publish wiring and interface documentation.

## Phase 7 — Make a parts list people can actually use

- Build a BOM with alternates.
- For each subsystem, explicitly choose BUY, ADAPT, DONOR, or DESIGN.
- Publish CAD/drawings for locally manufacturable parts.
- Identify which parts are appropriate for additive manufacturing and which require conventional fabrication.
- Document tooling and assembly procedures.
- Record alternate suppliers and substitution interfaces wherever practical.

## Phase 8 — Prove it works

- Static structural checks.
- Brake and steering validation.
- Electrical fault testing.
- Battery and thermal safety testing.
- Regulatory verification tests as applicable.
- Low-speed closed-course drivability and traction testing.
- Progressive road testing only after prerequisite safety gates are satisfied.

## Phase 9 — Make it repeatable

A successful VolksMule is not merely one working vehicle. The documentation should be good enough that another competent builder can understand the design, source parts or equivalents, reproduce the important assemblies, and know what still requires validation.
