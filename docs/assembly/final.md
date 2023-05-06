---
title: 8. Final Notes
summary: Notes on wiring and finishing up.
authors: Jon Harper
date: 2023-4-8
---

## X Endstop Wiring

<figure markdown>
![Horizontal limit switch](../img/bom_endstop.png)
<figcaption>
Example of a mechanical limit switch from the BOM.
</figcaption>
</figure>

### Overview

Mechanical limit switch PCBs (as above) have a 3-pin JST-XH connector with the following pins:

1. Common (C)
2. Normally Open (NO)
3. Normally Closed (NC).

![MCU endstop wire order example](../img/endstop.png){width="100px" align="right"}

MCU boards *also* have a 3-pin JST-XH connector for endstops, but they are typically wired as seen in the graphic at right:

1. +5V
2. GND
3. SIG (pin 1.29 in the illustration)

### Wiring the Endstop

Although both sides have a 3-pin connector, the endstop connection only needs two (2) wires. Unfortunately, limit switch PCBs are often sold with a *3-wire* cable. This is hazardous if the +5V pin is connected to the endstop, and may start a fire.

!!! warning
    Never connect the board's +5V pin to a mechanical endstop.

Your limit switch should be wired this way:

| Switch Pin | Board Pin |
|---|---|
| C | SIG |
| NC | GND |