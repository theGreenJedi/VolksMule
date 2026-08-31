# Roadmap

This roadmap is intentionally ordered from understanding to commitment. It should prevent premature component shopping from becoming architecture by accident.

## Phase 0 — Canon and project hygiene

- Establish `main` as the working/default branch.
- Record durable project principles.
- Add project-name and affiliation notice.
- Choose an explicit open-source licensing strategy before inviting broad reuse.
- Keep design decisions traceable.

## Phase 1 — Reference study

- Document useful reference vehicles and mechanisms.
- Measure packaging, seating, cargo, suspension, steering, drivetrain, and service access where practical.
- Record what should be preserved as a principle and what should be discarded.
- Treat the Honda-inspired automatic on-demand traction behavior as a reference behavior, not a requirement to clone proprietary hardware.

## Phase 2 — Requirements and packaging

- Define target dimensions, mass, payload, range, ground clearance, seating, cargo envelope, wheel/tire envelope, and service-access requirements.
- Establish battery packaging and crash-isolation constraints.
- Produce first packaging CAD.

## Phase 3 — Chassis, suspension, steering, and brakes

- Compare donor, fabricated, and hybrid approaches.
- Prefer proven commodity parts when they meet requirements.
- Document loads, interfaces, replacement sources, and safety margins.

## Phase 4 — Electric drivetrain and traction

- Evaluate architectures capable of the `if it slips, it grips` behavior.
- Prototype slip detection and second-axle engagement logic.
- Test transition behavior on low-friction surfaces at controlled speeds.
- Define degraded/failure modes.

## Phase 5 — Electrical and controls

- Define low-voltage architecture, HV isolation, contactors, charging, instrumentation, diagnostics, and local vehicle control.
- Ensure basic vehicle operation never depends on cloud services.
- Publish wiring and interface documentation.

## Phase 6 — Parts catalog and fabrication package

- Build a BOM with alternates.
- Publish CAD/drawings for locally manufacturable parts.
- Identify which parts are appropriate for additive manufacturing and which require conventional fabrication.
- Document tooling and assembly procedures.

## Phase 7 — Prototype validation

- Static structural checks.
- Brake and steering validation.
- Electrical fault testing.
- Battery and thermal safety testing.
- Low-speed closed-course drivability and traction testing.
- Progressive road testing only after prerequisite safety gates are satisfied.

## Phase 8 — Reproducibility

A successful VolksMule is not merely one working vehicle. The documentation should be good enough that another competent builder can understand the design, source parts or equivalents, reproduce the important assemblies, and know what still requires validation.
