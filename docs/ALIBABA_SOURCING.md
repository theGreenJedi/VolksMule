# Alibaba sourcing ledger

This is the working Alibaba discovery ledger for **VolksMule Prototype 1**.

It follows the existing project rule:

> **Choose the right kind of thing before choosing the exact thing.**

Alibaba is used here as a **supplier and architecture discovery surface**, not as proof that a component is appropriate, compliant, genuine, automotive-qualified, or production-ready.

The workflow is:

**requirement -> subsystem architecture -> marketplace discovery -> documentation request -> regulatory screen -> interface/serviceability screen -> bench validation -> BUY / DONOR / ADAPT / DESIGN decision**

This file should stay subordinate to:

- [WHAT_THE_CAR_NEEDS.md](WHAT_THE_CAR_NEEDS.md)
- [WHAT_RULES_OUR_SUV_HAS_TO_FOLLOW.md](WHAT_RULES_OUR_SUV_HAS_TO_FOLLOW.md)
- [WHAT_GOES_IN_THE_FIRST_MULE.md](WHAT_GOES_IN_THE_FIRST_MULE.md)
- [ROADMAP.md](ROADMAP.md)

## Status legend

- **GREEN — sourceable family:** Alibaba clearly exposes the kind of component VolksMule wants. Exact part is not yet selected.
- **YELLOW — useful lead:** promising, but integration, documentation, qualification, calibration, or compliance may dominate the decision.
- **RED — do not source as a generic marketplace part:** safety architecture or validation burden makes a random catalog purchase the wrong approach.
- **OPEN — not yet screened deeply enough.**

## Non-negotiable sourcing rules

1. A seller claim such as "DOT approved," "CE," "automotive," "Grade A," or "EV compatible" is **evidence to investigate, not evidence to trust**.
2. For any regulated item of motor-vehicle equipment, require the actual manufacturer identity, applicable standard, certification/marking basis, test report or declaration where appropriate, exact part/model number, and traceability.
3. Prefer the actual manufacturer over a trading company when practical.
4. Ask for engineering drawings, connector pinouts, communications documentation, calibration requirements, environmental ratings, thermal derating data, and replacement availability before designing around a part.
5. Prefer parts whose essential behavior can be diagnosed and serviced locally.
6. No component becomes architecture merely because it is cheap or easy to find.
7. Safety-critical systems must be treated as systems. A physically compatible module is not automatically a functionally compatible module.
8. Marketplace listings are ephemeral. Record manufacturer + model + documentation, not just a URL.
9. Where multiple suppliers sell the same component family, document substitution interfaces so loss of one supplier cannot immobilize the vehicle.

## U.S. regulatory guardrail

NHTSA uses a manufacturer **self-certification** system; it does not pre-approve a seller's vehicle or component. The finished-vehicle manufacturer remains responsible for certifying the completed vehicle to all applicable FMVSS.

NHTSA also identifies specific equipment categories whose import/compliance status matters independently, including brake hoses, brake fluid, glazing, lighting equipment, seat-belt assemblies, tires, and rims.

Useful references:

- NHTSA Importation and Certification FAQ: https://www.nhtsa.gov/importing-vehicle/importation-and-certification-faqs
- NHTSA New Manufacturers Handbook: https://www.nhtsa.gov/sites/nhtsa.gov/files/manufacturer_information_march2014.pdf

Therefore, Alibaba is particularly valuable in two different ways:

- for **unregulated/vehicle-integrated hardware**, as a supplier discovery and technical-comparison surface;
- for **regulated equipment**, as a way to locate manufacturers who may already understand the applicable standard and can supply traceable compliant equipment.

---

# Sweep 1 — high-value Prototype 1 subsystem families

Research date: **2026-08-31**

## 1. Safety cell / body structure — RED for generic sourcing

**Prototype strategy:** DESIGN.

Alibaba may later be useful for steel, stampings, laser-cut parts, fixtures, hinges, latches, seals, and contract fabrication. It should not decide the crash architecture.

**Verdict:** keep the welded safety cell, crash load paths, battery protection, and service architecture under VolksMule design control.

## 2. Front/rear subframes — YELLOW

**Prototype strategy:** ADAPT or DESIGN around proven suspension and drive hardware.

Useful Alibaba roles:

- fabrication suppliers once geometry is defined;
- commodity bushings and mounts;
- reference assemblies showing packaging approaches;
- possible donor cradles if a coherent suspension/e-axle family emerges.

**Do not freeze before suspension corners and e-axles are selected.**

## 3. Suspension corners — GREEN

Alibaba has deep supply for conventional control arms, knuckles, hubs, bearings, coil springs, dampers, bushings, and ball joints.

The important filter is not availability. It is choosing a coherent geometry and then using common service parts with known loads and dimensions.

**Next evidence required:** candidate donor family, hub load rating, bearing size, ball-joint taper, brake mount geometry, wheel bolt pattern, damper travel, spring envelope.

## 4. Steering rack / column / EPS — YELLOW-GREEN

Alibaba exposes C-EPS, P-EPS, dual-pinion EPS, and rack-assist EPS families, including SUV-oriented rack systems.

Discovery references:

- https://autopart.alibaba.com/product/eps-power-steering-gear
- https://autopart.alibaba.com/product/types-of-electric-power-steering

**Important finding:** even Alibaba's own integration material emphasizes that EPS is not plug-and-play. Rack geometry, torque sensing, steering-angle sensing, firmware, CAN messaging, assist calibration, and failure behavior matter.

**VolksMule implication:** prefer a proven rack/column/assist family with a continuous mechanical path. A locally controllable column-assist architecture may deserve special attention because it can reduce dependence on proprietary rack electronics, but the final choice must follow steering loads and packaging.

**Next evidence required:** assist force/torque curve, mechanical ratio, travel, mounting geometry, torque sensor interface, CAN protocol, limp behavior, calibration procedure, temperature derating.

## 5. Friction brakes — GREEN; ABS/ESC controller — YELLOW/RED unless coherent donor system

Commodity calipers, rotors, pads, hoses, master cylinders, and service hardware are abundant.

ABS/ESC hydraulic controllers are also abundant, but listings are overwhelmingly model-specific modules whose calibration assumes particular master-cylinder displacement, caliper piston area, tire behavior, wheel-speed signals, mass distribution, and stability model.

Discovery reference:

- https://www.alibaba.com/countrysearch/CN/abs-control-unit.html

Examples currently surfaced include OE-style VW modules and a JAC ESC hydraulic assembly. These are useful **donor-family references**, not universal ABS boxes.

**VolksMule implication:** keep ordinary hydraulic four-wheel brakes. Treat ABS/ESC/HCU + wheel-speed sensing + steering-angle sensing + calibration as one integrated chassis-control problem.

**Next evidence required:** find an integrator/OEM supplier willing to support a low-volume vehicle with documented calibration access, or select a coherent donor chassis-control family.

## 6. Front/rear e-axles — YELLOW, promising but not yet solved

Alibaba clearly exposes the integrated e-axle ecosystem: motor + reduction gear + differential, sometimes inverter in the same family.

Discovery references:

- https://autopart.alibaba.com/product/electric-vehicle-differential-with-motor
- https://autopart.alibaba.com/product/axle-with-differential

One surfaced family is Brogen high-speed 60/120 kW PMSM e-axle hardware. Current marketplace results skew toward commercial vehicles, trucks, low-speed vehicles, or conversion hardware rather than the compact passenger-SUV unit VolksMule needs.

**Verdict:** ecosystem confirmed; exact candidate still OPEN.

**Search target:** compact 400-V-class passenger/light-MPV units roughly in the 60–150 kW family, with separate front-primary and smaller/low-drag rear possibilities, documented CAN torque command, regen behavior, cooling, resolver/encoder interface, inverter fault behavior, and mechanical drawings.

**Reject:** giant truck axles, low-speed cart axles, undocumented controller bundles, or units that force permanent rear-drive losses without benefit.

## 7. LFP cells/modules — GREEN supply, YELLOW qualification

Alibaba has enormous EVE/CATL-style prismatic LFP supply. This is simultaneously promising and dangerous because reseller listings often mix EV, ESS, RV, and generic claims.

Discovery references:

- EVE LF105 listing: https://www.alibaba.com/product-introduction/Eve-Lf105-Lithium-Batteries-with-MSDS_1601322543470.html
- EVE LF280K listing: https://www.alibaba.com/product-introduction/EVE-280Ah-Lifepo4-Battery-Cell-LF280k_1601004778668.html

**Important finding:** one current LF280K marketplace page describes a 280 Ah cell as "280 kWh" in marketing copy. That arithmetic error is exactly why marketplace text must never be our engineering source of truth.

**VolksMule rule:** use Alibaba to identify supply channels; use the original cell manufacturer's datasheet, QR/serial traceability, batch data, test reports, and sample testing to qualify cells.

**Next evidence required:** genuine manufacturer datasheets; cell mass/dimensions; continuous and peak current; DCIR; cycle life test conditions; low-temperature charge limits; compression requirement; vent behavior; thermal propagation data; lot traceability; UN 38.3 shipping documentation.

Large 280 Ah ESS-oriented cells may be physically awkward for a compact vehicle. Smaller automotive-oriented prismatic cells/modules deserve a dedicated search before capacity is frozen.

## 8. Battery enclosure / vehicle integration — RED for generic sourcing

**Prototype strategy:** DESIGN.

Alibaba is useful for cooling plates, extrusions, seals, vents, contactors, disconnects, HV connectors, busbars, and fabrication. It should not dictate enclosure geometry or crash integration.

## 9. BMS — YELLOW

High-voltage master/slave BMS families are easy to find, including 96S, 128S and larger CAN-connected units.

Discovery references:

- https://www.alibaba.com/catalog/battery-management-systems-bms-_cid201765701
- example high-voltage listing: https://www.alibaba.com/pla/EC-Smart-BMS-High-Voltage-BMS_1601723849199.html

Current surfaced products are heavily ESS-oriented. Voltage/channel count alone does not make them vehicle-suitable.

**Vehicle BMS evidence required:** automotive environmental qualification, cell-voltage accuracy over temperature, pack-current sensing, isolation monitoring integration, contactor/precharge control, crash input/shutdown, HVIL, redundant fault handling where needed, CAN documentation, service tooling, logging, balancing limits, watchdog/fail-safe behavior, and offline firmware recovery.

**Verdict:** do not select an ESS BMS merely because it says 400 V and CAN.

## 10. OBC + HV-to-12V DC/DC + PDU — GREEN and high-priority

This is one of the strongest Alibaba sourcing areas found so far.

Supplier/family leads:

### Dilong

Alibaba currently surfaces a **400-V-class 6.6 kW OBC + 14 V / 1.5 kW DC/DC + PDU** integrated family, with MOQ 1 listings in some variants.

Discovery references:

- https://www.alibaba.com/countrysearch/CN/400v-ev-charger.html
- https://chinese.alibaba.com/g/400v-output-dc-converter.html

### Shenzhen Ovar New Energy Technology

Alibaba supplier listings show **6.6 kW OBC + 1.5 kW DC/DC** integrated products for approximately **200–420 V** EV systems with CAN communication.

Discovery references:

- https://www.alibaba.com/board-battery-charger-suppliers.html
- https://www.alibaba.com/ev-charger-control-board-suppliers.html

### Hunan CTS Technology

Alibaba surfaces 300/400/500/600/800-V OBC families and OBC+DCDC offerings.

Discovery reference:

- https://www.alibaba.com/countrysearch/CN/400v-ev-charger.html

**VolksMule implication:** a 2-in-1 or 3-in-1 module could eliminate substantial custom HV power electronics while preserving a conventional 12-V ecosystem.

**Required before shortlist:** complete electrical datasheet; supported pack-voltage window; AC input requirements; J3400 control compatibility or exposed pilot/control interface; galvanic isolation; CAN DBC/protocol; HVIL; IP rating; coolant specifications; continuous output at high ambient temperature; EMC test data; automotive qualification; fault-state behavior; service/reflash procedure; dimensional CAD; connector source; sample pricing and production continuity.

**Priority:** HIGH.

## 11. SAE J3400 / NACS vehicle inlet — OPEN-YELLOW

Alibaba clearly has a rapidly expanding NACS/J3400 ecosystem, but the first search returned many **adapters, EVSE cables, and station-side plugs** rather than a well-documented native **vehicle inlet** suitable for VolksMule.

Discovery references:

- https://autopart.alibaba.com/product/tesla-inlet-socket
- https://autopart.alibaba.com/product/electric-car-charging-cables

**Do not accidentally design around an adapter product.**

**Search target:** native vehicle-side SAE J3400 inlet supporting AC + DC, temperature sensing, locking/release strategy, HVIL as appropriate, high-voltage cable termination, environmental sealing, and published dimensional/CAD data.

**Priority:** HIGH because inlet geometry affects body and charging packaging.

## 12. EV HVAC / heat pump / PTC backup — GREEN-YELLOW

Alibaba has broad supply of electric scroll compressors for EVs, including high-voltage units, R1234yf-oriented products, and CAN-controlled compressors.

Discovery reference:

- https://autopart.alibaba.com/product/ac-for-electric-cars

A currently surfaced example is a CAN-controlled compressor listed for a BYD Seal around the 409-V class. That demonstrates the hardware family exists, but an OE replacement compressor with undocumented proprietary CAN is not automatically a good VolksMule part.

**Search target:** supplier-supported 300–450 V variable-speed compressor with documented command interface, R1234yf support, engineering map, oil requirement, isolation requirements, mounting CAD, noise/vibration data, and replacement availability.

Also source:

- PTC backup heater;
- cabin evaporator/heater core/blower;
- coolant pumps and valves;
- battery chiller/plate interfaces;
- conventional service ports and refrigerant plumbing.

**Rule:** avoid an inseparable proprietary thermal "octopus" unless whole-vehicle benefit is compelling.

## 13. Seats / belts / airbags / restraint controller — RED for generic marketplace assembly

Alibaba can help identify manufacturers and commodity seat structures, but restraint hardware is not a mix-and-match catalog exercise.

**VolksMule strategy:** BUY/DONOR a proven, traceable restraint family and integrate the seat, belt, pretensioner, airbag, occupancy logic, sensors, controller, and crash structure as one system.

FMVSS 209 seat-belt equipment itself is among the equipment categories NHTSA identifies as independently regulated.

**Reject:** unknown inflators, cloned airbags, seller-only "compatible" claims, or connectors-as-proof-of-fit.

## 14. Glass / lights / mirrors / wipers — GREEN with regulatory/documentation split

Marketplace depth is excellent.

- **Glazing:** source from a manufacturer capable of supplying traceable compliant glazing; body should adapt to practical glass where possible.
- **Lighting:** standardized replaceable modules are desirable, but require actual FMVSS 108 compliance basis/marking rather than styling claims.
- **Mirrors/camera:** commodity supply is broad; final rear-visibility architecture follows the rules map.
- **Wipers/washer hardware:** strongly suitable for commodity sourcing.

NHTSA identifies glazing and lighting equipment among independently regulated equipment categories.

## 15. Wheels / tires / hubs / roadside hardware — GREEN, but prefer North American service ubiquity

Alibaba can source wheels, hubs and hardware, but VolksMule's priority is a common North American bolt pattern, common load-rated tire size, real sidewall, and a replacement ecosystem available from ordinary tire/parts stores.

**Marketplace price is secondary to roadside replaceability.**

## 16. TPMS / rear camera / pedestrian sound / basic sensors — GREEN-YELLOW

Commodity hardware is easy to locate. Integration and regulatory performance still need to be demonstrated at vehicle level.

Prefer sensors with documented electrical interfaces rather than cloud/app dependencies.

## 17. Vehicle controls / switches / contactors / connectors / relays — GREEN

This is exactly where the commodity-sourcing philosophy should work well.

Search for:

- sealed automotive switches;
- conventional stalks and tactile controls;
- automotive relays/fuse blocks;
- HV contactors and precharge hardware;
- service disconnects;
- HVIL connectors;
- sealed LV connectors;
- TXL/GXL/SXL automotive wire and traceable HV cable;
- coolant pumps, valves and sensors.

Prefer components with multiple manufacturers and published mating-interface information.

---

# Current priority queue

The next Alibaba sweeps should happen in this order because these components most strongly constrain packaging and system architecture:

1. **Compact passenger-vehicle 400-V e-axle families** — front primary and rear assist possibilities.
2. **400-V OBC/DC-DC/PDU** — obtain real datasheets and CAN/interface documentation from Dilong/Ovar/CTS-class suppliers.
3. **Native SAE J3400 vehicle inlet** — not an adapter or EVSE plug.
4. **Automotive-capable HV BMS** — distinguish real vehicle products from ESS products.
5. **EPS family** — determine whether supported column-assist or rack-assist gives better owner-control/serviceability tradeoff.
6. **HVAC compressor + heat pump components + PTC** — document protocol and thermal maps.
7. **Suspension/brake donor family** — coherent corners first, individual commodity service parts second.
8. **ABS/ESC integration route** — identify a supportable donor/integrator path rather than a random HCU.
9. **Regulated commodity suppliers** — glazing, lamps, belts, brake hoses, tires/rims with actual certification evidence.
10. **Low-risk commodity hardware** — switches, pumps, relays, connectors, wipers, washer system, mirrors, jack/recovery hardware.

# Supplier-question template

For any candidate that survives first screening, ask the supplier for:

1. Are you the **original manufacturer** of this exact model? If not, who is?
2. Exact manufacturer name and model/part number.
3. Full engineering datasheet and dimensional drawing/CAD.
4. Intended vehicle/application class and continuous duty rating.
5. Environmental ratings and test standards.
6. Applicable automotive quality certification (for example IATF 16949) and which factory/site it covers.
7. EMC/EMI and electrical-transient qualification data where relevant.
8. Functional-safety process/evidence where relevant.
9. CAN/CAN-FD protocol or DBC, diagnostic protocol, bootloader/update procedure, and fault table for electronic modules.
10. Connector manufacturer/part numbers and mating connectors.
11. Cooling requirements and thermal-derating curves.
12. Failure/degraded behavior and safe-state definition.
13. Applicable FMVSS/SAE/UL/UN/ECE or other certifications/tests, with copies of evidence — not just a logo in the listing.
14. MOQ for samples, prototype quantities, and production quantities.
15. Production lead time and expected support/availability horizon.
16. Whether firmware/custom calibration can be supplied without cloud/vendor account dependency.
17. Whether replacement units can be installed and commissioned with documented local tools.

# Working conclusion after Sweep 1

Alibaba appears capable of supplying a **large fraction of VolksMule's solved hardware**, especially EV power electronics, thermal hardware, electrical distribution, conventional mechanical service parts, and potentially e-axles.

The marketplace is much less trustworthy as a direct selection mechanism for integrated safety systems, cell qualification, or anything whose software/calibration is inseparable from a donor vehicle.

That is a useful result: **we do not need Alibaba to design the car. We need it to expose the industrial ecosystem of already-solved pieces so VolksMule can orchestrate them deliberately.**
