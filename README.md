# NEMA Step Motor Control Study

## Day 1 — Hardware Setup

### Goal
Connect a NEMA 17 stepper motor to a TB6600 microstep driver
and control the driver using an Arduino Mega.

### Wiring

                     ┌─────────────────────┐
                    │    Arduino Mega     │
                    │                     │
                    │   5V ───────┬────────────→ PUL+
                    │             │
                    │             └────────────→ DIR+
                    │
                    │   D2 ────────────────────→ PUL−
                    │
                    │   D3 ────────────────────→ DIR−
                    │
                    │   ENA: not connected
                    └─────────────────────┘


                              │
                              ▼

                    ┌─────────────────────┐
                    │       TB6600        │
                    │                     │
 Arduino 5V ───────→│ PUL+                │
 Arduino D2 ───────→│ PUL−                │
                    │                     │
 Arduino 5V ───────→│ DIR+                │
 Arduino D3 ───────→│ DIR−                │
                    │                     │
       nothing ─────│ ENA+                │
       nothing ─────│ ENA−                │
                    │                     │
                    │ A+ ─────────→ BLACK │
                    │ A− ─────────→ GREEN │
                    │ B+ ─────────→ RED   │
                    │ B− ─────────→ BLUE  │
                    │                     │
                    │ VCC ←── +24V        │
                    │ GND ←── 0V / −      │
                    └─────────────────────┘
                              │
                              │
                    ┌─────────▼───────────┐
                    │      NEMA 17        │
                    │                     │
                    │ Black ─── A+        │
                    │ Green ─── A−        │
                    │ Red   ─── B+        │
                    │ Blue  ─── B−        │
                    └─────────────────────┘


24V POWER SUPPLY:

     +24V ───────────────────→ TB6600 VCC
      0V ────────────────────→ TB6600 GND

## Day 2 — Basic Step and Direction Control

### Goal
Understand how STEP pulses, pulse count, pulse timing,
and DIR control the movement of a stepper motor.

### What I learned

- `DIR` determines the direction of rotation.
- `STEP` sends pulse commands to the motor driver.
- The number of STEP pulses determines the commanded amount of rotation.
- The pulse interval (`step_delay`) determines the motor speed.
- Shorter delay → higher pulse frequency → faster rotation.
- Longer delay → lower pulse frequency → slower rotation.

### Question
How can I precisely control the angle of rotation?
