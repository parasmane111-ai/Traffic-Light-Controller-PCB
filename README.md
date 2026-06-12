# Traffic Light Controller using 555 Timer, 7490 Counter, 74LS74 and Logic Gates

This project is a **two-way traffic light controller** designed using basic digital electronics ICs.  
The circuit controls the Red, Yellow, and Green signals for two roads, Road A and Road B, in a fixed cyclic sequence.

The main purpose of this project is to understand how **timing, counting, decoding, flip-flop state control, and output logic** can be combined to build a practical digital control system.

---

## Project Overview

In this project, a **555 timer** is used in astable mode to generate continuous clock pulses.  
These clock pulses are applied to a **7490 decade counter**, which is configured as a **MOD-10 counter**.

The MOD-10 counter counts from **0 to 9** and then resets back to 0, creating a repeated timing cycle.  
The output bits of the counter are decoded using logic gates such as **NOT, AND, OR, and XOR gates**.  
These decoded signals are then used with **74LS74 D flip-flops** to control the traffic light states.

Finally, the output logic drives LEDs representing the traffic lights for Road A and Road B.

---

## Working Principle

The working of the circuit can be divided into the following stages:

1. **Clock Generation**

   The 555 timer is configured in astable mode.  
   It produces continuous square wave clock pulses.  
   The timing of these pulses depends on external components such as resistors, capacitors, and diode.

2. **MOD-10 Counting**

   The clock pulses are given to the 7490 counter.  
   The 7490 is configured as a MOD-10 decade counter, so it counts from 0 to 9 repeatedly.  
   This count sequence is used as the timing base for the traffic light operation.

3. **Logic Decoding**

   The counter outputs are connected to logic gates.  
   The combination of 74LS04, 74LS08, 74LS32, and 74LS86 ICs is used to decode specific count conditions.  
   These decoded outputs decide which traffic signal should be ON at a particular state.

4. **State Control**

   The 74LS74 D flip-flop is used for stable state control.  
   It helps in maintaining proper switching between the traffic light states.

5. **Output Indication**

   LEDs are used to represent Red, Yellow, and Green signals for both roads.  
   Current-limiting resistors are connected with LEDs to protect them from excess current.

---

## Traffic Light Sequence

The traffic light controller follows a four-state sequence:

| State | Road A | Road B |
|------|--------|--------|
| S0 | Green | Red |
| S1 | Yellow | Red |
| S2 | Red | Green |
| S3 | Red | Yellow |

After state S3, the sequence returns to S0 and repeats continuously.

---

## Main Components Used

| Component | Purpose |
|----------|---------|
| NE555 Timer | Generates clock pulses in astable mode |
| 7490 Counter | Works as MOD-10 counter for timing sequence |
| 74LS74 D Flip-Flop | Stores and controls logic states |
| 74LS04 NOT Gate | Provides signal inversion |
| 74LS08 AND Gate | Used for logic decoding and gating |
| 74LS32 OR Gate | Combines logic conditions |
| 74LS86 XOR Gate | Used for logic operation and decoding |
| LEDs | Indicate Red, Yellow, and Green signals |
| 220Ω Resistors | Limit LED current |
| R1, R2, C1, C2, D1 | Timing components for 555 timer |

---

## Software and Tools Used

- **Proteus** – Circuit schematic and simulation
- **KiCad** – Schematic design, footprint assignment, PCB layout
- **Digital Logic ICs** – 555, 7490, 74LS74, 74LS04, 74LS08, 74LS32, 74LS86

---

## PCB Design

The PCB layout was designed in KiCad using through-hole components.  
All major ICs and output LEDs are placed in a structured layout for easy understanding and hardware implementation.

Design details:

- 2-layer PCB layout
- Through-hole DIP IC packages
- Separate LED outputs for Road A and Road B
- Current-limiting resistors for each LED
- ERC completed with 0 errors
- Footprints assigned for all components

---

## Folder Structure

```text
Traffic-Light-Controller/
│
├── README.md
│
├── Proteus_Schematic/
│
├── KiCad_PCB/

## Author

Developed by **Paras Mane**  
B.Tech Electronics and Telecommunication Engineering  
Government College of Engineering, Karad  

GitHub: [@parasmane111-ai](https://github.com/parasmane111-ai)
