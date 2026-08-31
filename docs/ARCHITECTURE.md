# Architecture Principles

VolksMule is still pre-architecture. This document defines decision rules rather than pretending that untested component choices are settled.

## Vehicle concept

Target a compact two-seat electric utility vehicle/SUV whose usefulness comes from packaging, traction, simplicity, and serviceability rather than luxury feature count.

## Drivetrain

The preferred behavioral model is automatic on-demand extra traction. Normal driving should not require mode selection. The second driven axle should engage when the primary axle loses traction, subject to whatever control strategy proves mechanically and electrically sound.

Potential implementations may include dual motors, a mechanically coupled secondary axle, or another architecture. The behavior is canon; the mechanism is not yet frozen.

## Controls

Controls should be understandable without a tutorial. Automation is appropriate when it removes routine driver workload without obscuring important vehicle state or creating fragile dependencies.

Recovery/service overrides are acceptable when they solve a real problem. They should not become a wall of lifestyle modes.

## Mechanical design

Prefer assemblies that can be inspected, removed, repaired, and replaced with normal tools. Avoid unnecessary bonded, potted, serialized, or vendor-locked modules.

Design interfaces before designing bespoke parts. A component with two or three viable suppliers is usually more valuable than a marginally better component available from only one source.

## Electronics and software

Keep vehicle-critical behavior local. Network or cloud connectivity must never be required for basic driving, unlocking, charging, diagnosis, or service.

Document buses, connectors, message formats, control assumptions, firmware dependencies, and recovery procedures.

## Parts strategy

Each important part should eventually have a record containing:

- function;
- specification;
- chosen part;
- viable alternates;
- supplier/source information;
- interface dimensions;
- expected service life;
- failure consequences;
- whether local fabrication is reasonable.

## Validation

No subsystem graduates from concept to accepted design because it looks right in CAD. Test it. Record the test. Record failures. Revise the design.

Safety-critical systems deserve explicit validation plans before road use.
