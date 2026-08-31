# How big the first Mule should be

This is the working packaging envelope for **VolksMule Prototype 1**.

The goal is not to copy a first-generation Honda CR-V. The CR-V is our reference because its footprint, visibility, cargo usefulness, ground clearance, and simple utility were unusually good. We use it to keep ourselves honest about what “compact utility vehicle” means while building a two-seat electric vehicle around modern safety requirements.

> **Reference the good package. Do not inherit the old car by accident.**

These are working targets, not frozen production dimensions. A target may move when a real requirement, component, crash structure, battery, or test result gives us a better reason.

## The reference point

A 1997–1998 first-generation CR-V was roughly:

- 177.6 in long
- 68.9 in wide without mirrors
- 65.9 in tall
- 103.2 in wheelbase
- about 60 in front/rear track
- 8.1 in ground clearance
- about 3,100–3,250 lb curb weight depending on configuration
- about 35 ft curb-to-curb turning circle
- about 67 ft³ maximum cargo volume with the rear passenger volume converted to cargo

Those numbers are a ruler, not a specification.

---

# 1. Keep the outside compact

| Item | Working target | Why |
|---|---:|---|
| Overall length | **172–180 in** | CR-V-scale usefulness without modern SUV bloat. |
| Overall width, no mirrors | **68–72 in** | Wide enough for structure, seats, battery protection and stability; still easy to place on narrow roads and in garages. |
| Overall height | **64–68 in** | Upright visibility and cargo volume without becoming a tall heavy box. |
| Wheelbase | **101–107 in** | Keeps the compact footprint while leaving room for battery, crash structure and useful cargo. |
| Track width | **about 60–64 in** | Stability and packaging target; final value follows suspension/wheel choices. |
| Turning circle | **36 ft or less** | A utility vehicle should be easy to maneuver. |

**Hard rule:** do not make the vehicle bigger merely because an available component is oversized. Change the component before casually growing the whole Mule.

---

# 2. Keep the weight well below the regulatory cliff

The current federal rules map uses **3,500 kg / 7,716 lb GVWR** as an important ceiling because FMVSS 135 applies to our intended MPV at or below that weight.

That is a ceiling, not a design target.

Working engineering targets:

- **Curb weight:** aim for **4,200 lb or less**.
- **Preferred curb weight:** below **4,000 lb** if safety, range, durability, cost, and serviceability allow it.
- **Target GVWR:** approximately **5,500 lb or less** unless payload engineering proves that unreasonable.
- **Usable payload target:** at least **1,000 lb** after the production curb weight is known.
- Keep meaningful margin between target GVWR and 7,716 lb so normal design growth cannot accidentally change the brake/regulatory regime.

We will not chase low weight by weakening crash structure, reducing battery protection, or using fragile exotic materials. Simplicity and intelligent packaging come before heroic lightweighting.

---

# 3. Make the off-road features real

VolksMule is intended to be a genuine MPV with occasional off-road capability, not a passenger car wearing an SUV costume.

NHTSA has repeatedly treated **four-wheel drive plus meaningful ground clearance/approach/departure geometry and protective features** as evidence supporting MPV classification. Part 523 uses a separate fuel-economy classification test, but its dimensions are a useful objective design target and have been referenced by NHTSA when discussing off-road features.

Prototype 1 should therefore be designed to meet **all five** of these Part 523 geometry numbers if reasonably possible, even though that rule is not itself the FMVSS definition of an MPV:

- **Approach angle:** at least **28°**
- **Breakover angle:** at least **14°**
- **Departure angle:** at least **20°**
- **Running clearance:** at least **20 cm / 7.87 in**
- **Front and rear axle clearance:** at least **18 cm / 7.09 in**

Additional VolksMule off-road/rough-road features:

- automatic on-demand second-axle traction;
- battery and powertrain underside protection designed for rocks/debris;
- protected HV and cooling lines;
- no fragile low-hanging cosmetic air dam that destroys useful approach geometry;
- suspension travel appropriate for rough roads rather than appearance-only ride height;
- recovery/tow points with documented load paths;
- water/mud/debris protection for connectors and service-critical components.

These features have to be useful in the real world. We are not adding fake skid plates to win a classification argument.

---

# 4. Two seats means the rest of the cabin earns its keep

Prototype 1 has **two designated seating positions**. The volume behind them is working space, not a future third row waiting to happen.

Packaging targets:

- flat or nearly flat primary cargo floor;
- **about 60 ft³ or more of useful enclosed cargo volume** as an initial target;
- a practical path to a **roughly 6 ft sleeping/tool platform** without removing permanent safety structure;
- cargo tie-down points tied to real structure;
- room for permanent or modular tool storage;
- heavy cargo located low and restrained;
- rear cargo access large enough that the nominal volume can actually be used;
- interior trim and panels should remain removable for service.

The old CR-V demonstrated an important principle: passenger volume that is not actually needed can be far more valuable as tools, storage, and sleeping/work space. Prototype 1 starts from that lesson instead of installing rear seats and asking owners to remove them later.

---

# 5. Do not let the battery eat the vehicle

The battery must fit the vehicle mission; the vehicle should not become enormous just to package an arbitrary battery.

Before pack capacity is frozen, packaging CAD must reserve space for:

- front and side crash structures;
- adequate ground/running clearance;
- battery enclosure and intrusion protection;
- service disconnect access;
- HV routing;
- cooling/thermal hardware;
- seat and belt anchor load paths;
- suspension travel and jounce clearance;
- drivetrain/e-axle service removal paths;
- protected venting paths required by the HV safety architecture.

Range will be selected after we understand the mass/space/cost curve. “More battery” is not automatically “better Mule.”

---

# 6. The driver should see out of it

The first-generation CR-V reference matters as much for visibility as dimensions.

Working requirements:

- upright seating position;
- low enough beltline to see nearby obstacles;
- pillars no thicker than safety requires;
- large useful windshield area;
- mirrors/cameras should supplement natural sightlines rather than excuse bad body geometry;
- hood/front-body geometry should make the front corners understandable from the driver's seat;
- no styling-driven rear window slit.

Crashworthiness wins when there is a genuine conflict, but styling never gets to destroy visibility for free.

---

# 7. Things we are deliberately not freezing yet

Do not turn this envelope into premature architecture. These remain open until engineering closes them:

- exact wheel/tire size;
- exact track width;
- exact suspension type;
- exact battery capacity/chemistry/voltage;
- exact motor/e-axle selection;
- exact front/rear overhang;
- exact towing rating;
- exact roof load;
- exact cargo dimensions;
- exact curb/GVWR values;
- exact approach/breakover/departure values above the minimum targets.

---

# 8. What would make us change the envelope

Change a target when evidence shows one of these:

1. an applicable safety rule requires it;
2. crash/structural analysis requires it;
3. a proven commodity component produces a major whole-vehicle benefit and cannot reasonably be adapted within the target;
4. battery/thermal safety requires it;
5. real human packaging proves the cabin/cargo target does not work;
6. testing proves stability, ride, steering, or rough-road capability needs a change;
7. the change materially improves repairability or parts substitutability without causing a larger harm.

Do **not** change the envelope because current SUV fashion is larger, because a supplier says “everyone uses this,” or because unused space looks impressive on a spec sheet.

---

# 9. Definition of done for packaging

Before we start treating a real BOM as architecture, produce a first packaging model that shows:

- [ ] two occupied front seating envelopes;
- [ ] steering/pedal/column envelope;
- [ ] required occupant-restraint/airbag zones;
- [ ] front, side, roof and rear crash structure allowances;
- [ ] tire/wheel/suspension full-travel envelopes;
- [ ] steering lock envelope;
- [ ] battery envelope and protection zone;
- [ ] front and rear drive-unit candidate envelopes;
- [ ] HVAC/defrost hardware envelope;
- [ ] cargo floor and major cargo dimensions;
- [ ] service-removal paths for major modules;
- [ ] approach, breakover, departure and running-clearance checks;
- [ ] estimated curb mass and axle loads;
- [ ] estimated GVWR/payload;
- [ ] turning-circle estimate.

Once those boxes are filled, **then** the vehicle is ready for disciplined component selection.

> **Make it small enough to be handy, big enough to be useful, and no bigger than it needs to be.**
