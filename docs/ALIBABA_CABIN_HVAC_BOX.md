# Alibaba cabin HVAC box — simple single-zone air handling

Research current as of **2026-09-01**.

This document continues the VolksMule roadmap sourcing mission into the cabin air-handling box itself: blower, evaporator, heater/heat exchanger, air doors, drains and duct outlets.

The high-voltage compressor, battery thermal system, coolant heater and physical dashboard controls are covered separately.

> **Prototype 1 needs a small, serviceable single-zone air box with excellent defrost. It does not need a luxury multi-zone climate monument.**

---

## 1. Functional requirement

The cabin HVAC box must provide:

- fresh-air intake;
- recirculation path;
- cabin filter;
- blower;
- evaporator/dehumidification path;
- heating path from heat-pump/coolant/PTC architecture as selected;
- face/floor/windshield air distribution;
- positive windshield defrost/defog;
- condensate drainage;
- accessible evaporator/heater-core service where practical;
- physical/local actuation compatible with the three-knob control philosophy.

It does not own the compressor, battery thermal logic, infotainment or vehicle authority.

---

# 2. Cheap prototype benchmark — BEU-404-100 family

Alibaba currently exposes the **BEU-404-100** universal under-dash evaporator family through several suppliers/brands, including GOUKU and other automotive-A/C sellers.

A current low-MOQ Alibaba listing is approximately **$35–40** for a 12-V universal under-dash evaporator unit with tactile controls/mechanical thermostat.

Independent current supplier catalogs for the same BEU-404-100 family publish a useful engineering envelope:

- approximately **404 × 335 × 156 mm** housing;
- approximately **4.8 kg**;
- **12 V / 6 A** or 24-V variants;
- three blower speeds;
- maximum airflow about **562–586 m³/h**;
- published cooling-capacity figures around **18,800–19,300 BTU/h** on one current catalog;
- mechanical thermostat on common versions;
- aluminum multi-pass evaporator.

Other current sellers publish differing dimensions/specs for BEU-404-labelled products, which is exactly why the model name alone is not a final engineering specification.

### What it is good for

A BEU-404-class unit is useful for:

- Revision-A packaging box;
- bench airflow tests;
- initial duct sizing;
- blower/noise experiments;
- windshield-defrost duct prototyping;
- proving that a compact single-zone air handler is physically practical.

### What it is not

It is not automatically:

- the final road-intent HVAC box;
- R1234yf-qualified for our exact system;
- heat-pump optimized;
- crash/NVH/flammability validated for the final dash;
- equipped with the final heater-core/condenser arrangement;
- sufficient for FMVSS defrost validation without duct/system testing.

### Current verdict

> **GREEN low-cost Prototype-1 / bench reference; YELLOW-RED as an automatic production selection.**

---

# 3. Road-intent/custom HVAC benchmark — Hubei Meibiao

**Hubei Meibiao Automotive Refrigeration System Co., Ltd.** is a substantially stronger road-intent reference for a custom passenger-vehicle HVAC box.

Current manufacturer material states:

- IATF 16949:2016 quality-system certification;
- CNAS-recognized laboratory;
- provincial technical/R&D center;
- a dedicated automotive-air-conditioning research institute;
- approximately 36 automotive HVAC design engineers;
- 3D CAD/CAE capability;
- status as a core supplier to FAW and Valeo and strategic supplier to multiple vehicle manufacturers.

### Why it matters

This is the kind of company to involve if the Mule eventually needs a purpose-built compact single-zone HVAC case rather than adapting an existing box.

It has the capability to engineer:

- air distribution;
- evaporator/heater packaging;
- blower sizing;
- defrost performance;
- molded casework;
- validation and vehicle integration.

### Current verdict

> **GREEN road-intent/custom-system benchmark.**

This does not mean we contact them now or freeze them as supplier. It proves a credible Chinese automotive-HVAC engineering ecosystem exists if the body package ultimately needs a custom box.

---

# 4. Heat-exchanger component path — HBS

**Guangzhou Huadu Bisheng (HBS) Automotive Air Conditioner Factory** is a useful component-manufacturing path.

Current manufacturer material states:

- established in 1993;
- IATF 16949:2016;
- approximately 2 million-unit annual production capability;
- in-house production of automotive evaporators, condensers, radiators and related heat exchangers;
- global customer/dealer base including North America.

### VolksMule role

If we design or adapt our own case, HBS-class suppliers can provide the actual:

- evaporator core;
- condenser/front heat exchanger;
- radiator;
- possibly heater-core/related exchanger.

That helps keep the molded air box and heat-exchanger function separable.

### Verdict

> **GREEN heat-exchanger supplier class / exact core open.**

---

# 5. Alibaba universal HVAC units — use with discipline

Alibaba also exposes many complete 12-V/24-V under-dash and parking-A/C systems.

Current examples advertise:

- 1–3.5 kW cooling classes;
- 12/24-V blowers;
- mechanical or digital control panels;
- evaporator/condenser combinations;
- compact truck/van/retrofit use.

These are useful for:

- packaging references;
- inexpensive prototypes;
- airflow/duct experiments;
- bench thermal work.

They are **not** evidence that an entire low-voltage parking-A/C system is the right production architecture for a 400-V-class EV.

VolksMule already has a dedicated HV compressor/thermal architecture. We need the **air-handling box**, not another complete independent air-conditioning system competing with it.

---

# 6. Revision-A packaging reserve

Use the documented BEU-404 family as a conservative compact benchmark.

Initial air-box reserve:

- roughly **450 mm width**;
- roughly **380 mm fore/aft or vertical package dimension depending orientation**;
- roughly **200 mm minimum core housing depth**, plus ducts/door/linkage/service clearance.

This is deliberately larger than the better-documented 404 × 335 × 156-mm BEU-404 core box.

Additional reserve is required for:

- filter/fresh-air inlet;
- recirc door;
- heater section;
- face/floor/defrost distribution plenum;
- condensate drain;
- cable/actuator motion;
- service-removal route.

> **Do not mistake the evaporator-unit housing for the complete dashboard HVAC envelope.**

---

# 7. Blower target

The BEU-404 benchmark's ~562–586 m³/h maximum published airflow is a useful first-scale reference for a small cabin.

The final blower must be sized from:

- windshield area and defrost requirement;
- duct pressure loss;
- cabin volume;
- filter pressure drop;
- evaporator/heater-core resistance;
- noise target;
- 12-V load budget.

A replaceable 12-V centrifugal blower motor/wheel remains preferred.

### Rule

Do not hide the blower inside a welded/bonded case that requires dashboard destruction to replace.

---

# 8. Defrost-first distribution geometry

For Prototype 1, the air box should be optimized around safety and simplicity rather than multi-zone luxury.

Minimum distribution modes:

1. face;
2. face/floor if useful;
3. floor;
4. floor/defrost if useful;
5. windshield defrost.

A dedicated physical **MAX DEFROST** command must be able to drive the box into a known clearing configuration.

### Preferred mode-door actuation

- Bowden/push-pull cable first;
- simple local 12-V actuator only where cable routing is materially worse.

The final air box should be selected or designed with those actuation choices in mind.

---

# 9. Heating path

The cabin box need not contain a high-voltage PTC heater if the vehicle uses a coolant-based heater path.

Current preferred architecture remains compatible with:

- heat-pump/refrigerant heating;
- coolant heater/PTC backup;
- coolant-to-air heater core or refrigerant-side cabin condenser depending final thermal topology.

The air box therefore needs a defined heat-exchanger location and service interface, not ownership of the thermal-generation method.

### Rule

> **The cabin box moves and distributes air. The thermal plant decides how the air gets hot or cold.**

---

# 10. Cabin filter / fresh-air plenum

The Mule should use an ordinary replaceable cabin filter.

Design requirements:

- accessible from cabin/cowl without removing the dashboard;
- common rectangular filter size or documented cut-to-size media if practical;
- water-separated cowl fresh-air inlet;
- debris screen;
- condensate/water paths that do not dump into the blower/electronics;
- recirculation door downstream/upstream as appropriate.

Avoid a unique proprietary filter cartridge if a common size can be packaged.

---

# 11. Serviceability requirements

The final box should allow reasonable independent replacement of:

- blower motor/wheel;
- blower resistor/PWM module;
- cabin filter;
- evaporator temperature sensor;
- mode cable/actuator;
- recirc cable/actuator;
- heater-core/evaporator assembly where practical;
- drain hose.

No service action should require an infotainment pairing or cloud procedure.

### Desired architecture

Split case with screws/clips and documented seams is preferable to an ultrasonically welded one-use case if packaging/NVH allows.

---

# 12. Supplier / component shortlist

| Function | Current first path | Mode | Gate |
|---|---|---|---|
| Prototype air-box benchmark | BEU-404-100 family / GOUKU-Alibaba equivalent | BUY SAMPLE later / benchmark | exact dimensions/spec of purchased version |
| Road-intent custom HVAC box | Hubei Meibiao-class automotive HVAC integrator | DESIGN WITH SUPPLIER / BUY | final dash/body/defrost requirement |
| Evaporator / heat exchangers | HBS-class IATF automotive core manufacturer | BUY to spec | refrigerant/core/pressure/thermal design |
| Blower | common 12-V centrifugal automotive family | BUY | airflow/static pressure/noise/load budget |
| Mode actuation | Bowden cable first | BUY to length | HVAC-door geometry |
| Actuator fallback | simple local 12-V position actuator | BUY | documented feedback/fail state |
| Cabin filter | common replaceable automotive element | LOCAL-FIRST | final plenum size |
| Case/ducting | donor/prototype fabricated; later molded to project CAD | ADAPT / DESIGN | final dash/windshield/body geometry |

---

# 13. What not to buy

Reject as Prototype-1 architecture:

- enormous four-zone HVAC cases;
- rooftop/parking A/C unit used merely because it is easy to order;
- digital-screen-only air box;
- integrated climate ECU that requires proprietary CAN for a blower to run;
- universal evaporator treated as road-ready without defrost/thermal validation;
- air box whose blower/filter cannot be serviced without complete dashboard removal if avoidable;
- custom molded case whose CAD/tooling remains supplier-secret.

---

# 14. Current verdict

The cabin-air-box problem is no longer an unknown-size black box.

Revision A can carry a compact single-zone envelope based on the BEU-404 class while body/dashboard geometry develops.

The sourcing strategy is:

> **Cheap universal unit for prototype airflow/packaging intelligence; serious automotive HVAC integrator or project-owned case for road intent.**

That keeps the physical HVAC system simple without confusing `simple` with `unengineered`.

---

## Sources reviewed

Public research current as of **2026-09-01**:

- current Alibaba GOUKU BEU-404 universal 12-V under-dash evaporator listings;
- current BEU-404 family engineering catalogs publishing ~404 × 335 × 156 mm, ~4.8 kg, 12 V/6 A, three-speed blower and ~562–586 m³/h airflow;
- Hubei Meibiao Automotive Refrigeration System current manufacturer material: IATF 16949, CNAS lab, automotive HVAC research institute, engineering staff and OEM/Tier-1 relationships;
- Guangzhou HBS current manufacturer material: IATF 16949 and automotive evaporator/condenser/radiator production.

Marketplace specifications remain exact-part verification items; conflicting BEU-404 listing dimensions are specifically treated as a reason to require the exact purchased drawing.
