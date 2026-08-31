# VolksMule Canon

This file records the durable project principles. Detailed engineering may change; these principles should change only intentionally.

## 1. Purpose

**Mission: Build a vehicle that doesn’t suck.**

VolksMule is a passion project, and that is intentional. It should optimize for conviction, utility, engineering sense, and the builder's standards rather than market fashion, startup pressure, focus groups, or the need to justify itself commercially.

The guiding question is:

> What would a vehicle look like if the best existing ideas were organized correctly and unnecessary nonsense was refused?

## 2. Normal driving must be simple

The driver should not need to manage a collection of traction modes during ordinary use. Normal operation should feel calm and uncomplicated.

Extra traction is an ace in the sleeve, not a reason to drive faster in snow, ice, mud, or loose terrain.

## 3. If it slips, it grips

The preferred 4x4 behavior is automatic on-demand traction:

- One axle handles normal driving when conditions allow.
- When the primary axle slips, the second axle engages automatically.
- The transition should require no routine driver intervention.
- A manual override may exist only if engineering shows it is useful for recovery, testing, or service; it is not intended as a normal driving-mode selector.

This philosophy is inspired by the simple behavior of older Honda Real Time 4WD systems, not by any requirement to reproduce their exact mechanism.

## 4. Repairability is a first-class requirement

The project should avoid the failure mode where a useful vehicle becomes economically dead because one proprietary supplier stops supporting a part.

Prefer, where practical:

- commodity components;
- multiple possible suppliers;
- documented interfaces;
- locally fabricable brackets, housings, trim, ducts, and fixtures;
- 3D-printable parts when the material and load case make sense;
- replaceable modules instead of sealed assemblies;
- ordinary fasteners and service tools.

Not every safety-critical or high-load part should be 3D printed. Manufacturability follows engineering reality, not ideology.

## 5. Reuse good ideas

VolksMule does not need to reinvent every wheel. Existing vehicles, especially simple and durable utility vehicles, can serve as reference designs and experimental baselines.

A proven arrangement may be studied, measured, reproduced conceptually, simplified, updated, or replaced. The goal is to understand why something worked and preserve the useful principle without inheriting unnecessary vendor dependence.

## 6. Utility beats feature count

Every feature must earn its complexity, mass, cost, failure modes, and maintenance burden.

Prefer:

- useful cargo volume;
- straightforward controls;
- robust visibility;
- easy ingress/egress;
- accessible service points;
- understandable failure modes;
- modularity where it reduces long-term burden.

## 7. Open development should produce reproducible knowledge

The project should document not only what was chosen, but why.

Useful artifacts include:

- dimensions and CAD;
- part specifications and alternates;
- wiring diagrams;
- software and control logic;
- test procedures;
- failure reports;
- measurement data;
- assumptions and rejected alternatives.

## 8. Safety is not implied by openness

Open-source documentation does not make a vehicle safe. Roadworthiness, crash performance, braking, steering, battery safety, electromagnetic compatibility, and regulatory compliance require explicit engineering and validation.

Prototype status must always be stated plainly.

## 9. Architecture is allowed to evolve

The drivetrain, chassis, suspension, battery system, controls, dimensions, and materials remain engineering questions until supported by evidence. Canon should constrain philosophy, not prematurely freeze solutions.

## 10. The computer does not own the vehicle

The vehicle computer may **inform, coordinate, optimize, log, diagnose, and assist**. It does not become the owner or sole gatekeeper of basic vehicle functions.

Prototype 1 should prefer physical, tactile controls for frequent driving functions: knobs, switches, stalks, levers, and buttons. A screen may display information and expose secondary configuration, but it should not be the only practical way to operate core functions.

The loss or failure of any of the following must not unnecessarily disable the basic vehicle:

- infotainment computer or center display;
- phone;
- companion application;
- internet connection;
- cloud service;
- user account or subscription.

Where electrically practical, core controls should have direct, local control paths. Where a controller is required, the control interface should remain documented, local, deterministic, and independently serviceable.

Core functions that should not depend on an infotainment surface include, at minimum:

- steering and braking;
- propulsion enable / drive selection;
- hazard lamps;
- exterior lighting;
- wipers and washers;
- windshield defrost / demist;
- essential HVAC control;
- door access and interior release;
- parking brake or equivalent hold function;
- rear visibility required for safe backing;
- recovery and service functions.

Convenience electrification is optional. Power windows, power locks, motorized handles, powered seats, and similar features are not requirements. Prefer the mechanical solution when it is cheaper, simpler, and easier to repair; use a powered solution only when it wins on the whole-system trade without creating unnecessary dependency.

Software may make the vehicle better. It must not make ownership conditional.
