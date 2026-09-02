# VolksMule Prototype 1 — roadmap sourcing BOM skeleton

Status: **working sourcing control document**

Updated: **2026-09-01**

This is not a purchase order and not a frozen production BOM.

It is the bridge between:

- the Prototype-1 subsystem architecture;
- the roadmap-driven Alibaba sourcing work;
- local/donor alternatives;
- future supplier documents;
- eventual exact part-number selection.

> **Choose the right kind of thing, identify a credible sourcing path, then freeze the exact thing only when the vehicle gives us enough information.**

---

## Status legend

- **CARRY** — credible family/path; keep in current design study.
- **OPEN** — exact choice intentionally waits for geometry/load/electrical data.
- **LOCAL-FIRST** — Alibaba may inform cost/supply, but local availability is more valuable.
- **SYSTEM** — must be engineered/calibrated as a coherent vehicle safety system.
- **DESIGN** — VolksMule owns the architecture/geometry; suppliers fabricate pieces.
- **REJECT GENERIC** — marketplace item exists but generic purchase is the wrong engineering answer.

---

# 1. Structure / body

| Item | Mode | Preferred sourcing path | Local / alternate path | Current status | Blocker before exact selection | Service / safety gate |
|---|---|---|---|---|---|---|
| Central safety cell | DESIGN | local prototype steel fabrication; later IATF body supplier once CAD stable | local welding/fabrication | **DESIGN** | crash/load-path analysis, packaging CAD | body must remain structurally whole without battery |
| Front cradle | ADAPT / DESIGN | drawing-based fabrication; China later after geometry settles | local fabricated prototype | **OPEN** | READ2982 CAD, steering/suspension hard points | bolt-on/removable, service paths preserved |
| Rear cradle | ADAPT / DESIGN | drawing-based fabrication | local fabricated prototype | **OPEN** | rear drive geometry + suspension hard points | bolt-on/removable |
| Exterior panels | BUY / DESIGN | simple steel/aluminum/composite panels to drawing | local sheet/composite fabrication | **OPEN** | final body geometry | individually replaceable where practical |
| Door hinges/latches | BUY / ADAPT | proven automotive hardware family; donor/application latch first | donor/common U.S. vehicle hardware | **CARRY** | door mass/axis/section | FMVSS 206 evidence for final system |
| Exterior/interior handles | BUY | mechanical conventional hardware | donor/common | **CARRY** | door architecture | must work without 12-V power |
| Weather seals / glass channels | BUY / ADAPT | **Hebei Shida / Letu** automotive EPDM system; common profiles first | donor/common extrusion profiles | **CARRY supplier family / exact profile open** | flange/opening/glass geometry | project-owned profile specs; no one-off orphan rubber |
| Manual window regulator | BUY / ADAPT | common mechanical regulator family; Alibaba mechanical suppliers | common donor regulator | **CARRY MANUAL BASELINE** | door glass travel/geometry | no motor/controller dependency |
| Door / quarter / rear glazing | BUY / ADAPT | **Fuyao / Xinyi benchmark; qualified custom tempered glass to project drawing** | local automotive glass | **CARRY strategy / geometry open** | door/body openings and regulator geometry | correct FMVSS 205/ANSI Z26.1 use; project owns pane definition |
| Locks | BUY / ADAPT | keyed/mechanical lock family | common donor lock set | **CARRY MANUAL BASELINE** | door/latch geometry | local mechanical access retained |
| Harness grommets / boots | BUY / ADAPT | Shida/Letu molded-rubber family; standardized size vocabulary | local rubber/grommet supplier | **CARRY commodity** | harness/pass-through geometry | replaceable, documented grip/diameter/material |
| Hood support | DESIGN / BUY commodity | mechanical prop rod baseline | passive automotive gas strut if it earns usability | **CARRY SIMPLE BASELINE** | hood mass/geometry | must not require powered mechanism |
| Rear hatch support | BUY / ADAPT | passive automotive gas struts if top-hinged hatch | common local gas strut | **OPEN** | hatch mass/CG/hinge geometry | common ends/force/length documented |
| Underbody structural protection | DESIGN | VolksMule pack/skid load paths | local structural fabrication | **DESIGN** | crash/impact/pack geometry | impact loads cannot be delegated to a thin cover |
| Sacrificial skid / splash panels | DESIGN + BUY fabrication | local Mule-1 sheet/HDPE; Alibaba stable-CAD fabrication later | local | **CARRY fabrication path** | underbody geometry/service zones | removable separately from pack/suspension |
| Wheel liners / mud flaps | BUY / DESIGN | local thermoformed prototype; Alibaba PP/PE production later | local molded/sheet plastic | **CARRY category** | tire/jounce/body geometry | cheap, replaceable, no hidden salt traps |

---

# 2. Suspension / wheel ends

| Item | Mode | Preferred sourcing path | Local / alternate path | Current status | Blocker | Gate |
|---|---|---|---|---|---|---|
| Front suspension geometry | DESIGN | VolksMule-owned hard points; components sourced around them | — | **DESIGN** | first packaging CAD | bump steer, scrub radius, CV angle, travel |
| Rear suspension geometry | DESIGN | compact independent layout; exact architecture open | — | **DESIGN** | rear packaging/hard points | travel, cargo/pack space, toe/camber behavior |
| Hub/bearing assemblies | BUY / ADAPT | **Zhejiang/Hangzhou Xingjie Gen-III family** | common U.S.-market hub family | **CARRY supplier family** | bolt pattern, axle spline, loads, encoder | high-volume replaceable bearing preferred |
| Front knuckles | DONOR / ADAPT / DESIGN | existing knuckle first; drawing-based China/local if needed | common donor family | **OPEN** | steering axis/hub/brake geometry | do not let donor knuckle dictate bad kinematics |
| Rear knuckles | DONOR / ADAPT / DESIGN | existing common family first | local drawing-based fabrication | **OPEN** | rear hard points/hub/brake | replaceable hub/ball joints preferred |
| Control arms/links | ADAPT / DESIGN | existing common arms; Jinjiang-class fabrication later | local fabricated prototype | **OPEN** | hard points/loads | common bushings/ball joints preferred |
| Ball joints | BUY | common replaceable automotive family | local parts-store family | **LOCAL-FIRST** | knuckle/arm geometry | avoid unique joint taper |
| Bushings | BUY | common rubber/elastomer family | local replacement | **OPEN** | load/NVH geometry | replaceable, ordinary presses/tools |
| Dampers/struts | BUY / ADAPT | **Hubei Dongfeng JC** / equivalent automotive damper manufacturer | Monroe/KYB-style local family | **CARRY supplier family** | installed length, stroke, corner load, motion ratio | passive, serviceable, no ECU dependency |
| Coil springs | BUY to spec | **Meili** benchmark; Alibaba IATF custom spring makers | local spring shop / common application | **OPEN** | corner weights, motion ratios, ride frequency | fatigue/test evidence |
| Anti-roll bars | BUY / DESIGN | Meili/Jinjiang-class supplier after handling study | local bar fabricator/donor | **OPEN** | roll stiffness requirement | only if handling/ESC work proves useful |

---

# 3. Steering

| Item | Mode | Preferred path | Alternate | Status | Blocker | Gate |
|---|---|---|---|---|---|---|
| Rack-and-pinion | BUY / ADAPT | Zhuzhou Elite / common rack family | donor North-American compact SUV rack | **OPEN** | track, rack travel, steering-arm geometry | continuous mechanical path |
| EPS assist | BUY / ADAPT | **Zhuzhou Elite P-EPS / DP-EPS first study** | C-EPS donor/common; R-EPS if loads require | **CARRY family** | assist load, rack/column geometry | local diagnostics/calibration, no steer-by-wire |
| Steering column | BUY / DONOR / ADAPT | collapsible common automotive column | donor/common | **OPEN** | occupant H-point, wheel, firewall/rack | crash collapse + mechanical continuity |
| Steering-angle sensor | BUY / SYSTEM | EPS/ESC-compatible automotive sensor | donor/common | **OPEN** | ESC/EPS architecture | documented signal/calibration |
| Steering wheel | BUY / ADAPT | restraint-compatible supplier/donor assembly | integrated restraint supplier | **SYSTEM** | airbag/restraint selection | cannot mix casually with airbag system |

---

# 4. Brakes

| Item | Mode | Preferred path | Alternate | Status | Blocker | Gate |
|---|---|---|---|---|---|---|
| Front rotors | BUY | high-volume ~320-mm-class application; Alibaba alternate manufacturer | local mass-market rotor family | **OPEN** | axle load, caliper, hub/bolt pattern | material/vane/runout/thermal validation |
| Rear rotors | BUY | high-volume ~310-mm-class application | local mass-market rotor | **OPEN** | rear load/caliper/parking brake | same |
| Front calipers | DONOR / ADAPT | proven OEM application family | **APG** supported mechanical/system family | **OPEN** | hydraulic sizing, rotor, axle load | known piston/pad/seal/service parts |
| Rear calipers | DONOR / ADAPT | proven application family, mechanical parking brake preferred | APG/supplier-supported family | **OPEN** | parking-brake architecture | friction retention independent of HV |
| Pads | BUY | common pad shape tied to chosen caliper | local parts-store | **LOCAL-FIRST** | caliper selection | multiple formulations/sources |
| Brake hoses | BUY regulated | compliant manufacturer for exact assemblies | U.S.-available FMVSS-106 hardware | **OPEN** | corner geometry/length | exact regulated-equipment evidence |
| Master cylinder / booster | BUY / DONOR | proven vehicle family | supplier system package | **OPEN** | pedal ratio, caliper displacement, AEB architecture | friction brakes must stop vehicle without regen |
| ABS/ESC HCU | SYSTEM | **APG / WBTL-Bethel class** vehicle-calibrated supplier | coherent donor/integrator path | **SYSTEM** | mass, CG, wheel/tire, brake hardware | vehicle calibration; no generic pump purchase |
| AEB pressure control | SYSTEM | integrated with calibrated ESC/HCU | same | **SYSTEM** | FMVSS/AEB validation program | dedicated safety function, no autonomy creep |
| Parking brake | BUY / ADAPT | cable/mechanical system | donor/common | **CARRY preference** | rear caliper/corner packaging | holds vehicle mechanically |

---

# 5. Wheels / tires / recovery

| Item | Mode | Preferred path | Alternate | Status | Blocker | Gate |
|---|---|---|---|---|---|---|
| Wheel diameter | BUY | **16 in first study** | 17 in if brakes require | **OPEN** | caliper/rotor/knuckle clearance | smallest common wheel safely clearing brakes |
| Tire size | BUY | tall/narrow common sizes in roughly **28–34 in OD** envelope | local equivalent | **OPEN** | final gearing, body clearance, loads | local replacement availability wins |
| Tire width | BUY | relatively narrow for height; not locked to 215/225 | local equivalent | **PREFERENCE** | load/handling/snow/clearance | real sidewall; no fashion low-profile tire |
| Spare | BUY | full-size / same rolling diameter | common steel spare wheel | **CARRY** | final size/bolt pattern | must clear brakes |
| Jack/tools | BUY | common mechanical jack + lug tools | local retail | **LOCAL-FIRST** | vehicle lift points | usable roadside without special equipment |
| Recovery points | DESIGN + BUY fabrication | welded/bolted engineered points | local fabrication | **DESIGN** | crash/subframe loads | rated front/rear procedure documented |

---

# 6. Front / rear drive

| Item | Mode | Preferred path | Alternate | Status | Blocker | Gate |
|---|---|---|---|---|---|---|
| Front e-axle | BUY / ADAPT | **Rawsuns READ2982** | Sumcont 60/120-kW-class integrated unit | **CARRY READ2982 study** | original installation CAD/CAN/thermal data | road speed, service, local diagnostics |
| Rear e-axle | BUY / ADAPT | second READ2982-sized envelope for commonality | smaller high-speed/disconnect unit later | **OPEN / conservative symmetric package** | coast drag, overspeed, disconnect evidence | inactive rear must tolerate full road speed |
| Front inverter | BUY | matching documented e-axle inverter | Sumcont/alternate | **OPEN** | HV window/CAN/current map | torque watchdog/fail-safe/local service |
| Rear inverter | BUY | same family where possible | alternate | **OPEN** | rear-unit selection | zero-torque coast behavior documented |
| Halfshafts/CV | BUY / ADAPT | **Wuxi Kingfarm** using common joint ends | local rebuilt/OEM application family | **CARRY supplier family** | e-axle spline + hub spline + travel | custom length okay; custom service ecosystem not |
| Outer CV | BUY | common high-volume hub-compatible joint | local parts-store joint | **LOCAL-FIRST** | hub/knuckle choice | replaceable boots/joints |
| Inner CV | BUY / ADAPT | existing joint compatible with e-axle output | custom hybrid shaft if needed | **OPEN** | Rawsuns output drawing | plunge/angle/torque/rpm limits |
| Wheel-speed sensors | BUY | **JinzhouABS-class active sensors** with encoded hubs | common local sensor family | **CARRY architecture** | hub encoder + HCU signal spec | direct safety input to ABS/ESC |
| E-axle mounts | DESIGN + BUY | drawing/load-driven isolators/brackets | local fabrication | **OPEN** | e-axle CAD/load/NVH | no generic mount selected by appearance |

---

# 7. Battery cells / pack

| Item | Mode | Preferred path | Alternate | Status | Blocker | Gate |
|---|---|---|---|---|---|---|
| LFP cells | BUY | **REPT BATTERO 171-Ah / 150-Ah BEV families** | EVE automotive power-cell path | **CARRY REPT study** | 171-Ah full engineering spec; current/power reconciliation | manufacturer-direct provenance + testing |
| Pack series count | DESIGN | ~400-V-class study | — | **OPEN** | inverter/OBC/DCFC/cell voltage reconciliation | electrical window first, BMS follows pack |
| Parallel architecture | DESIGN | 1P or higher as power/energy requires | — | **OPEN** | continuous/peak current duty | avoid overrating based on peak-only data |
| Compression/end plates | DESIGN + BUY fabrication | local/Alibaba drawing-based | local | **OPEN** | exact cell preload/swelling | REPT compression limits maintained |
| Cold plates | DESIGN + BUY fabrication | FSW/vacuum-brazed Alibaba suppliers to drawing | local coolant plate fabricator | **CARRY category** | module layout/thermal model | no convenient cold plate dictates cell layout |
| Pack enclosure | DESIGN | local Mule-1 fabrication; later China stable-CAD supplier | local | **DESIGN** | crash/underbody/vent/service model | non-structural, removable, protected |
| Service disconnect | BUY | Yonggui / Chilye automotive MSD | alternate automotive supplier | **CARRY** | final current/voltage | physical local service isolation |
| Pack venting | DESIGN + BUY | automotive vent hardware to pack design | local/Tier-1 | **OPEN** | cell vent/propagation data | protected directed vent path |

---

# 8. BMS / HV safety / distribution

| Item | Mode | Preferred path | Alternate | Status | Blocker | Gate |
|---|---|---|---|---|---|---|
| Road-intent BMS | BUY / integrate | **Ligoo Power BMS** | Suzhou Miaoyi/Mewyeah automotive BMS | **CARRY supplier paths** | exact cell count/CAD/CAN/service docs | motive-power evidence, local recovery |
| Development BMS | BUY | ENNOID/open development platform | Orion benchmark/other transparent dev platform | **CARRY for bench** | test-pack architecture | not automatically road-intent |
| Main contactors | BUY | **Hongfa HFE82V-class geometry** | equivalent automotive contactor | **CARRY 400-A-class package envelope** | final current/fault study | interrupt/fault rating, coil/fail state |
| Main fuse | BUY | automotive EV fuse family | Littelfuse/Mersen-class local equivalent | **OPEN** | fault/current study | conductor/contactors coordinated |
| Precharge | DESIGN + BUY components | standard resistor/contactor path | alternate | **OPEN** | DC-link capacitance/inverter set | timed/diagnosable failure state |
| Current sensor | BUY | automotive isolated Hall/shunt family | local Tier-1 | **OPEN** | current range/accuracy needs | BMS/HV safety integration |
| Isolation monitor | BUY | **Bender-class automotive IMD** | qualified alternate | **CARRY benchmark** | exact HV topology | continuous chassis isolation monitoring |
| HVIL | DESIGN + BUY interfaces | Yonggui/Chilye connector/MSD family | alternate automotive | **CARRY** | final connectors/branches | local transparent loop |
| BDU/PDU enclosure | DESIGN | ~600×350×180-mm Rev-A reserve | local fabricated box | **DESIGN** | final branches/current/fuse map | transparent, separately serviceable branches |
| HV connectors | BUY | **Yonggui / Chilye** | TE/Amphenol/Tier-1 equivalent | **CARRY supplier paths** | cable/current/application geometry | keyed/HVIL/IP/derating evidence |
| HV cable/busbar | BUY / DESIGN | automotive orange cable + drawing-based busbars | local Tier-1 | **OPEN** | currents/routes | touch-safe, strain relief, service clearances |

---

# 9. Charging / onboard power

| Item | Mode | Preferred path | Alternate | Status | Blocker | Gate |
|---|---|---|---|---|---|---|
| J3400 inlet | BUY | Phoenix Contact 300-A CHARX as current benchmark | verified J3400/2 Alibaba supplier later | **CARRY benchmark** | final body location/exact supplier | 12-V lock, manual release, temp sensing, serviceable |
| EVCC | BUY / integrate | **MIDA GQEVPLC-V3.4-class** | alternate ISO15118/HPGP controller | **CARRY** | exact J3400 revision/CAN/interoperability | local config/reflash; charging communication only |
| OBC | BUY | **Dilong 6.6-kW family** | Ovar / VMAX-class alternate | **CARRY supplier path** | pack window/AC target/CAN docs | J3400 controller remains separate role |
| HV→12-V DC/DC | BUY | Dilong integrated 14-V unit | 3-kW VMAX-class benchmark/alternate | **OPEN 1.5 vs 3 kW** | 12-V worst-case load budget | enough EPS/brake/thermal transient margin |
| Integrated PDU option | BUY only if transparent | Dilong 3-in-1 | separate VolksMule BDU/PDU | **SKEPTICAL / OPEN** | topology/docs/serviceability | reject black-box PDU |
| DC fast-charge branch | DESIGN + BUY safety hardware | BDU/PDU contactors/fuse/sensing | — | **DESIGN** | pack/current/J3400 system | OBC not in DC power path |
| V2L inverter | BUY | **Rawsuns RDA350-120-3KW** | Bel 350INV60 benchmark | **CARRY pending rating confirmation** | 3-kW spec discrepancy / thermal/EMC docs | 120-V safety, no cloud permission |
| Future V2H/V2G | LATER | standards-compliant bidirectional system | — | **NOT P1 BLOCKER** | standards/grid integration | separate from simple V2L |

---

# 10. Thermal / HVAC

| Item | Mode | Preferred path | Alternate | Status | Blocker | Gate |
|---|---|---|---|---|---|---|
| HV compressor | BUY | **Aotecar E-series** | other automotive 400-V compressor | **CARRY** | capacity map/refrigerant/CAD/CAN | automotive heat-pump duty |
| Compact thermal module | BUY / ADAPT | Aotecar ~300×400×275-mm module as benchmark | modular separate valves/pumps/chiller | **CARRY benchmark** | schematics/serviceability | no inseparable thermal octopus |
| Battery cooler/chiller | BUY | Aotecar-class / equivalent | separate plate HX | **CARRY** | loop sizing | serviceable fittings |
| HV coolant heater | BUY | **NF/EVLINK-class 3–7-kW** | BorgWarner-class benchmark/local Tier-1 | **CARRY family** | final heat/load/voltage | low-flow/dry-run/overtemp safety |
| Coolant pumps | BUY | common 12-V automotive brushless pumps | Pierburg/Bosch/local equivalent | **GREEN** | flow/pressure model | local replacement, documented PWM/CAN if used |
| Valves | BUY | ordinary automotive 2/3-way valves | local equivalent | **GREEN** | loop design | default/fail-state known |
| Cabin air box | BUY / ADAPT / DESIGN | simple single-zone unit; exact supplier open | compact donor HVAC box | **OPEN** | dash/firewall/windshield geometry | positive defrost/defog, physical controls |
| HVAC control head | BUY / ADAPT | **Hangzhou Guangan mechanical/tactile panel** or standardized rotary controls | donor/simple locally built control panel | **CARRY PHYSICAL ARCHITECTURE** | exact HVAC-box actuators and electrical loads | three real knobs; infotainment not required |
| Airflow mode actuation | BUY / ADAPT | mechanical Bowden/push-pull cable first study | local 12-V position actuator | **CARRY MECHANICAL-FIRST** | HVAC-box lever geometry | defrost remains locally commandable |
| Blower-speed control | BUY | stepped rotary switch + resistor/relay, or dedicated local PWM module | common donor blower hardware | **CARRY** | blower current/efficiency budget | tactile knob; module separately replaceable |
| Radiator/condenser | BUY / ADAPT | common automotive heat exchanger where geometry fits | local radiator custom shop | **OPEN** | thermal model/front package | service access / stone protection |
| Refrigerant lines | BUY/fabricate to spec | automotive hose/fittings | local A/C hose shop | **LOCAL-FIRST** | final layout | common service refrigerant practices |

---

# 11. Low voltage / driver controls

| Item | Mode | Preferred path | Alternate | Status | Blocker | Gate |
|---|---|---|---|---|---|---|
| 12-V battery | BUY LOCAL | common North-American group size | any local equivalent | **LOCAL-FIRST** | load/space | easy roadside replacement |
| Fuse/relay centers | BUY | Daier/Daiertek/Onegol-class passive boxes | Littelfuse/Eaton/local | **CARRY commodity** | circuit count | visible/labeled/serviceable |
| Fuses/relays | BUY | standard ATO/ATC/MINI/MAXI + ISO relays | local parts store | **LOCAL-FIRST** | circuit ratings | no vendor software |
| Sealed LV connectors | BUY | DT/DTM/Superseal-class standardized vocabulary | genuine TE/Deutsch/local distributor | **CARRY architecture** | cavity/current assignment | terminals/crimp/seals specified |
| Harness | DESIGN + BUY manufacture | Chinese IATF harness shop after drawings exist | local harness shop | **DESIGN KNOWLEDGE / BUY BUILD** | complete schematics | harness knowledge remains open/documented |
| Accelerator pedal | BUY | **Wayou/Jieou dual-channel Hall pedal** | donor/common electronic pedal | **CARRY supplier path** | signal/geometry/VCU interface | redundant channels/fault → zero torque |
| Drive selector | BUY | Wayou/Jieou physical rotary/lever P-R-N-D | donor/common switch | **CARRY physical path** | state-machine/interface | physical tactile control |
| Ignition/key | BUY / ADAPT | common IATF/OEM-style keyed switch | donor/common lock cylinder | **CARRY KEY baseline** | column/dash packaging | OFF/ACC/RUN; no phone/cloud requirement |
| Hazard/light/wiper stalks | DONOR / BUY | common automotive switch family | local donor | **OPEN** | steering column/dashboard geometry | physical, documented signals |
| HVAC knobs | BUY / DESIGN HMI | Hangzhou Guangan mechanical/tactile control path; standard rotary shafts | donor/simple switches/potentiometers | **CARRY PHYSICAL** | dashboard/HVAC-box geometry | fan/mode/temp + physical defrost; no touch-only path |
| Instrument cluster | BUY / ADAPT | Wuhan Green Electronic-class simple CAN cluster | donor/custom simple cluster | **OPEN** | signals/telltales/FM VSS 101 layout | independent of infotainment boot |
| Horn | BUY | ordinary waterproof 12-V horn | Hella/FIAMM/Denso local | **LOCAL-FIRST** | none meaningful | simple relay/two-wire service |
| Washer pump | BUY | common OEM-fitment pump via Qeepei/Lianzheng etc. | local common pump | **LOCAL-FIRST** | reservoir/windshield | no unique interface |
| Wiper motor/linkage | BUY / ADAPT | **Zhejiang Jixiang-class 12-V motor + conventional linkage**; Xiamen Kction alternate | common donor assembly | **CARRY supplier category / geometry open** | selected windshield/cowl wipe geometry | physical stalk, self-park, complete required wipe area |

---

# 12. Body visibility / lighting

| Item | Mode | Preferred path | Alternate | Status | Blocker | Gate |
|---|---|---|---|---|---|---|
| Windshield | BUY / ADAPT body | carry CR-V FW02294, Nissan FW02510, CR-V FW02023 geometries | whichever common glass wins CAD | **OPEN, 3-family study** | body/A-pillar/cowl/wiper CAD | AS1, replacement depth, good visibility |
| Movable door glass | BUY / custom to drawing | **Fuyao / Xinyi road-intent benchmark; qualified custom tempered glass** | local automotive glass | **CARRY strategy / geometry open** | door/regulator/channel geometry | FMVSS 205 location evidence; drawing belongs to project |
| Quarter / fixed side glass | BUY to drawing | qualified custom tempered automotive glass manufacturer | local specialist | **CARRY custom strategy** | body opening/curvature | multiple-source reproducibility |
| Rear backlite | BUY / custom | Fuyao/SYP/qualified heated backlite supplier | local auto glass | **CARRY SIMPLE HEATED STRATEGY** | rear closure geometry / heater load | simple two-terminal heater; physical switch/relay |
| Headlamps | BUY complete optics | standardized compliant module | donor/common sealed optical unit | **OPEN** | front styling/height/beam package | complete compliant optic, not random LED bulb |
| Tail/turn/brake lamps | BUY complete module | common compliant lamp modules | local trailer/automotive compliant hardware if suitable | **OPEN** | body geometry | required photometry/markings |
| Mirrors | BUY | conventional simple mirror assemblies | donor/local | **OPEN** | door/A-pillar geometry | natural visibility first; no camera-only need |
| Rear camera | BUY | dedicated automotive camera/display path | supplier module/local | **CARRY** | display/placement | image within required timing; independent of infotainment |

---

# 13. Seats / restraints

| Item | Mode | Preferred path | Alternate | Status | Blocker | Gate |
|---|---|---|---|---|---|---|
| Manual seat frame | BUY / ADAPT | **Suzhou Chuangtou** automotive manual frame/mechanism family | donor/common road seat | **CARRY supplier family / exact frame open** | floor/H-point/restraint integration | manual, head restraint, crash/load evidence |
| Seat tracks | BUY | qualified automotive manual dual-rail slides; Chuangtou-class | donor/common | **CARRY MANUAL ARCHITECTURE** | floor/frame choice | documented crash/pull-out/cycle strength |
| Manual recliner | BUY | qualified automotive manual recliner mechanism | donor/common | **CARRY MANUAL ARCHITECTURE** | frame/back geometry | documented torque/crash/cycle capacity |
| Foam / trim | BUY to drawing | simple durable cloth/vinyl + molded foam | local upholstery | **OPEN** | final seat frame/H-point | flammability/airbag/belt fit as applicable |
| Belts/pretensioners | SYSTEM | **Songyuan Safety** integrated path | Jinheng alternate | **SYSTEM** | body/seat/crash development | FMVSS 209/210/etc as applicable |
| Airbags | SYSTEM | Songyuan/Jinheng integrated system | qualified restraint supplier | **SYSTEM** | crash structure/occupant model | never generic/mixed inflators |
| Restraint ECU/sensors | SYSTEM | same integrated supplier | same | **SYSTEM** | full vehicle crash architecture | one coherent validated system |
| Child tether anchorage | DESIGN + hardware | body-integrated anchorage | — | **REQUIRED DESIGN ITEM** | seat/body geometry | two-seat FMVSS 225 implications tracked |

---

# 14. Safety automation

| Item | Mode | Preferred path | Alternate | Status | Blocker | Gate |
|---|---|---|---|---|---|---|
| TPMS | BUY | Baolong-class automotive system | common aftermarket/OEM supplier | **CARRY family** | wheel/valve/cluster interface | regulated performance/low-battery diagnostics |
| AVAS/pedestrian sound | BUY | TEMB-class dedicated EV sounder | qualified alternate | **OPEN** | regulatory implementation/state machine | dedicated appliance, not infotainment |
| AEB/forward sensing | SYSTEM | Freetech-class automotive safety supplier | other Tier-1 | **SYSTEM** | brake/ESC/vehicle geometry | dedicated safety function only |
| Yaw/lateral sensor | SYSTEM | compatible ESC-family sensor | donor/coherent supplier | **OPEN** | ESC selection | calibrated chassis input |
| Rear visibility | BUY / SYSTEM | dedicated camera/display | local automotive system | **CARRY** | body/display | not dependent on consumer OS/cloud |
| Seat-belt reminders | BUY / DESIGN logic | local sensor/telltale integrated with restraint/cluster | — | **OPEN** | final regulation implementation | dedicated telltales/chime path |

---

# 15. Software / controllers / diagnostics

| Item | Mode | Preferred path | Alternate | Status | Blocker | Gate |
|---|---|---|---|---|---|---|
| VCU | DESIGN / controlled platform | EVPT-class supplier only if interface sovereignty clears | open/owned controller platform | **OPEN / sovereignty item** | exact I/O/state machines | local source/config/recovery; no vendor cloud ownership |
| CAN/CAN-FD backbone | DESIGN | standard transceivers/connectors/harness | — | **DESIGN** | ECU selection | documented message ownership/gateway boundaries |
| Diagnostic connector | BUY | standard service connector | local | **CARRY** | protocol choices | accessible without subscription |
| Infotainment | BUY / OPTIONAL | commodity computer/display | phone/tablet/simple head unit | **NON-SAFETY** | user experience later | isolated from safety-critical authority |
| Firmware recovery | DESIGN REQUIREMENT | per-ECU local methods | — | **MANDATORY GATE** | supplier docs | offline backup/reflash/replacement path |

---

# 16. Utility / roadside / owner use

| Item | Mode | Preferred path | Alternate | Status | Blocker | Gate |
|---|---|---|---|---|---|---|
| 120-V outlet | BUY + DESIGN protection | conventional receptacle/GFCI appropriate to inverter topology | local electrical hardware | **OPEN** | inverter neutral/ground topology | shock/ground-fault/weather protection |
| Cargo track / movable tie-downs | BUY + DESIGN mounting | **Ningbo Reach L-track first study**; standard single-stud fittings | local/common L-track ecosystem | **CARRY OPEN INTERFACE** | floor crossmember/load path | vehicle rating includes track → fastener → reinforcement → body |
| Fixed heavy cargo anchors | BUY + DESIGN mounting | conventional forged/recessed D-rings | local truck/cargo hardware | **OPEN** | specific heavy-load locations | whole load path validated |
| Tool storage | DESIGN / fabricate | simple boxes/trays + L-track mounting | local | **OPEN** | interior package | accessible, no powered mechanisms needed |
| Sleeping/work platform | DESIGN | flat cargo structure/panels | local | **DESIGN** | seats/cargo geometry | ~6-ft practical surface target; track does not ruin flat floor |
| Roof-rack mounts | DESIGN + BUY hardware | documented reinforced threaded hard points; common crossbars later | local | **DESIGN / OPEN LOAD** | roof/crash/airbag structure | project-owned coordinates/load limits/sealing |
| Spare retention | BUY / DESIGN mounting | structural internal track/strap or common underbody winch after location study | local | **OPEN** | final spare location | full-size spare cannot become crash projectile |
| Grab handles | BUY / ADAPT | simple conventional donor/Alibaba handle | local | **CARRY COMMODITY** | occupant ergonomics / reinforcement | trim is not structural load path |

---

# 17. Supplier-contact maturity column

Supplier outreach is **deferred**.

Use these readiness levels later:

- **R0 — research only:** still determining what VolksMule wants.
- **R1 — requirement mature:** exact questions and envelope are known.
- **R2 — supplier docs needed:** public information exhausted; ready to request CAD/DBC/application data.
- **R3 — sample candidate:** docs fit architecture; sample is justified.
- **R4 — prototype integrated:** bench/vehicle validation underway.
- **R5 — BOM candidate:** validated enough to carry as preferred part with alternate.

Current examples:

- READ2982: **R2 eventually**, but contact remains intentionally deferred until the broader vehicle requirement package is mature.
- REPT 171-Ah: **R2 eventually** for detailed application spec.
- Daier-style fuse box: **R1/R3 category** once circuit count exists; no engineering outreach needed.
- horn / washer pump / ordinary fuses: usually **R3 by local/commodity purchase**, no supplier relationship necessary.
- manual window regulator / L-track / common seals: **R1 category**, with exact SKU/profile waiting on body CAD rather than supplier discovery.

---

# 18. No-orphan-parts rule

Every future exact part number must answer:

1. Where can another one be bought?
2. Is there a second supplier or substitutable interface?
3. What drawing/specification defines the interface?
4. What happens if the original vendor disappears?
5. Can a competent owner diagnose the failure?
6. Can the component be replaced without cloud/VIN authorization?
7. Does replacing it require redesigning adjacent systems?

A spectacular part that fails those questions may be worse than a boring part that survives them.

---

# 19. Current high-impact unresolved engineering dependencies

These are now more important than finding additional sellers:

1. first integrated vehicle packaging CAD;
2. actual front/rear suspension hard points;
3. READ2982 output/mount CAD;
4. hub spline / bolt pattern / wheel-end choice;
5. axle loads and CG;
6. brake hydraulic/thermal calculations;
7. REPT 171-Ah detailed power/compression/thermal data;
8. pack current/fault architecture;
9. exact 12-V load budget;
10. simple cabin HVAC-box geometry;
11. restraint/crash integration;
12. final windshield/body geometry;
13. door / hatch geometry sufficient to freeze regulators, seals and side/rear glass;
14. underbody impact/load-path analysis before skid thickness/attachments freeze;
15. cargo/roof structural loads before final anchor ratings.

The sourcing mission continues around these dependencies without pretending they are already solved.

---

# 20. Phase-8 working verdict

The sourcing BOM now includes both the major power/chassis systems and the supposedly-small service parts that often create long-term ownership misery.

Prototype 1 continues to divide cleanly into:

- **VolksMule-designed geometry and interfaces**;
- **proven automotive systems requiring supplier integration/calibration**;
- **mass-produced commodity hardware**;
- **local replacement parts**;
- **a relatively small set of supplier-original-data blockers.**

Recent roadmap sourcing has materially narrowed:

- body-service mechanisms;
- manual seat hardware;
- seals / glass channels / grommets;
- cargo restraint interfaces;
- tactile HVAC controls;
- layered underbody protection;
- reproducible side/rear glazing.

The next sourcing work should continue updating this document rather than create disconnected shopping lists.

For every new candidate:

> **Does it fit the requirement, preserve the interface, remain serviceable, and improve the whole vehicle?**

If yes, it earns a place in the BOM study.

If not, Alibaba can keep it.
