# Alibaba J3400 vehicle-side charging screen

This document takes the Volkswagen Mule Alibaba sourcing mission into the **vehicle-side SAE J3400 charging stack**.

It is intentionally more than a search for a NACS-shaped socket.

> **A J3400 inlet is the mouth of the charging system. It is not the charging system.**

Prototype 1 needs an architecture that can accept ordinary AC charging and standards-based DC fast charging while remaining diagnosable, serviceable, and independent of any manufacturer cloud account.

This screen is subordinate to:

- [WHAT_THE_CAR_NEEDS.md](WHAT_THE_CAR_NEEDS.md)
- [WHAT_GOES_IN_THE_FIRST_MULE.md](WHAT_GOES_IN_THE_FIRST_MULE.md)
- [ALIBABA_SOURCING.md](ALIBABA_SOURCING.md)
- [ALIBABA_OBC_POWER_ELECTRONICS.md](ALIBABA_OBC_POWER_ELECTRONICS.md)

No candidate in this document is production-approved.

---

# 1. Executive result

Alibaba is useful for J3400 discovery, but the useful pieces split into two very different quality bands.

## Strong lead

**Vehicle charging communications:** Shanghai MIDA exposes an EVCC family through Alibaba and its own engineering site that is the correct *kind* of controller for Prototype 1. It supports:

- NACS;
- HomePlug Green PHY power-line communication;
- DIN SPEC 70121;
- ISO 15118-2;
- supplier-claimed ISO 15118-20 support;
- CAN 2.0B / J1939;
- UDS;
- control-pilot wake-up;
- AC and DC charging communication;
- supplier-claimed bidirectional-power-transfer communication support.

That makes it a **serious Prototype 1 integration candidate**, subject to documentation and bench validation.

## Weak lead

**Vehicle inlet hardware:** Alibaba has many NACS/Tesla sockets, but current listings do not yet give enough evidence that the exact vehicle-side parts meet the current SAE J3400/J3400-2 requirements for the full AC + DC use case.

Several inexpensive listings are plainly AC-oriented 50 A or 80 A sockets. A NACS geometry does not magically make an AC-rated inlet suitable for hundreds of amperes of DC fast charging.

Therefore:

> **Do not freeze body packaging around an Alibaba NACS inlet until the exact inlet has current-standard drawings, current ratings, thermal sensing, lock/actuator behavior, environmental qualification, and traceable compliance evidence.**

---

# 2. Standards baseline

As screened on 2026-08-31:

## SAE J3400

The current SAE J3400 family defines the North American Charging System vehicle/EVSE interface for conductive AC or DC power transfer.

Relevant official SAE publications include:

- **SAE J3400_202409**, revised 2024-09-30 — general physical, electrical, functional, safety, and performance requirements for the J3400 conductive interface.
- **SAE J3400/2_202505**, revised 2025-05-27 — dimensional definition of the J3400 connector and vehicle inlet.
- **SAE J3400/1_202504** — adapter safety and OEM-qualified-device designation.

Sources:

- https://saemobilus.sae.org/standards/j3400_202409-north-american-charging-system-nacs-electric-vehicles
- https://saemobilus.sae.org/standards/j34002_202505-connectors-inlets-north-american-charging-system-nacs-electric-vehicles
- https://saemobilus.sae.org/standards/j34001_202504-electric-vehicle-charging-adapter-safety-oem-qualified-device-designation

The project shall check for revisions again before design freeze or compliance testing.

---

# 3. The communication fact that changes the sourcing problem

J3400 DC fast charging is not a generic CAN conversation between the car and charger.

CharIN states that SAE J3400 and CCS share high-level charging communication based on **DIN SPEC 70121 and ISO 15118 over power-line communication (PLC)**.

CharIN also explicitly warns that a vehicle which only speaks CAN for charging cannot communicate with a PLC/ISO-15118 EVSE merely by adding a physical adapter.

Sources:

- https://www.charin.global/technology/north-america-charging-interoperability-naci-task-force
- https://www.charin.global/faq-section/

This creates a hard VolksMule requirement:

> **The vehicle-side charge controller must implement the required PLC charging communication; CAN is the internal vehicle-side interface to the BMS/VCU, not a substitute for EV-to-EVSE PLC.**

---

# 4. Working Prototype 1 J3400 architecture

The current functional chain should be treated as:

```text
J3400 vehicle inlet
        |
        |-- power contacts -----------------------------+
        |                                               |
        |       AC charge                               | DC fast charge
        |                                               |
        +--> OBC --------------------------------> HV bus/pack
        |                                               ^
        +----------------------------------------------> |
                                                        |
Control pilot / proximity / temp / lock                 |
        |                                               |
        v                                               |
EVCC / PLC charge communication controller              |
        |                                               |
        | CAN / diagnostics                             |
        v                                               |
VCU <----> BMS ----> charge contactors / PDU / HVIL ----+
```

This is deliberately conceptual. Exact switching topology, isolation strategy, inlet pin treatment, contactors, fusing, precharge, and charge-control state machine remain engineering work.

The important architectural separation is already useful:

- **the inlet provides the physical conductive interface**;
- **the EVCC speaks to the EVSE**;
- **the BMS defines what the battery may safely accept**;
- **the VCU coordinates vehicle state**;
- **the OBC converts AC charging power**;
- **DC fast charging bypasses the OBC power-conversion path and reaches the HV battery bus through controlled DC-charge switching/protection**;
- **the PDU/HV system provides contactors, fusing, HVIL and safe isolation as the final topology requires**.

No single marketplace box gets to quietly absorb all of those responsibilities without documentation.

---

# 5. Candidate A — MIDA EVCC

## Supplier

Shanghai MIDA EV Power / MIDA Group

Alibaba discovery listing:

- MIDA EVCC controller, ISO 15118 vehicle communication, approximately USD 650–750 in the listing screened during this mission.

Supplier engineering page:

- https://www.midapower.com/evcc-module-ccs-v2g-nacs-protocols-plc-to-can-ev-car-charger-controller-product/

Alibaba discovery page:

- https://autopart.alibaba.com/product/ev-charging-controller

## Published/claimed features

The supplier publishes or claims:

- NACS support;
- HomePlug Green PHY 1.1;
- DIN SPEC 70121;
- ISO 15118-2 AC/DC EIM / Plug & Charge;
- ISO 15118-20 AC/DC EIM / Plug & Charge;
- PLC-to-CAN gateway behavior;
- CAN 2.0B;
- J1939;
- UDS;
- CP wake-up;
- approximately 9–28 V supply range;
- approximately -40 C to +85 C environment on the detailed product description;
- IP67 on the supplier product page;
- inlet-lock control capability in some supplier descriptions;
- configurable interfaces for selected BMS/current sensors;
- bidirectional-power-transfer communication support.

## Why it is interesting

This is fundamentally different from the generic Alibaba `EV charging controller` problem.

The product is aimed at the **vehicle-side high-level charging communication problem**, which is exactly the missing function between our J3400 inlet and our internal BMS/VCU CAN network.

It also fits the 12-V Prototype 1 service ecosystem electrically.

## Why it is not selected

There are unresolved issues:

1. Alibaba and supplier pages expose different version identifiers (for example V3.4 versus a V4.1 marketplace listing). Exact hardware/firmware identity must be frozen.
2. CE/RoHS is not automotive functional-safety evidence.
3. We need the actual CAN object dictionary / DBC or equivalent API documentation.
4. We need exact ISO-15118 feature/version behavior, including what is truly implemented versus merely advertised.
5. We need security/key/certificate provisioning and recovery behavior.
6. We need inlet-lock state-machine details.
7. We need full diagnostic and offline firmware/update procedures.
8. We need failure-state behavior when communication dies mid-charge.
9. We need environmental/EMC qualification evidence appropriate to a road vehicle.
10. We need actual interoperability test evidence against North American EVSEs.

## Current verdict

**YELLOW-GREEN — strongest Alibaba-accessible EVCC lead so far.**

Good enough to request engineering documents and potentially bench-test.

Not good enough to call road-ready.

---

# 6. Physical inlet candidates exposed by Alibaba

Alibaba's NACS/Tesla inlet discovery page currently surfaces multiple suppliers, including:

- Suzhou Junchi Electronic Technology Co., Ltd.;
- Jiangsu Zilong New Energy Technology Co., Ltd.;
- Shenzhen Mandzer New Energy Technology Co., Ltd.

Discovery page:

- https://autopart.alibaba.com/product/tesla-inlet-socket

The marketplace evidence is useful because it proves that the physical NACS/J3400 ecosystem is becoming a multi-supplier commodity ecosystem.

It does **not** yet prove that any exact inlet is acceptable for VolksMule.

---

# 7. Suzhou Junchi — investigate, do not package around it yet

Alibaba currently surfaces a `NACS High Voltage EV Charging Socket` from Suzhou Junchi around the marketplace's higher-current end.

Alibaba's supplier summary associates Junchi's NACS products with approximately:

- up to 1000 V class;
- roughly 80–350 A product families;
- IP67 claims.

That makes Junchi worth an RFQ.

Missing before candidate status can advance:

- exact J3400/J3400-2 revision claim;
- exact continuous and temporary DC-current rating;
- conductor cross-section;
- contact temperature-sensor type and placement;
- temperature/current derating curve;
- locking actuator and feedback details;
- HVIL behavior if applicable;
- IP rating test basis;
- insertion-cycle durability;
- creepage/clearance evidence;
- exact 3D CAD;
- North American certification/test evidence;
- automotive quality-system evidence;
- traceable part number and revision control.

## Current verdict

**YELLOW — supplier lead only.**

---

# 8. Jiangsu Zilong / HPConnect — supplier quality is interesting; current NACS listing is not our DC inlet

Alibaba currently surfaces a Zilong NACS vehicle socket around **50 A AC**.

That is useful for showing the ecosystem, but it is not evidence of a full-power J3400 AC/DC inlet.

Zilong itself is more interesting than that particular listing. Its own site says the company manufactures:

- charging guns and sockets;
- high-voltage vehicle wiring harnesses;
- PDU-related products;
- AC and DC charging components;
- liquid-cooled charging components.

The company also publishes historical claims of automotive customer projects involving Chery/JAC, WM Motor, and SAIC and quality/certification work on several charging standards.

Sources:

- https://www.hpconnect.cn/aboutus.html
- https://www.hpconnect.cn/

That means Zilong is worth asking a different question:

> **Do you manufacture a current SAE J3400/J3400-2 AC+DC vehicle inlet suitable for a 400-V passenger EV, even if that exact product is not the Alibaba listing we found?**

## Current verdict

**YELLOW — promising manufacturer, wrong exact marketplace product so far.**

---

# 9. Shenzhen Mandzer — useful ecosystem supplier, current listing is AC-oriented

Mandzer's current Alibaba NACS inlet listing exposes AC-current variants such as 16/32/48/80 A.

Its own site shows that the company manufactures EV adapters, charging cables, connectors, sockets, portable chargers, and other charging equipment and publishes CE/RoHS/FCC/UL-related certificate claims across its product portfolio.

Sources:

- https://www.mandzer.com/about-us.html
- https://www.mandzer.com/products.html

The present evidence does not justify treating the listed inlet as VolksMule's DC fast-charge inlet.

## Current verdict

**YELLOW-RED for the exact listing; YELLOW as a supplier lead.**

---

# 10. Benchmark — Phoenix Contact CHARX J3400 vehicle inlet

Alibaba pricing is not the engineering benchmark.

Phoenix Contact's current NACS/J3400 vehicle-inlet page gives us a much better specification target.

Its CHARX connect universal J3400 vehicle-inlet family is published with features including:

- J3400 geometry/compliance target;
- up to 1000 V DC;
- 300/350 A permanent DC current variants;
- 600/800 A boost-mode variants;
- 48/80 A AC variants;
- 12-V actuator;
- Pt1000 temperature sensing;
- IP6K9K / IP6K6K / IP67 / IP6K5 family ratings;
- IATF 16949 manufacturing context;
- 70/95 mm2 DC conductor variants.

Phoenix announced the high-power NACS vehicle inlet for Q3 2026. Exact part-level UL 2251 status must be verified because the current page describes certification status differently across the overall product family and the new vehicle-inlet section.

Source:

- https://www.phoenixcontact.com/en-us/industries/e-mobility/charging-infrastructure/nacs-connectors-and-charging-inlets

## Why this matters

This gives Alibaba candidates a concrete hurdle.

A USD 40 socket is not a bargain if we later discover that it lacks:

- enough copper;
- contact temperature sensing;
- a validated lock;
- road-environment sealing;
- dimensional conformance;
- lifecycle durability;
- current derating data;
- certification evidence.

## Current verdict

**GREEN benchmark / supplier candidate outside Alibaba.**

It does not violate the Alibaba mission to use a non-Alibaba reference as the quality bar. Alibaba is the discovery surface, not a religion.

---

# 11. Supercharger access is not the same thing as J3400 compliance

This distinction is important enough to make durable.

Tesla's current support documentation says access to NACS Superchargers is being enabled by **vehicle manufacturer**, with supported automakers specifically enumerated.

Therefore:

> **VolksMule shall not assume that installing a J3400 inlet and implementing ISO 15118 automatically grants access to every Tesla Supercharger.**

Source:

- https://www.tesla.com/support/charging/supercharging-other-evs

This creates a project principle:

> **Standards-based J3400 interoperability is a requirement. Tesla-network authorization is an external ecosystem capability and must not become a dependency for ordinary charging.**

Prototype 1 should be able to charge from standards-compliant non-Tesla J3400 infrastructure even if Tesla never recognizes VolksMule as an automaker.

---

# 12. Plug & Charge / PKI is a separate layer

ISO 15118 Plug & Charge involves certificate/public-key infrastructure in addition to physical and protocol compatibility.

CharIN's North America Charging Interoperability work explicitly treats communication/security and multi-PKI interoperability as separate active workstreams.

Source:

- https://www.charin.global/technology/north-america-charging-interoperability-naci-task-force

Prototype 1 therefore needs a deliberate answer for:

- EIM/manual authorization;
- Plug & Charge certificate provisioning;
- certificate replacement/recovery;
- owner-accessible diagnostics;
- offline fallback behavior where standards permit;
- security without permanent OEM cloud dependence.

We should not let a vendor's hidden certificate service become the ignition key for the charging system.

---

# 13. Bidirectional/V2H implication

The MIDA EVCC's advertised ISO 15118-20 and bidirectional-power-transfer support is architecturally interesting.

It does **not** mean Prototype 1 automatically gets V2H.

Bidirectional operation also requires compatible:

- vehicle-side power electronics/topology;
- switching and protection;
- EVSE/grid interface;
- standards implementation;
- safety behavior;
- regulatory/utility treatment.

VolksMule should preserve the communication and hardware path where practical, but V2H remains **future capability rather than a Prototype 1 blocker**.

---

# 14. J3400 subsystem requirements created by this screen

The sourcing mission has now created the following durable requirements.

## Inlet

The exact vehicle inlet must provide or document:

- current SAE J3400/J3400-2 conformance basis;
- AC and DC ratings appropriate to the vehicle;
- temperature sensing at the power contacts;
- current derating behavior versus temperature;
- mechanical lock/actuator;
- lock-position feedback;
- CP/PP interface details;
- sealing/environmental ratings;
- mating-cycle durability;
- cable/conductor sizes;
- touch-safe behavior;
- service replacement procedure;
- CAD and mounting datum;
- traceable revision/part number.

## EVCC

The vehicle charge communication controller must provide or document:

- HomePlug Green PHY/PLC implementation;
- DIN SPEC 70121 behavior where required;
- ISO 15118 version/features;
- AC and DC charging state machines;
- EIM authorization;
- Plug & Charge capability if used;
- certificate provisioning and recovery;
- internal CAN interface documentation;
- diagnostic protocol and DTCs;
- CP/proximity behavior;
- inlet-lock control/feedback behavior;
- safe shutdown behavior on communication failure;
- offline firmware/update/recovery path;
- interoperability-test evidence.

## BMS/VCU interface

The EVCC must not independently invent battery limits.

The vehicle architecture shall have a documented interface for at least:

- pack maximum allowable charge voltage;
- maximum allowable charge current;
- present pack voltage/current;
- SOC;
- thermal limits;
- insulation/fault state;
- contactor state;
- permission to charge;
- requested controlled shutdown;
- emergency fault shutdown.

---

# 15. RFQ — vehicle inlet

Ask Junchi, Zilong, Mandzer, MIDA, and any new candidate:

1. Exact manufacturer and part number?
2. Is this exact part a vehicle inlet rather than an EVSE connector?
3. Which exact revision of SAE J3400 / J3400-2 is it designed/tested against?
4. Continuous AC current at 120/240/277 V?
5. Continuous DC current at 400 V and 1000 V?
6. Temporary/boost DC current and allowable duration?
7. Contact-temperature sensors: type, count, position, tolerance?
8. Temperature derating curve?
9. Main conductor material and cross-section?
10. Lock actuator voltage and pinout?
11. Lock/unlock feedback method?
12. Manual emergency-release provision?
13. CP and PP pin/interface drawing?
14. HVIL provision, if any?
15. IP ratings and underlying test standard?
16. Operating/storage temperature?
17. Mechanical mating-cycle validation?
18. Vibration/shock validation?
19. Flammability/material certifications?
20. UL 2251 or other applicable NRTL certification status for the exact inlet?
21. IATF 16949 manufacturing site/certificate?
22. Dimensional inspection report against J3400/2?
23. 2D drawing and STEP model?
24. MOQ and prototype quantity price?
25. Production lead time and second-source status for seals/contacts/actuator?

---

# 16. RFQ — EVCC

Ask MIDA and competing EVCC suppliers:

1. Exact hardware and firmware version currently shipping?
2. Which DIN SPEC 70121 version is implemented?
3. Which ISO 15118 versions and feature sets are implemented?
4. Is ISO 15118-20 production-ready or beta/custom firmware?
5. HomePlug Green PHY chipset and implementation?
6. SLAC behavior/interoperability test report?
7. EIM supported?
8. Plug & Charge supported?
9. TLS stack and certificate storage method?
10. Certificate provisioning/replacement/recovery method?
11. Does ordinary EIM charging require any supplier cloud service?
12. Complete vehicle-side CAN protocol/DBC available?
13. UDS services/DTC list available?
14. BMS limit/request signal definition?
15. VCU state signal definition?
16. Control-pilot/proximity circuitry included or external?
17. Inlet-lock driver output and feedback inputs?
18. 12-V operation and cranking/brownout behavior?
19. Sleep current and wake conditions?
20. IP/environmental rating evidence?
21. EMC test reports?
22. Automotive qualification / IATF manufacturing evidence?
23. Functional-safety development evidence?
24. Safe-state behavior if CAN, PLC, CP, lock feedback, or BMS communication fails?
25. Offline firmware update/recovery procedure?
26. Can the owner/operator replace the unit without supplier account authorization?
27. Has the exact firmware been interoperability-tested against North American J3400 EVSEs?
28. Has it been tested on Tesla, ChargePoint, EVgo, Electrify America, or other networks using standards-based sessions? Provide logs/test reports if available.
29. Price at 1 / 10 / 100 / 1000 units?
30. Long-term availability commitment?

---

# 17. Current candidate ranking

| Candidate | Role | Current status | Why |
|---|---|---|---|
| MIDA EVCC | Vehicle-side PLC charge controller | **YELLOW-GREEN** | Correct architecture and protocol family; documentation/qualification still required |
| Phoenix Contact CHARX J3400 inlet | Benchmark / possible inlet source | **GREEN benchmark** | Strong published vehicle-inlet engineering specification; exact part availability/certification to verify |
| Suzhou Junchi NACS inlet family | Alibaba inlet lead | **YELLOW** | Higher-current marketplace family exists; exact compliance/evidence missing |
| Jiangsu Zilong / HPConnect | Alibaba manufacturer lead | **YELLOW** | Serious charging-component manufacturer; current NACS listing found is AC-oriented, so ask for current AC+DC J3400 part |
| Shenzhen Mandzer | Alibaba manufacturer lead | **YELLOW-RED exact listing / YELLOW supplier** | Current inlet variants are AC-oriented; broader supplier capability may still be useful |

---

# 18. Current Prototype 1 direction

Do **not** choose an exact inlet yet.

Do **not** choose an exact EVCC yet.

But the architecture is now sufficiently concrete to carry forward:

1. **Native SAE J3400 vehicle inlet** with real AC + DC capability.
2. **Dedicated vehicle-side PLC EVCC** implementing standards-based DIN/ISO charging communication.
3. **Internal documented CAN interface** between EVCC, VCU, and BMS.
4. **OBC handles AC conversion.**
5. **Controlled DC path bypasses OBC conversion for DC fast charging.**
6. **Pack/BMS remains sovereign over allowable battery voltage/current and fault state.**
7. **Physical emergency charge release exists.**
8. **Ordinary charging does not require a phone or cloud account.**
9. **Tesla Supercharger access is desirable but not assumed or architecturally required.**
10. **V2H/bidirectional capability stays architecturally possible without blocking Prototype 1.**

---

# 19. Mission conclusion

Alibaba has given VolksMule something more important than a cheap plug.

It has exposed a plausible path to a **standards-native, supplier-independent J3400 charging architecture**.

The strongest immediate sourcing action is now:

- obtain the MIDA EVCC engineering package;
- RFQ Junchi/Zilong/Mandzer for their *actual current J3400 AC+DC vehicle inlet*, not generic Tesla sockets;
- obtain a Phoenix Contact J3400 inlet drawing/quote as the benchmark;
- build a bench charge-communications rig before any body tooling is frozen around a port.

The next companion screen is the **400-V automotive BMS**, because the EVCC can only request sensible charging behavior if the BMS provides trustworthy pack limits and fault state.
