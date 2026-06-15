# INDUCTION-HEATER
# Induction Heater Driver (Royer / Mazzilli ZVS Push-Pull)

A self-oscillating push-pull resonant converter (Royer/Mazzilli-type oscillator) designed to drive an induction heating coil. The circuit uses a cross-coupled MOSFET gate-drive feedback network with a resonant LC tank to generate a high-frequency oscillating magnetic field.

## ⚠️ Safety Warning

This circuit operates at **high currents and voltages**, generates **strong magnetic fields**, and the MOSFETs/coil can get **extremely hot** during operation. The resonant capacitor bank can **store dangerous charge** even after power is disconnected.



## Overview

| Parameter            | Value                          |
|----------------------|--------------------------------|
| Topology             | Self-oscillating push-pull (Royer/ZVS) |
| MOSFETs              | IRFP4668PBF (x2)               |
| Primary Inductors    | L1, L2 — 100µH, 15A rated      |
| Resonant Tank Caps   | 10 × 470nF (4.7µF total)       |
| Output               | Coil1 / Coil2 (work coil)      |
| Input                | +VDC (high-current supply)     |

## Circuit Description

- **L1/L2 (100µH, center-tapped):** Feed the supply rail to the drains of Q1/Q2, acting as the choke for the push-pull stage.
- **Q1/Q2 (IRFP4668PBF):** Power MOSFET switching pair, alternately conducting to drive the resonant tank.
- **Cross-coupled gate feedback (D3/D4, R2/R5, C11/C12):** Provides positive feedback that sustains oscillation once started.
- **Zener gate clamps (D1/D2, 12V):** Protect MOSFET gates from overvoltage.
- **R8/R9 (18Ω):** Gate drive resistors controlling switching speed.
- **R1/R4 (47Ω, 5W):** Startup bias resistors that initiate oscillation.
- **C1–C10 (470nF each):** Resonant tank capacitor bank, parallel with the work coil (Coil1/Coil2).
- **D8 (SB5H100):** Input protection/rectifier diode.
- **D5 + R7:** Power-on indicator LED.


  IM DESINGED WITH EASYIDE

