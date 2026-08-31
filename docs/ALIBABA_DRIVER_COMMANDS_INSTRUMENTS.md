# VolksMule driver commands and instrumentation sourcing screen

Research date: **2026-08-31**

This document covers the pieces directly between the driver and the vehicle:

- starting/authorization;
- accelerator pedal;
- brake-pedal input and shift interlock;
- drive-direction/gear selection;
- parking-brake command;
- instrument cluster;
- warning telltales;
- local status/diagnostic display behavior.

It inherits the project canon:

> **The computer does not own the vehicle.**

The purpose of this screen is not to make the cockpit primitive. It is to make direct vehicle authority **obvious, local, tactile, replaceable, and independent of infotainment/cloud systems**.

---

# 1. Prototype 1 starting architecture — physical key

## Decision

Prototype 1 baseline is a **conventional physical key**, not push-to-start.

Working positions:

**LOCK/OFF -> ACC -> RUN/READY**

An EV does not need a spring-loaded engine-crank position. RUN/READY requests vehicle wake-up and, once safety conditions are satisfied, enables the traction system.

## Why a physical key wins

A keyed switch provides:

- local authority;
- an obvious physical vehicle state;
- cheap replacement;
- no proximity-fob battery;
- no RF antennas around the cabin;
- no phone/app/cloud requirement;
- no pairing account;
- no body-computer dependency merely to authorize ordinary use.

Push-to-start may remain a future optional variant if it later proves cheaper or materially better without compromising owner control. It is **not** the Prototype 1 architecture.

## Regulatory notes

FMVSS No. 114 covers theft protection and rollaway prevention. NHTSA interpretations make clear that a conventional physical key is entirely compatible with the standard and that, when the key is removed, the key-locking system must prevent normal activation of the vehicle motor and either steering or forward self-mobility as applicable.

A vehicle with an automatic transmission/gear selection system that includes Park and is within the applicable GVWR range must also use brake-transmission shift interlock behavior: the service brake must be depressed before shifting out of Park in starting-system positions where shifting is possible.

Useful references:

- https://www.nhtsa.gov/interpretations/katz1
- https://www.nhtsa.gov/interpretations/alliance-114
- https://www.nhtsa.gov/document/laboratory-test-procedure-fmvss-114-theft-protection-and-rollaway-prevention

## Prototype behavior target

- key removed -> traction cannot be enabled;
- OFF -> no drive request accepted;
- ACC -> accessory loads only;
- RUN/READY -> safety checks execute and READY may become available;
- Park exit requires brake-pedal confirmation;
- key removal must not leave a condition that permits uncontrolled self-mobility;
- a documented mechanical/service method must exist for towing/recovery when 12-V power is unavailable.

---

# 2. Accelerator pedal — electronic, but simple and redundant

An EV necessarily converts pedal position into an electronic torque request. That does **not** justify making the pedal a networked black box.

## Preferred architecture

Use a conventional automotive electronic accelerator pedal with:

- two independent/redundant position channels;
- Hall-effect/contactless sensing preferred;
- physical return spring(s);
- direct 5-V/signal wiring to the safety-relevant controller rather than infotainment;
- documented transfer curves;
- connector and pinout documentation;
- plausibility checking in the VCU;
- immediate zero-torque/degraded response on implausible channel disagreement.

## Regulatory design gate

FMVSS No. 124 requires accelerator-control behavior that returns motive power to idle/zero propulsion when the driver removes actuating force and addresses accelerator-control failures. NHTSA has long applied the standard to electronic accelerator controls as well as mechanical systems.

Useful references:

- https://www.nhtsa.gov/interpretations/7633
- https://www.nhtsa.gov/document/federal-motor-vehicle-safety-standards-accelerator-control-systems-march-2012

The final Prototype 1 accelerator implementation must be validated against the **current regulatory text in force at the vehicle's certification date**.

---

# 3. Strongest Alibaba pedal/selector lead — Xiamen Wayou / Jieou

## Supplier

**Xiamen Wayou Automotive Electronic Co., Ltd. / Xiamen Jieou Automotive Electronics**

Current manufacturer material states:

- founded 2005;
- products include electronic accelerator pedals, electronic gear shifters, control handles and automotive sensors;
- IATF 16949 automotive quality-system certification;
- VDA 6.3/6.5 process-quality audit history;
- approximately hundreds of thousands of automotive electronic assemblies per year.

Manufacturer:

- https://www.xmjieou.com/en/
- https://www.xmjieou.com/

Alibaba currently exposes Wayou/Jieou accelerator pedals including:

- `J-DS89(PS)-MT` electronic pedal, MOQ 2;
- `J-P0137A(3103)` electronic-car accelerator pedal, MOQ 2;
- several new-energy-vehicle pedal families in roughly the low-tens-of-dollars sample-price range.

Alibaba discovery references:

- https://autopart.alibaba.com/product/electric-car-accelerator
- https://www.alibaba.com/pla/Electronic-Car-Accelerator-Pedal-J-P0137A3103_1601266306006.html

## Verdict

**GREEN-YELLOW — CONTACT NOW / DOCS FIRST / SAMPLE AFTER DOCS.**

Wayou/Jieou is currently the best-shaped Alibaba-accessible source for the **driver torque-request pedal** and potentially the **physical drive selector**.

## RFQ — accelerator pedal

Ask for:

1. exact model recommended for a left-hand-drive passenger/MPV EV;
2. dimensional drawing / STEP model;
3. mounting-bolt pattern;
4. pedal travel and pedal-force curve;
5. return-spring architecture;
6. sensor technology;
7. number of independent signal channels;
8. signal voltage transfer curves and tolerances;
9. independent power/ground strategy if available;
10. connector manufacturer and mating connector;
11. operating-temperature range;
12. ingress/environmental rating;
13. EMC/ESD data;
14. endurance-cycle data;
15. failure modes for open/short/channel disagreement;
16. PPAP/APQP availability;
17. sample pricing for 2–5 units;
18. production pricing at 10/100/1000 quantities.

## Purchase gate

Do **not** buy merely because it says Hall sensor or EV pedal.

A candidate passes only when the two-channel relationship, pinout, pedal-force/return behavior and fault response are documented well enough to implement deterministic plausibility checking.

---

# 4. Drive selector — physical control, electronic command

The e-axles do not require a mechanical transmission linkage. Direction/park state is therefore an electronic command by nature.

That does not require a touchscreen.

## Preferred Prototype 1 interface

A **small physical selector with positive detents**, likely either:

- rotary **P-R-N-D** knob; or
- short conventional P-R-N-D lever.

The selector must provide tactile confirmation and a clear selected-state indication.

### Why rotary deserves first study

A rotary selector fits the project's preference for knobs and saves console space without hiding the control in a screen.

It should be treated as a **real physical switch/sensor**, not a cosmetic input routed through Android/infotainment.

## Required behavior

- Park state clear and unambiguous;
- brake pedal required to leave Park as applicable;
- reverse request accepted only under defined speed/torque conditions;
- loss of selector communication cannot create unexpected drive torque;
- current selected position shown in the dedicated cluster;
- towing/service neutral procedure documented;
- manual/service Park release provided if the chosen parking mechanism requires it;
- no automatic electronic "guessing" of the driver's intended direction.

## FMVSS considerations

FMVSS Nos. 102, 114 and 101 interact with gear selection, shift-position indication and brake-shift interlock requirements. NHTSA interpretation material states that vehicles with automatic-transmission-type shift positions must display the selected position and that vehicles with Park within the applicable class require the service brake before leaving Park.

Useful references:

- https://www.nhtsa.gov/interpretations/nht93-535
- https://www.nhtsa.gov/interpretations/1984-132
- https://www.nhtsa.gov/interpretations/alliance-114

Final applicability to the particular single-speed EV architecture must be confirmed against current rules before certification.

## Wayou/Jieou selector path

Wayou/Jieou's own product catalog includes **electronic shifters including rotary products**.

**Verdict:** YELLOW-GREEN.

RFQ must ask for:

- rotary/lever EV selector models;
- detent architecture;
- outputs (hardwired discrete, analog, CAN/LIN);
- electrical truth table / DBC where relevant;
- mechanical drawing;
- illumination/telltale behavior;
- expected-life cycles;
- IP/environmental ratings;
- fault-state behavior;
- sample availability.

### Preference

If a simple hardwired Gray-code/discrete selector is available, it deserves first study over a proprietary CAN-only selector. CAN is acceptable if fully documented and fault behavior is deterministic.

---

# 5. Brake pedal and shift interlock

The service brake remains a hydraulic braking foundation. The driver-command architecture therefore keeps:

- physical brake pedal;
- mechanical pedal box;
- hydraulic master-cylinder actuation / validated brake-system interface;
- redundant brake-pedal/brake-light state sensing as needed for ESC/AEB/regen/BTSI;
- no dependence on infotainment for brake recognition.

The brake switch/sensor is also part of:

- brake lamps;
- Park shift interlock;
- regen blending;
- cruise cancellation if cruise exists;
- AEB/ESC coordination;
- READY-state logic where required.

The brake pedal itself should be sourced/integrated with the brake-system study rather than purchased as unrelated cosmetic hardware.

---

# 6. Parking brake — physical retention, physical control preferred

Prototype 1 already prefers a **real friction parking brake with mechanical retention**.

First study remains:

- conventional hand lever or foot-operated mechanical cable;
- simple mechanical release;
- local adjustment/service;
- dashboard PARK BRAKE warning switch/telltale.

An electronic parking brake should only displace this if packaging or regulatory/system evidence makes it materially better.

A console hand lever remains extremely attractive because it makes park-brake state mechanically obvious and retains function without software.

---

# 7. Instrument cluster — dedicated vehicle appliance, not infotainment

## Architecture

Prototype 1 should have a **dedicated instrument cluster** that boots independently of infotainment and displays the information needed to safely operate the vehicle.

Minimum information/telltale set will be driven by the current FMVSS map, but the working cluster should include at least:

- vehicle speed;
- selected P/R/N/D state;
- READY state;
- high-voltage/propulsion fault;
- battery state of charge;
- charging status as useful;
- brake-system warning;
- ABS warning;
- ESC warning;
- airbag/restraint warning;
- TPMS warning;
- turn signals/hazard;
- high beam;
- parking-brake state;
- seat-belt warning;
- critical thermal warnings;
- 12-V/charging-system fault as applicable;
- odometer/trip information as required/useful.

The center infotainment display may repeat this information. It is not the authoritative source.

## FMVSS 101 principle

NHTSA's FMVSS 101 material requires applicable controls, telltales and indicators to be located, identified, visible and illuminated appropriately. Certain warnings have prescribed identifiers/colors under FMVSS 101 and related standards.

Useful references:

- https://www.nhtsa.gov/interpretations/2671o
- https://www.nhtsa.gov/interpretations/ncc-230927-001-fmvss-135-telltale-st-pierre-canoo

This strongly supports a dedicated, deterministic instrument appliance rather than relying on a consumer operating system.

---

# 8. Cluster supplier screen

## Wuhan Green Electronic Instruments

Current manufacturer/supplier material describes:

- dedicated automobile and new-energy-vehicle instrumentation;
- IATF 16949 quality-system history;
- CAN-connected EV instrument clusters;
- development/manufacturing focused on heavy-truck and electric-vehicle instruments.

One current E629 EV cluster uses:

- CAN bus vehicle data;
- physical pointer speed/tach displays plus a 5-inch LCD;
- 12-V power;
- EV battery/motor information.

This is philosophically much closer to VolksMule than an Android "smart cockpit."

References:

- https://greenyb.en.made-in-china.com/
- https://greenyb.en.made-in-china.com/product/VdRTNHLwMPkF/China-Electric-Vehicle-Main-Instrument-Panel-Cluster-for-Electric-Bus-Car-Accessories-E629.html

### Verdict

**YELLOW-GREEN — CONTACT / CUSTOM RFQ.**

It is not currently the strongest Alibaba-native lead, but it is a strong Chinese supplier benchmark and potential direct source.

Ask for:

- passenger-vehicle/MPV cluster families;
- custom CAN DBC support;
- CAN-FD support if required;
- physical telltale implementation;
- FMVSS 101 identifier/color customization;
- sunlight readability;
- night dimming;
- startup time;
- operating temperature;
- reverse-polarity/load-dump/ESD/EMC validation;
- local firmware update path;
- connector drawings;
- sample and custom NRE pricing.

## KLYDE/NH-Tech — secondary benchmark

KLYDE currently advertises IATF 16949 and custom TFT instrument-cluster manufacturing.

Reference:

- https://klyde.com.cn/about/

Useful as a supplier benchmark, but VolksMule does **not** need its broader Android/CarPlay smart-cockpit stack merely to obtain instrumentation.

### Rule

If a supplier insists that the instrument display and infotainment system must be one inseparable Android computer, reject that architecture.

---

# 9. Local replacement benchmark for accelerator hardware

Alibaba pricing may be attractive for initial samples, but the pedal interface should remain sufficiently documented that a future alternate can be adapted.

Current U.S. parts channels carry replacement electronic accelerator-pedal assemblies from Hella, Dorman/Carquest and others. That demonstrates the broader automotive ecosystem is not inherently exotic.

VolksMule's goal is **not** necessarily to use a local aftermarket pedal as the first design part. The goal is to avoid creating a pedal/VCU interface that only one obscure supplier can ever satisfy.

---

# 10. Driver-command failure philosophy

A driver's command must fail in the safer direction.

## Accelerator failure

- no valid redundant correlation -> zero propulsion torque / controlled degraded mode;
- pedal released -> torque request returns to zero;
- one failed signal cannot silently become full torque.

## Selector failure

- ambiguous selector state -> no new propulsion-direction command;
- direction reversal cannot occur because one message bit flipped;
- selected state remains clearly indicated.

## Key/start failure

- infotainment failure does not prevent use;
- cloud loss does not prevent use;
- physical key authorization remains local;
- a failed accessory circuit must not automatically disable steering/brakes.

## Cluster failure

- vehicle-control ECUs continue their safety functions;
- cluster failure is detectable;
- cluster replacement/reflash can be performed locally;
- infotainment is not the emergency fallback required for vehicle control.

---

# 11. Prototype 1 recommendation

## Baseline

1. **Physical key** with LOCK/OFF, ACC and RUN/READY states.
2. **Wayou/Jieou dual-channel Hall-effect accelerator pedal candidate** after documentation review.
3. **Physical rotary P-R-N-D selector** if Wayou/Jieou can provide a documented, deterministic model; otherwise a short physical lever or a simple custom hardwired detent selector.
4. **Hydraulic physical brake pedal** with validated brake-state sensing and brake-shift interlock.
5. **Mechanical parking-brake lever/cable** unless later packaging proves another solution better.
6. **Dedicated CAN instrument cluster** independent of infotainment; Wuhan Green Electronic is first Chinese custom-cluster conversation.
7. Center screen remains optional navigation/media/deeper-diagnostics equipment.

This is the cockpit equivalent of the broader VolksMule sourcing philosophy:

> **Use electronics where the vehicle physics require them. Keep the driver's authority physical, obvious and local.**

---

# 12. Next actions

1. Contact Wayou/Jieou for pedal datasheet, dual-channel transfer curves, CAD and sample pricing.
2. Request its rotary-shifter catalog and interface documentation.
3. Contact Wuhan Green Electronic for a simple 12-V CAN EV cluster built to a VolksMule signal/telltale matrix.
4. Add the candidate pedal and selector to bench fault-injection planning.
5. Define Prototype 1's key-switch electrical truth table.
6. Define the Park/brake/READY state machine in the VCU architecture.
7. Build the FMVSS-required telltale matrix before freezing the cluster face/layout.
8. Keep every driver-command interface documented so another supplier can replace it later.
