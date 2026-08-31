# VolksMule

> **Mission: Build a vehicle that doesn’t suck.**

VolksMule is an experimental, open-development vehicle project exploring a simple, repairable, compact two-seat electric utility vehicle with automatic on-demand extra traction.

The project is deliberately not optimized around automotive fashion, focus groups, startup theater, or feature accumulation. The question is simpler: **what would a useful vehicle look like if proven ideas were organized correctly and unnecessary nonsense was refused?**

## Core idea

- Calm, simple normal driving.
- Electric drivetrain.
- Compact two-seat utility packaging.
- Automatic on-demand second-axle traction: **if it slips, it grips.**
- Repairability and serviceability over proprietary lock-in.
- Commodity/off-the-shelf parts where sensible.
- Printable or locally manufacturable parts where practical.
- Open documentation and reproducible engineering.
- No assumption that more driven wheels justify higher speed in poor conditions.

## Project status

VolksMule is an early engineering and documentation project. Architecture, dimensions, components, and safety systems are not frozen. Nothing in this repository should be treated as road-ready, certified, or production-approved unless explicitly documented as such.

Start with [docs/CANON.md](docs/CANON.md), then read [what the car needs](docs/WHAT_THE_CAR_NEEDS.md), [what rules our SUV has to follow](docs/WHAT_RULES_OUR_SUV_HAS_TO_FOLLOW.md), [what goes in the first Mule](docs/WHAT_GOES_IN_THE_FIRST_MULE.md), and [how big the first Mule should be](docs/HOW_BIG_THE_FIRST_MULE_SHOULD_BE.md). The first integrated packaging bridge is [Revision-A interface envelopes](docs/REV_A_INTERFACE_ENVELOPES.md), with focused follow-on screens for [Revision-A windshield candidates](docs/REV_A_WINDSHIELD_CANDIDATES.md), the [Revision-A READ2982 drive-unit envelope](docs/REV_A_READ2982_ENVELOPE.md), the [Revision-A rear e-axle envelope](docs/REV_A_REAR_EAXLE_ENVELOPE.md), the [Revision-A MIDA EVCC charging-controller envelope](docs/REV_A_MIDA_EVCC_ENVELOPE.md), the [Revision-A steering / EPS envelope](docs/REV_A_STEERING_EPS_ENVELOPE.md), the [Revision-A occupant / manual-seat envelope](docs/REV_A_OCCUPANT_SEAT_ENVELOPE.md), the [Revision-A REPT BEV-cell envelope](docs/REV_A_REPT_CELL_ENVELOPE.md), the [Revision-A BMS physical envelope](docs/REV_A_BMS_PHYSICAL_ENVELOPE.md), the [Revision-A J3400 vehicle-inlet envelope](docs/REV_A_J3400_INLET_ENVELOPE.md), the [Revision-A thermal / HVAC packaging envelope](docs/REV_A_THERMAL_PACKAGING_ENVELOPE.md), the [Revision-A brake-corner envelope](docs/REV_A_BRAKE_CORNER_ENVELOPE.md), and the [Revision-A transparent BDU / PDU envelope](docs/REV_A_BDU_PDU_ENVELOPE.md).

Alibaba/Chinese-supplier work is split deliberately: broad catalog archaeology is closed, but **roadmap-driven part sourcing remains active**. See the clarified [Alibaba sourcing boundary](docs/ALIBABA_SOURCE_MISSION_CLOSEOUT.md), the working [Alibaba sourcing ledger](docs/ALIBABA_SOURCING.md), the [coverage audit](docs/ALIBABA_COVERAGE_AUDIT.md), the current [procurement queue](docs/ALIBABA_PROCUREMENT_QUEUE.md), and the [Wave-1 supplier RFQ packet](docs/ALIBABA_RFQ_WAVE1.md). Current roadmap continuation files include the [Phase-5 roll/steer/stop chassis candidate screen](docs/ALIBABA_PHASE5_CHASSIS_CANDIDATES.md), the [Phase-6 CV / halfshaft / wheel-speed support screen](docs/ALIBABA_PHASE6_DRIVE_SUPPORT.md), and the [Phase-7 12-V service-hardware screen](docs/ALIBABA_PHASE7_12V_SERVICE_HARDWARE.md).

Detailed sourcing screens cover [structure / cradles / battery-enclosure fabrication](docs/ALIBABA_STRUCTURE_FABRICATION.md), the [e-axle candidates](docs/ALIBABA_EAXLE_CANDIDATES.md), [OBC / DC-DC / PDU](docs/ALIBABA_OBC_POWER_ELECTRONICS.md), [J3400 vehicle-side charging](docs/ALIBABA_J3400_CHARGING.md), [400-V automotive BMS](docs/ALIBABA_BMS_CANDIDATES.md), [LFP cells / modules](docs/ALIBABA_LFP_CELLS_MODULES.md), [high-voltage safety plumbing](docs/ALIBABA_HV_SAFETY_PLUMBING.md), [utility power / V2L](docs/ALIBABA_UTILITY_POWER_V2L.md), [thermal management](docs/ALIBABA_THERMAL_MANAGEMENT.md), [steering / EPS](docs/ALIBABA_STEERING_EPS.md), [brakes / ABS / ESC](docs/ALIBABA_BRAKES_ESC.md), [suspension corners](docs/ALIBABA_SUSPENSION_CORNERS.md), [visibility hardware](docs/ALIBABA_VISIBILITY_HARDWARE.md), [seats / restraints](docs/ALIBABA_SEATS_RESTRAINTS.md), [wheels / tires / recovery](docs/ALIBABA_WHEELS_TIRES_RECOVERY.md), [body controls / doors](docs/ALIBABA_BODY_CONTROLS_DOORS.md), [driver commands / key / pedals / selector / instrumentation](docs/ALIBABA_DRIVER_COMMANDS_INSTRUMENTS.md), [low-voltage / CAN / diagnostics](docs/ALIBABA_LOW_VOLTAGE_NETWORK.md), and [required safety automation](docs/ALIBABA_SAFETY_AUTOMATION.md).

## Name notice

**VolksMule is a development/project name.** This project is independent and is not affiliated with, sponsored by, endorsed by, or connected to Volkswagen AG, Volkswagen Group, Honda Motor Co., or any other vehicle manufacturer. See [NOTICE.md](NOTICE.md).

## License

No open-source license has been selected yet. Until one is added explicitly, normal copyright restrictions apply to repository contents. The intent is open development; the exact licensing model will be chosen deliberately rather than accidentally.
