# NEMA Step Motor Control Study

## Day 1 — Hardware Setup

### Goal
Connect a NEMA 17 stepper motor to a TB6600 microstep driver
and control the driver using an Arduino Mega.

## Wiring

```text
Arduino Mega                    TB6600
────────────                    ──────

5V ───────────────────────────→ PUL+
 │
 └────────────────────────────→ DIR+

D2 ───────────────────────────→ PUL−
D3 ───────────────────────────→ DIR−

                                ENA+  not connected
                                ENA−  not connected


TB6600                          NEMA 17
──────                          ───────

A+ ───────────────────────────→ Black
A− ───────────────────────────→ Green
B+ ───────────────────────────→ Red
B− ───────────────────────────→ Blue


24V Power Supply               TB6600
────────────────               ──────

+24V ─────────────────────────→ VCC
0V / − ───────────────────────→ GND
```

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
