# Discrete Audio Control System

An automatic audio sequencer built **without any integrated circuits**. It watches the amplitude and cycle count of a high-voltage AC input and uses only discrete transistors, diodes, resistors and capacitors to switch two audio oscillators on and off. After 30 input cycles it shuts everything down. Designed and simulated in Proteus, with the schematic and PCB layout in Altium.

## What it does

| Input condition | Result |
|---|---|
| Input amplitude passes 40 V and 80 V | Threshold stages switch (voltage-divider sensing) |
| Counter below 4 (counts 0 to 3) | Speaker 1 plays, a 330 Hz tone |
| Counter 4 and above | Speaker 2 takes over, a 2.5 kHz tone |
| Counter reaches 30 (binary 11110) | Master kill latch stops the clock and everything shuts down |

## Prototypes

The project started with small test circuits in Proteus, used to check the transistor building blocks before the full system:

- `proteus/prototypes/led-circuit-discrete.pdsprj`: an LED circuit built from discrete transistors only.
- `proteus/prototypes/led-circuit-with-ic.pdsprj`: a version using an IC, used as a reference to compare against when debugging the transistor logic.

Open them in Proteus 8.17 or newer.

## Tech

Proteus VSM, discrete BJTs, 1N4148 diodes.
