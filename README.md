# latch-light-sensor-control

This repository includes two related electronics projects that share a single lamp output:

## Task 1: Latching Switch

A purely hardware circuit using a push-button and an NPN transistor to toggle a lamp on or off. Once pressed, the circuit latches in its last state until the button is pressed again.

## Task 2: Light & Button Sensor

An Arduino sketch reads an LDR on analog pin A0 and the same push-button on digital pin D2. It drives the lamp through pin D9 and a transistor:

* Press the button → lamp toggles on.
* When ambient light rises above the set threshold → lamp automatically turns off, even if previously on.
* Press again to toggle back.

### Wiring Overview

```
5V ── LDR ──•── 10 kΩ ── GND
             |
            A0

D2 ── Button ── GND (use INPUT_PULLUP)

D9 ── 330 Ω ── Base of NPN transistor
Emitter of transistor ── GND
Collector of transistor ── Lamp ── 5V
```

### Directory Layout

```
latch-light-sensor-control/
├ Task1_LatchingSwitch/   (hardware latch circuit)
├ Task2_LDR_Sensor/       (Arduino code and wiring)
└ README.md
```
