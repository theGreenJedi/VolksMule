# Alibaba wheels, tires, spare and recovery sourcing screen

This document screens the Prototype 1 wheel/tire/roadside-recovery layer against the current VolksMule architecture and Alibaba sourcing strategy.

It does **not** freeze an exact tire, wheel, bolt pattern, offset, jack or recovery-eye part number. It defines the preferred envelope and sourcing rules that should survive later packaging work.

> **Boring, common and replaceable beats fashionable.**

The tire is not styling. It is suspension, gearing, ground clearance, braking, snow traction, ride quality, roadside serviceability and spare-wheel packaging all at once.

## Working direction

Prototype 1 should use:

- the smallest common wheel diameter that safely clears the final brake package;
- a **tall, relatively narrow tire** with useful sidewall;
- an overall tire diameter in the **roughly 28–34 inch** range;
- one common tire/wheel size at all four corners if practical;
- a full-size spare that clears the largest brake package on the vehicle;
- normal lug hardware;
- a TPMS architecture demonstrated to meet the applicable U.S. requirements;
- deliberately engineered front and rear recovery points tied into real structure;
- dedicated vehicle jacking points that remain usable with a fully deflated tire;
- ordinary wheel-changing tools that remain useful after years in the vehicle.

The final road tire should be replaceable through the ordinary North-American replacement-tire ecosystem. Alibaba is useful for supplier discovery, prototype pricing, wheels and recovery hardware, and may be useful for initial tires if the exact model is fully qualified. VolksMule should **not** depend on international freight to replace a damaged tire on the road.

## Tire shape preference — soft requirement

Current project preference:

- favor **taller/narrower** tires rather than wide low-profile tires;
- roughly **28–34 inches overall diameter** is the useful exploration window;
- 215 mm and 225 mm widths remain attractive but are **not targets or limits**;
- 205 mm is not automatically rejected if a tall, useful tire happens to make engineering sense;
- widths above 225 mm can still win if the whole vehicle requires them;
- section width is secondary to overall diameter, sidewall, snow behavior, replacement availability, load capability and packaging.

This preference aligns with the practical desire for a tire that can cut through snow rather than float unnecessarily, retain useful sidewall for potholes/rough roads, and avoid gratuitous aero/rolling-resistance penalties.

## First tire-size study ladder

These are packaging candidates, not final selections.

| Size | Approx. diameter | Character | Current disposition |
|---|---:|---|---|
| **215/75R16** | **28.7 in** | Narrow, common-ish, substantial sidewall | Lower end of study window |
| **225/75R16** | **29.3 in** | Very broad replacement depth; still reasonably narrow | **Primary baseline** |
| **215/85R16** | **30.4 in** | Excellent tall/narrow "pizza-cutter" geometry | **Strong geometry candidate; watch LT/E-load mass/stiffness** |
| **235/85R16** | **31.7 in** | Tall and still relatively narrow for height; huge utility-truck ecosystem | **Strong 32-in study candidate; usually LT/E-load** |
| **235/80R17** | **31.8 in** | Similar tall/narrow geometry with very broad current U.S. availability | **Strong 17-in fallback if brakes force 17s** |
| 255/75R17 | 32.1 in | Common 32-in-class size but wider than preferred | Secondary comparison |
| ~33–34 in narrow commercial/4x4 sizes | varies | Maximum end of current envelope | Study only after gearing/CV/steering-clearance checks |

Do not choose the tallest tire simply because it fits the stated envelope. Taller tires affect effective gearing, acceleration, e-axle overspeed, brake torque, steering lock, scrub, CV plunge/angles, body clearance and spare packaging.

## Local replacement availability matters

Current August 2026 retail evidence shows the tall/narrow idea does **not** force VolksMule into exotic tires:

- Discount Tire currently returns **109 results for 225/75R16**.
- Discount Tire currently returns **46 results for 215/85R16**.
- Tire Rack currently shows **29 215/85R16 models in stock**.
- Discount Tire currently returns roughly **58 results involving 235/85R16**.
- Discount Tire currently returns **79 results for 235/80R17**.

That is enough depth to treat these as normal North-American replacement ecosystems rather than specialty-import sizes.

Representative current sources:

- https://www.discounttire.com/fitmentresult/tires/size/225-75-16
- https://www.discounttire.com/fitmentresult/tires/size/215-85-16
- https://www.tirerack.com/tires/TireSearchResults.jsp?diameter=16&filtering=true&ratio=85&width=215%2F
- https://www.discounttire.com/fitmentresult/tires/size/235-80-17

## Load class — do not over-tire the vehicle

Many of the best tall/narrow sizes are historically light-truck sizes, so the catalog is rich in Load Range E products. That does **not** mean VolksMule should automatically use an E-load tire.

Final tire capacity must be derived from actual front/rear GAWR, placard pressure and applicable U.S. load rules.

A needlessly heavy LT tire can add:

- unsprung mass;
- rolling resistance;
- ride harshness;
- steering inertia;
- rotational mass;
- cost.

**Rule:** choose the lightest/common construction that safely satisfies axle load, pressure, durability, rough-road and snow requirements. If the desired tall/narrow size only exists in LT/E-load construction, quantify the penalty rather than assuming it is acceptable.

## Weather and traction

VolksMule should be a normal vehicle in bad weather, not a summer tire attached to clever AWD software.

First-road-tire preference:

- all-weather or mild all-terrain pattern;
- 3PMSF severe-snow rating strongly preferred;
- strong wet braking and hydroplaning behavior;
- useful loose-surface traction;
- acceptable road noise and rolling resistance;
- no mud-terrain tread unless a real use case justifies it.

The automatic second axle remains the ace in the sleeve. **Tires are the first traction system.**

## Wheel diameter

Current priority:

1. **Try 16-inch wheels first.**
2. Move to **17 inches only if brake packaging, hub/load capability or tire availability makes 16 inches inferior.**
3. Do not move to 18+ inches for appearance.

Sixteen-inch wheels maximize sidewall inside the target overall diameter and preserve a large truck/SUV tire ecosystem. The final brake package has veto power.

## Wheel material

### Steel — preferred first utility study

Advantages:

- inexpensive;
- straightforward manufacturing;
- broad conservative-design ecosystem;
- appropriate for a utility vehicle;
- ideal for the full-size spare even if road wheels become aluminum.

Disadvantages:

- heavier;
- corrosion protection matters;
- some modern brake/load packages may have fewer suitable choices.

### Aluminum — acceptable when it earns its keep

Advantages:

- lower unsprung mass is possible;
- broad OEM ecosystem;
- useful brake-clearance flexibility.

Disadvantages:

- cheap cosmetic marketplace wheels are unacceptable without material/process/load evidence;
- fracture behavior and field repair differ from steel.

**Working preference:** package a plain 16-inch steel wheel first. Keep a simple validated aluminum wheel as a mass-reduction alternative.

## Bolt pattern / hub interface

Exact PCD remains open until hub bearing, e-axle halfshaft spline, brake package and wheel-end geometry converge.

**5x114.3 mm deserves first study** because it is extremely common across Japanese/Korean/American passenger and crossover vehicles and has broad 16/17-inch replacement-wheel availability.

Alibaba's current wheel marketplace also has abundant 5x114.3 manufacturing capacity, including 16-inch steel and aluminum products.

Representative current sources:

- https://www.alibaba.com/wheel-rim-steel-suppliers.html
- https://autopart.alibaba.com/supplier/rims-16-5-holes-supplier
- https://www.alibaba.com/5x114.3-wheels-suppliers.html

This is a standardization candidate, **not canon**.

The final wheel specification must freeze together:

- PCD;
- center bore / hub-centric interface;
- wheel stud or bolt size and seat type;
- offset;
- rim width;
- brake-caliper envelope;
- approved tire rim-width range;
- wheel load rating;
- halfshaft / hub-bearing architecture.

Avoid multi-drilled cosmetic wheels as the production reference merely because they fit several PCDs.

## Alibaba tire sourcing

Alibaba can plausibly beat U.S. retail pricing at factory/wholesale scale. Current Alibaba sourcing pages for 225/75R16 show factory pricing far below U.S. premium-brand retail pricing, especially at container quantities.

Example current source:

- https://autopart.alibaba.com/product/2257516

But initial price does not override the replacement rule.

A tire sourced through Alibaba for Prototype 1 must still have:

- exact manufacturer and plant identity;
- valid DOT Tire Identification Number / plant-code traceability for U.S. road use;
- exact load/speed/service description;
- date-code freshness;
- construction and ply/load-range specification;
- warranty/defect process;
- wet/snow/rolling-resistance evidence where available;
- a plan for buying the same size locally even if the original brand disappears.

**Preferred sourcing model:** Alibaba may supply inexpensive prototype sets or introduce a manufacturer, but the tire *size* must remain locally replaceable with several mainstream brands.

## Alibaba wheel sourcing

Alibaba clearly exposes a large 16-inch wheel manufacturing ecosystem. Road-intent wheel sourcing requires actual evidence rather than seller badges.

Require:

- actual manufacturer identity;
- exact drawing and revision;
- material specification;
- manufacturing process;
- heat treatment where applicable;
- dimensional/runout tolerances;
- rated radial/cornering load;
- impact/fatigue test reports;
- corrosion test evidence;
- process/quality certification;
- traceability marking;
- PPAP or equivalent production-control evidence where available.

A marketplace phrase such as "DOT certified wheel" is a lead, not an engineering conclusion.

## Full-size spare — required baseline

Prototype 1 should package a **full-size spare** unless packaging later proves an extraordinary reason not to.

Requirements:

- same rolling diameter as road tires within the allowable mismatch;
- wheel clears the vehicle's largest brake package;
- usable at any corner;
- TPMS compatibility if practical;
- mechanically retained in a crash;
- accessible without unloading the entire cargo area if possible;
- not dependent on sealant or compressor as the primary flat-tire plan.

A plain steel spare wheel is entirely acceptable even if road wheels are aluminum.

## Jack and wheel-changing kit

The vehicle should ship with or provide a defined location for:

- mechanical jack sized for loaded vehicle corner weight;
- lug wrench with useful leverage;
- jack handle;
- wheel-chock provision;
- simple instructions permanently available in the vehicle;
- optional plug kit / 12-V compressor as supplements, not substitutes for the spare.

Jacking points should be visible/tactile and structurally obvious. The jack must fit under the designated point with the tire fully deflated.

## Recovery points

Recovery hardware is **not** decorative tow-hook jewelry.

Prototype 1 should have clearly identified front and rear recovery/towing points whose load paths run into the structural system.

Design requirements:

- recovery-point working load and proof load defined by engineering;
- no load into bumper fascia or cosmetic brackets;
- accessible while stuck in snow/mud;
- compatible with ordinary soft shackles / rated recovery hardware as appropriate;
- corrosion protected;
- replaceable if damaged;
- owner documentation distinguishes towing, tie-down and dynamic-recovery limits.

Alibaba is a reasonable source for forged/machined hooks, shackles and recovery eyes **only after VolksMule defines the geometry and load case**. The body/chassis attachment is VolksMule-owned engineering.

## Durability / packaging tests

Before freezing wheel/tire geometry, test or model:

- full lock + full bump + full droop clearance;
- snow/ice buildup clearance;
- brake hose and ABS harness clearance;
- CV joint angle/plunge through travel;
- e-axle rpm at maximum vehicle speed;
- gradeability and launch torque with final rolling radius;
- braking torque requirement with final rolling radius;
- scrub radius / steering effort;
- speedometer/odometer calibration;
- spare packaging;
- jack access with a flat tire;
- snow traction and wet stopping;
- pothole/rough-road impact behavior.

## Current decision state

### GREEN — source readily

- tires in common tall/narrow sizes;
- steel wheels;
- validated aluminum wheels;
- TPMS sensors once protocol is frozen;
- lug hardware;
- jack and wheel tools;
- recovery hardware fabricated to a specified interface.

### YELLOW — choose only after integration

- exact tire size;
- exact wheel diameter;
- exact PCD/offset/center bore;
- load range;
- final road-tire brand/model;
- Alibaba-sourced complete tire sets.

### RED — do not do

- unique tire size that cannot be replaced locally;
- low-profile wheel/tire package chosen for appearance;
- tire-inflator/sealant as the only flat-tire plan;
- cosmetic/unrated recovery hooks;
- unverified marketplace wheels designed only around price/style.

## Near-term recommendation

Use the following as the first packaging comparison rather than freezing a tire:

1. **225/75R16 — 29.3 in:** local-availability baseline.
2. **215/85R16 — 30.4 in:** strongest narrow/tall geometry study.
3. **235/85R16 — 31.7 in:** 32-inch-class tall/narrow utility comparison.
4. **235/80R17 — 31.8 in:** 17-inch brake-clearance fallback with excellent current replacement depth.

The winner should be the **narrowest/lightest common tire that gives the desired diameter and load capacity without forcing an overly stiff construction or compromising braking, gearing or steering clearance.**

That is more VolksMule than selecting a width first.