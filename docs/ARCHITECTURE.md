# Architecture Principles

VolksMule now has a **working Prototype 1 subsystem skeleton**, but exact components remain deliberately unfrozen. See [WHAT_GOES_IN_THE_FIRST_MULE.md](WHAT_GOES_IN_THE_FIRST_MULE.md).

This document records the decision rules that should survive individual part changes.

## Vehicle concept

Target a compact two-seat electric utility vehicle/SUV whose usefulness comes from packaging, traction, simplicity, serviceability, owner control, and replaceable systems rather than luxury feature count.

## Structure

Use a welded steel safety structure with explicit crash load paths and bolt-on front/rear cradles. Exterior non-structural panels should be individually replaceable where practical.

The battery is protected by the vehicle structure but is not the structural glue holding the vehicle together.

Avoid giant single-piece structural castings, unnecessary permanent bonding, and architectures that make ordinary collision repair require factory-scale reconstruction.

## Drivetrain

Prototype 1's working architecture is two independent electric drive axles:

- a primary front e-axle handles normal driving;
- a secondary rear e-axle contributes automatically when traction, acceleration, stability, thermal load sharing, or another validated control need calls for it.

Normal driving should not require traction-mode selection.

The behavior remains:

> **If it slips, it grips.**

Exact motors, inverters, ratios and rear-disconnect strategy remain engineering questions.

## Steering

Keep a continuous mechanical path from steering wheel to road wheels, with electric power assist. Steer-by-wire is not part of Prototype 1 unless evidence later provides an overwhelming reason to revisit the decision.

## Braking

Hydraulic four-wheel friction brakes are the base stopping system. Regenerative braking improves efficiency and feel but does not replace the friction-brake safety obligation.

ABS, ESC and AEB-capable pressure control belong in the architecture. The parking brake must use friction with mechanical retention.

## Energy storage

Start around a removable, non-structural, liquid-cooled **400-V-class LFP battery**.

The exact voltage, capacity and module format remain open until range, mass, charging, drivetrain and thermal work are completed.

Pack architecture should support safe service, isolation monitoring, a service disconnect, contactors/precharge, crash shutdown, protected venting and underside protection.

## Charging and useful power

Use SAE J3400 as the working North American charge inlet, with AC and DC charging capability.

Because VolksMule is a utility vehicle, preserve a path to useful external AC power. Higher-power bidirectional/V2H operation is desirable if it can be added safely without making Prototype 1 dependent on immature or proprietary infrastructure.

## Controls

Controls should be understandable without a tutorial. Essential visibility, safety, climate and driving functions should have dedicated physical controls where that is the clearer and more robust interface.

Automation is appropriate when it removes routine driver workload without obscuring important vehicle state or creating fragile dependencies.

Recovery/service overrides are acceptable when they solve a real problem. They should not become a wall of lifestyle modes.

## Mechanical design

Prefer assemblies that can be inspected, removed, repaired, and replaced with normal tools. Avoid unnecessary bonded, potted, serialized, or vendor-locked modules.

Design interfaces before designing bespoke parts. A component with two or three viable suppliers is usually more valuable than a marginally better component available from only one source.

Use independent coil-spring suspension with conventional replaceable dampers. Air suspension, adaptive dampers and active anti-roll hardware are not Prototype 1 requirements.

Use the smallest common wheel diameter that safely clears the final brakes and gives useful tire sidewall.

## Electronics and software

Keep vehicle-critical behavior local. Network or cloud connectivity must never be required for basic driving, unlocking, charging, diagnosis, or service.

Prototype 1 starts with a conventional **12-V low-voltage ecosystem** plus documented CAN/CAN-FD vehicle networking.

Safety-critical control should be separated from infotainment/general-purpose computing.

Document buses, connectors, message formats, control assumptions, firmware dependencies, calibration, diagnostic trouble codes, offline update methods, pairing/replacement procedures, and recovery procedures.

Security should stop attackers, not owners.

## Parts strategy

Each important part should eventually have a record containing:

- function;
- hard requirements;
- chosen part;
- viable alternates;
- supplier/source information;
- interface dimensions and electrical/software interface;
- expected service life;
- failure consequences;
- calibration/pairing requirements;
- whether local fabrication is reasonable.

The working sourcing rule is:

> **Buy the commodity. Design the distinction.**

The safety cell, battery enclosure/integration, vehicle-control orchestration, interfaces and locally manufacturable non-structural parts are likely design work. Steering, brakes, suspension corners, e-axles, cells/modules, restraints, glass, lights, latches, wipers and similar solved systems should begin with BUY/DONOR/ADAPT research.

## Validation

No subsystem graduates from concept to accepted design because it looks right in CAD. Test it. Record the test. Record failures. Revise the design.

Safety-critical systems deserve explicit validation plans before road use.

A component is not good merely because it is individually impressive. It is good when it improves the whole vehicle without creating worse dependencies elsewhere.
