# Revision-A MIDA EVCC integration envelope

This file turns the current public data for the **MIDA / RNL GQEVPLC-V3.4 Electric Vehicle Communication Controller (EVCC)** into a disciplined Prototype 1 packaging and electrical input.

It is not final J3400 approval. It is an integration envelope for the communication controller that may bridge VolksMule's BMS/VCU to charging infrastructure using PLC-based DIN 70121 / ISO 15118 communication.

> **The EVCC enables charging communication. It does not own the battery, the charge contactors, the vehicle, or the driver's access to the car.**

---

## 1. Why this part remains interesting

Current MIDA material advertises:

- HomePlug Green PHY 1.1;
- SLAC;
- DIN SPEC 70121;
- ISO 15118-2 AC/DC;
- ISO 15118-20 AC/DC, including EIM/PnC claims;
- CAN 2.0B;
- J1939;
- UDS;
- CP wake-up;
- CCS1/CCS2 support;
- NACS/J3400-oriented product marketing;
- bidirectional communication support claims.

That is the correct **kind** of controller for the vehicle-side charging-communications role.

---

## 2. The apparent 24-V problem is substantially resolved

Earlier public wording described this controller as a "standard ECU for 24V environments."

MIDA's current product data for **GQEVPLC-V3.4** now gives:

- **rated/input voltage: 9–28 VDC**;
- active consumption: published as less than 130 mA on current MIDA pages;
- CP wake-up;
- IP67 claim.

### Revision-A conclusion

The controller does **not** currently appear to require a dedicated 24-V low-voltage architecture.

It should be electrically compatible with VolksMule's conventional 12-V system, subject to the supplier's exact transient/load-dump/reverse-polarity specification.

Therefore:

> **Do not add a 12→24-V converter unless the exact production revision proves it necessary.**

Still required:

- permitted steady-state operating voltage range;
- cold-crank / brownout behavior;
- load-dump immunity;
- reverse-polarity behavior;
- sleep current;
- wake-state timing;
- 12-V transient qualification evidence.

---

## 3. Provisional physical envelope

A current third-party listing for the same GQEVPLC-V3.4 family publishes:

| Item | Provisional public value |
|---|---:|
| Housing | **156.4 × 101 × 25 mm** |
| Mass | **~315 g** |
| Operating temperature | **-40 to +85 °C** |
| Nominal supply examples | 12 V / 24 V |
| Input range | 9–28 VDC |
| Protection | IP67 claim |

These values are useful enough to reserve a Revision-A box.

They are **not bracket-release dimensions** until MIDA supplies its own dimensioned drawing/STEP file for the quoted revision.

### Provisional CAD box

Reserve approximately:

- 170 × 115 × 40 mm gross controller/service zone;
- connector mating and harness bend space on the connector side;
- local service access without windshield/cowl removal;
- short CP/PLC-related routing to the charge inlet where EMC practice supports it;
- isolated location from HV heat sources and direct wheel splash even if IP67 is retained.

The extra margin above the published housing is packaging allowance, not a claim about the component itself.

---

## 4. Vehicle interfaces to request

### Low voltage

Need exact pinout for:

- B+ / ignition / wake;
- ground architecture;
- CP input/wake;
- electronic-lock outputs/inputs if used;
- CAN H/L;
- diagnostic/RS232 service port;
- any discrete charge-enable / fault outputs;
- shielding/drain requirements.

### CAN / internal vehicle interface

VolksMule needs a documented message contract covering at least:

- requested charging voltage/current;
- BMS actual voltage/current limits;
- battery SOC and temperature state needed by the charger;
- contactor/precharge state;
- isolation/HVIL permission state;
- charge-port lock state;
- plug state;
- station/EVSE status;
- fault state;
- session stop reasons;
- DC charge enable/disable sequence;
- AC charge state interactions;
- diagnostic messages / DTCs.

A private CAN protocol that only a MIDA engineer can interpret is not sufficient.

---

## 5. J3400-specific questions

MIDA broadly markets NACS support, but VolksMule needs exact evidence for the intended North American J3400 implementation.

Ask:

1. Which exact hardware/software revision supports SAE J3400 vehicle-side use?
2. Is the same GQEVPLC-V3.4 hardware used, or is another revision required?
3. Which J3400 / J1772 control-pilot/proximity requirements are implemented by EVCC versus inlet-side/discrete vehicle hardware?
4. Which ISO 15118-20 profiles are supported on the exact revision?
5. Is TLS / Plug & Charge supported and configurable offline?
6. Can certificate provisioning be performed without a MIDA cloud account?
7. Is standards-based DC fast charging possible without OEM/network whitelisting?
8. What interoperability testing has been completed with North American J3400/NACS EVSE?
9. Does the controller support charge-port lock control suitable for the chosen J3400 inlet?
10. What physical-layer/PLC coupling requirements must be observed between EVCC and inlet?

> **"NACS supported" in a product page is a lead, not final J3400 validation.**

---

## 6. Software sovereignty gates

The controller remains viable only if VolksMule can service it locally.

Required:

- local configuration tool;
- offline firmware update/recovery;
- firmware version identification;
- bootloader recovery procedure;
- CAN/DBC or equivalent interface document;
- UDS service list;
- DTC list;
- configuration backup/restore;
- replacement-unit commissioning procedure;
- no mandatory cloud authentication for ordinary replacement or recovery.

Remote-update capability is acceptable as an option. Remote-only update is not.

---

## 7. Functional ownership boundary

### EVCC may own

- PLC protocol stack;
- SLAC;
- DIN/ISO high-level charging communication;
- station-session state translation;
- charge-port communication details specifically delegated to it;
- diagnostic reporting for its own functions.

### EVCC does not own

- pack cell protection;
- final charge-current permission;
- contactor safety logic;
- isolation-monitor permission;
- HVIL safety state;
- crash shutdown;
- overall VCU authority;
- vehicle start/access;
- owner service rights.

The BMS/VCU and HV safety system remain authoritative over whether energy may enter or leave the pack.

---

## 8. Failure behavior to verify

Bench test must include:

- EVCC unplugged;
- CAN lost;
- PLC negotiation failure;
- CP lost during charge;
- EVSE stops responding;
- BMS lowers current limit mid-session;
- isolation fault;
- HVIL opening;
- contactor failure to close;
- charge-port lock mismatch;
- 12-V brownout/recovery;
- EVCC reboot during session;
- corrupted/invalid station message;
- failed certificate / PnC path;
- immediate manual charge stop.

Desired failure behavior:

> **Charging stops safely; the vehicle remains diagnosable; ordinary non-charging vehicle operation is not bricked.**

---

## 9. Revision-A status

The earlier concern that the MIDA EVCC forced a 24-V low-voltage island is no longer supported by current product data.

The current status is:

> **CARRY IN REVISION A / 12-V-COMPATIBLE IN PRINCIPLE / PROVISIONAL 156.4 × 101 × 25 mm BOX / J3400 AND INTERFACE DOCUMENTATION STILL REQUIRED**

This is a meaningful reduction in uncertainty.

The next useful step is original supplier documentation, not more generic charging-controller browsing.

---

## 10. Sources reviewed

Public research current as of **2026-08-31**:

- MIDA current GQEVPLC-V3.4 EVCC pages: 9–28 VDC, IP67, CP wake-up, DIN 70121 / ISO 15118, CAN/J1939/UDS and related feature claims;
- current third-party GQEVPLC-V3.4 listing: 156.4 × 101 × 25 mm, ~315 g, -40 to +85 °C, 12/24-V typical operation.

Supplier-specific questions also remain in [`ALIBABA_RFQ_WAVE1.md`](ALIBABA_RFQ_WAVE1.md).
