# Automatic Room Light Controller with Visitor Counter

## Overview

An embedded systems project that automates room lighting based on occupancy while keeping track of the number of people entering and leaving a room.

The system uses two IR sensor modules placed sequentially at the entrance to identify the direction of movement. An ATmega328P microcontroller processes the sensor sequence, updates the visitor count and controls the room lighting accordingly.

A 16×2 LCD displays the current visitor count in real time. The light turns ON when at least one person is present and turns OFF when the room becomes empty.

## Features

- Automatic room lighting based on occupancy.
- Bidirectional visitor counting using two IR sensors.
- Direction detection based on sensor triggering sequences.
- Real-time visitor count display using a 16×2 LCD.
- Automatic light control based on the visitor count.

## Hardware Components

| Component | Quantity |
|---|---:|
| ATmega328P-PU | 1 |
| IR obstacle sensor modules | 2 |
| 16×2 LCD | 1 |
| LM7805 voltage regulator | 1 |
| 16 MHz crystal | 1 |
| 22 pF capacitors | 2 |
| 10 kΩ resistors | 2–3 |
| 220 Ω resistors | 2 |
| 10 kΩ potentiometer | 1 |
| LED | 1–2 |
| Push button | 1 |
| 9V battery and connector | 1 |
| Breadboard, jumper wires and supporting components | As required |

## Working Principle

Two IR sensors, ENTRY and EXIT, are positioned one after another at the doorway.

The sequence in which the sensors are triggered determines the direction of movement:

1. **Entry:** The ENTRY sensor is triggered first, followed by the EXIT sensor. The visitor count is incremented.
2. **Exit:** The EXIT sensor is triggered first, followed by the ENTRY sensor. The visitor count is decremented.

The microcontroller continuously monitors the sensor inputs and updates the visitor count.

The lighting mechanism operates according to the count:

- Visitor count > 0: Light ON.
- Visitor count = 0: Light OFF.

The updated count is displayed on the 16×2 LCD.

## Circuit Design

The circuit is built around the ATmega328P microcontroller.

- Two digital input pins interface with the IR sensor modules.
- The LCD is interfaced with the microcontroller to display the visitor count.
- A 16 MHz crystal oscillator provides the system clock.
- A reset circuit uses a pull-up resistor and push button.
- An LM7805 voltage regulator provides a regulated 5V supply.

**Simulation note:** LogicState components are used in Proteus to represent the IR sensor outputs. An LED represents the room-light switching output in the simulation.

## Simulation and Testing

The circuit was designed and simulated using Proteus.

The simulation was tested under different occupancy conditions:

- Idle condition with zero visitors.
- Entry sensor activation sequence.
- Exit sensor activation sequence.
- Visitor count increment after entry.
- Visitor count decrement after exit.
- Automatic light control based on occupancy.

## Results

The system successfully demonstrated visitor counting through sequential sensor activation and automatic lighting control based on the number of occupants.

The LCD displayed the updated visitor count, while the lighting output responded to changes in occupancy.

## Technologies Used

- **Microcontroller:** ATmega328P
- **Programming:** Embedded C
- **Simulation:** Proteus
- **Hardware:** IR sensors, LCD interfacing, voltage regulation and output switching

## Learning Outcomes

- AVR microcontroller interfacing and embedded C programming.
- IR sensor interfacing and sequential event detection.
- Implementation of visitor counting logic.
- LCD interfacing and display handling.
- Circuit simulation and hardware prototyping.

## Future Improvements

- Improve detection reliability under different lighting conditions.
- Add safeguards against incorrect counts caused by simultaneous or incomplete sensor triggering.
- Integrate wireless monitoring for remote occupancy tracking.
- Extend the system to control multiple lighting zones.

## Project Status

Completed – Circuit simulation and hardware prototype.

