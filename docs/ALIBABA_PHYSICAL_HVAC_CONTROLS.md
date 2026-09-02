# Alibaba physical HVAC controls — knobs, cables, blower switch and local actuation

Research current as of **2026-09-01**.

This document continues the VolksMule roadmap sourcing mission into the driver-facing HVAC command path.

The thermal system may contain sophisticated power electronics because heat pumps and battery conditioning require them. That does **not** mean the driver must operate basic climate functions through a touchscreen or general-purpose computer.

> **The thermal controller may manage thermodynamics. The driver still gets real knobs.**

---

## 1. Prototype-1 HVAC command baseline

Carry three primary physical controls:

1. **blower speed** — rotary knob/switch;
2. **airflow mode** — rotary knob/lever selecting face / floor / defrost combinations;
3. **temperature demand** — rotary knob.

Also provide dedicated physical commands for:

- A/C enable where useful;
- recirculation/fresh air;
- **MAX DEFROST / windshield clearing**;
- rear defog if a heated rear window is used.

None of these basic commands may require:

- infotainment boot;
- phone;
- internet/cloud;
- touch-only menus.

---

# 2. Mechanical HVAC control panel — strongest current sourcing direction

## Hangzhou Guangan Automobile Electric

Alibaba currently exposes **Hangzhou Guangan Automobile Electric Co., Ltd.** as a long-running automotive HVAC-controls manufacturer with product categories including:

- automotive air-conditioning controllers;
- speed-regulating modules;
- vehicle temperature manipulators;
- electronic HVAC panels;
- importantly, **automobile mechanical HVAC control panels / air-conditioner switches**.

That last product class is particularly attractive because it proves the supplier ecosystem still supports tactile/mechanical command hardware rather than forcing a large display or CAN-only panel.

### Current verdict

> **STRONG YELLOW-GREEN supplier path for a simple physical HVAC control head.**

Final viability depends on whether the exact panel can be supplied with open/simple electrical contacts and/or cable outputs appropriate to the chosen HVAC box.

---

# 3. Blower-speed control

## Baseline A — discrete stepped blower switch

Alibaba has abundant 12/24-V automotive 4-position / 3-speed blower switches.

Typical architecture:

- OFF;
- LOW;
- MEDIUM;
- HIGH.

Current listings show ordinary rotary automotive fan switches and replaceable resistor packs at very low cost.

### Why this is attractive

A stepped system provides:

- tactile detents;
- easy diagnosis with a meter;
- inexpensive switch replacement;
- inexpensive resistor/module replacement;
- no software needed to make the cabin fan run.

### Electrical caution

Do not run an unnecessarily large blower current directly through a dashboard switch if relay/module architecture is cleaner.

The knob can command:

- relay/resistor stages; or
- a dedicated local blower power module.

The important point is that the driver command remains simple and the power module remains independently replaceable.

### Current verdict

> **STEPPED PHYSICAL BLOWER KNOB IS THE PROTOTYPE-1 BASELINE.**

---

# 4. Blower resistor / power module

Alibaba has extremely deep automotive blower-resistor inventory from established replacement-part manufacturers including Ningbo Anchor, Ningbo Bowente and others.

A conventional resistor pack is wonderfully simple but wastes more power at lower speeds.

A solid-state blower module can be more efficient, especially in an EV, but should remain:

- dedicated to the blower;
- locally controlled;
- replaceable;
- documented;
- independent of infotainment.

### Selection rule

Compare two options after blower-motor power is known:

1. **simple resistor/relay stages** if heat loss is acceptable;
2. **dedicated PWM blower module** if the energy saving is meaningful.

Either option still uses a tactile driver knob.

### Verdict

> **OPEN RESISTOR VS LOCAL PWM MODULE; SCREEN/GENERAL COMPUTER NOT INVOLVED.**

---

# 5. Airflow-mode door actuation

## Preferred baseline — mechanical Bowden / push-pull cable

Automotive push-pull control cables are widely available on Alibaba from manufacturers such as Dongguan Guofeng, Hebei Junxiang and other dedicated cable makers.

Current listings also include actual heater-control cables for existing vehicles.

If the selected HVAC box supports it, a mechanical cable from the mode knob to a blend/distribution door has major advantages:

- visible/direct state;
- no calibration sequence;
- no gearmotor failure;
- easy field repair;
- no ECU dependency;
- door remains where the knob puts it.

### Requirements

Need:

- low-friction cable;
- sufficient bend radius;
- robust anchored sheath ends;
- corrosion-resistant inner wire;
- positive end stops;
- replaceable cable;
- mode-door torque low enough for comfortable knob force.

### Verdict

> **MECHANICAL MODE CABLE FIRST STUDY.**

---

# 6. Electric blend-door actuator — fallback, not enemy

Some packaging architectures may make direct cable actuation awkward.

Alibaba has a large automotive 12-V blend-door actuator ecosystem, including suppliers that specialize in HVAC flap servos and feedback actuators.

**Zhengzhou Newbase** and **Wuhan Longling** are current examples of Chinese manufacturers focused on automotive/bus HVAC actuators and fan-speed electronics.

An electric actuator is acceptable if it genuinely simplifies duct/door packaging.

### If used, require

- local dedicated controller or simple position command;
- explicit position feedback;
- manual/default safe defrost position where practical;
- no CAN-only closed protocol unless documented;
- replacement without dashboard destruction;
- recalibration procedure available offline.

### Verdict

> **YELLOW FALLBACK. Use only where mechanical cable routing loses the whole-system comparison.**

---

# 7. Temperature knob

The heat-pump/battery thermal system makes temperature control more complicated than a 1990s heater valve.

The **driver interface still need not be complicated**.

The temperature knob can provide a simple local demand signal such as:

- potentiometer voltage;
- discrete stepped command;
- cable position if a coolant/air door is used.

A dedicated HVAC/thermal controller may then decide:

- compressor speed;
- coolant-valve position;
- PTC backup heat;
- chiller routing;
- battery priority limits.

### Authority boundary

The dedicated thermal controller may optimize the method.

It must not remove the driver's direct ability to request:

- warmer;
- colder;
- windshield defrost.

### Verdict

> **PHYSICAL ROTARY DEMAND KNOB + SMALL DEDICATED THERMAL CONTROL LAYER.**

---

# 8. MAX DEFROST

Windshield clearing is safety equipment, not a comfort menu.

Prototype 1 should have a dedicated physical defrost command that requests a known high-priority state:

- airflow directed to windshield;
- adequate blower speed;
- compressor/dehumidification as appropriate;
- available heat/PTC support;
- recirculation state chosen for clearing performance;
- heated windshield/rear-glass function if installed.

If one actuator or controller fails, the system should fail toward a serviceable/diagnosable state rather than silently showing a software animation while the glass remains fogged.

### Hard rule

> **Defrost cannot depend on the infotainment computer.**

---

# 9. Recirculation control

Recirculation can be:

- mechanical lever/cable; or
- one simple 12-V actuator with physical pushbutton/switch.

A local electrical actuator may be reasonable because the recirc door is often remote and lightly loaded.

If powered, it still does not need a body computer.

### Verdict

> **MECHANICAL IF EASY; SIMPLE LOCAL ACTUATOR ACCEPTABLE.**

---

# 10. Knobs and switchgear

The dashboard control head should be designed around replaceable switches, not molded around one supplier's decorative faceplate.

Desired qualities:

- large enough for gloves;
- clear detents;
- mechanically keyed shaft/interface;
- replaceable knob cap;
- printed/engraved permanent legends;
- dim backlighting optional;
- no capacitive touch surface;
- no piano-black requirement.

Alibaba is overflowing with generic rotary switches and knobs, but final automotive controls need appropriate life, temperature, vibration and current ratings.

The control face/knobs themselves can be locally molded/printed/machined around standardized switch shafts if that improves long-term serviceability.

---

# 11. Supplier shortlist

| Function | Current first path | Mode | Gate |
|---|---|---|---|
| Mechanical/tactile HVAC control head | Hangzhou Guangan | BUY / ADAPT | exact open electrical/cable interfaces |
| Simple 12-V temperature knob/controller | Ningbo Bowente-class | BUY / benchmark | thermal-controller interface |
| Blower rotary switch | automotive 12/24-V 4-position family | BUY | current/cycle/environment rating |
| Blower resistor | common automotive resistor pack | BUY | blower current/airflow cooling |
| Efficient blower control alternate | dedicated automotive PWM module | BUY | efficiency benefit + open control |
| Mode-door cable | Dongguan Guofeng / Junxiang-class push-pull cable | BUY to length | HVAC-box lever geometry |
| Mode actuator fallback | Zhengzhou Newbase / Wuhan Longling-class | BUY | position feedback/open/local control |
| Recirc actuation | cable or simple local 12-V actuator | BUY | HVAC-box geometry |
| Knobs/faceplate | standard shafts + local/Alibaba molded hardware | DESIGN INTERFACE + BUY/FABRICATE | final dashboard layout |

---

# 12. What not to buy

Reject as Prototype-1 baseline:

- touchscreen-only HVAC panel;
- Android climate-control screen;
- proprietary CAN control head with undocumented messages;
- multi-zone luxury HVAC panel for a two-seat cabin;
- capacitive sliders for fan/temperature;
- blend actuators that require dealer calibration/cloud tools;
- integrated infotainment/HVAC computer whose failure disables defrost.

---

# 13. Current architecture recommendation

The first Mule should study an intentionally old-fashioned-looking driver interface over a modern thermal plant:

> **Knob 1: fan. Knob 2: where the air goes. Knob 3: hotter/colder. Physical buttons/switches for A/C, recirc and DEFROST.**

Behind that panel, a dedicated thermal controller can orchestrate the heat pump, coolant heater, valves and battery-conditioning priorities.

This gives us the efficiency of a modern EV thermal system without giving a touchscreen ownership of the windshield.

---

## Sources reviewed

Public research current as of **2026-09-01**:

- current Alibaba Hangzhou Guangan automotive HVAC controller / mechanical HVAC panel listings;
- current Alibaba Ningbo Bowente automotive A/C control hardware;
- current Alibaba universal automotive 12/24-V blower rotary switches;
- current Alibaba blower-resistor and blower power-module catalogs;
- current Alibaba automotive push-pull control cable manufacturers and heater-control-cable listings;
- current Zhengzhou Newbase and Wuhan Longling automotive HVAC actuator product material.

Exact environmental/cycle/current ratings remain part-specific qualification gates.
