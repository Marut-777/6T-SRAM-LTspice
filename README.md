# 🧠 6T SRAM Cell Design and Simulation using LTspice

## 📌 Project Overview

This project presents the design, implementation, and simulation of a **6-Transistor (6T) Static Random Access Memory (SRAM) Cell** using **LTspice**. The objective is to understand the fundamental operation of SRAM memory cells by performing transient simulations of the four basic memory operations:

- Hold Operation
- Write '1' Operation
- Write '0' Operation
- Read Operation

Additionally, a fifth experiment investigates the **effect of bit-line capacitance on the read operation**, providing insight into the influence of parasitic capacitance on SRAM performance.

---

## 🎯 Objectives

- Design a transistor-level 6T SRAM cell.
- Verify the functionality of Hold, Write, and Read operations.
- Simulate the SRAM cell using LTspice.
- Analyze the effect of bit-line capacitance on read performance.
- Understand the working principles of CMOS-based memory cells.

---

## 🛠 Software Used

- **LTspice XVII**
- CMOS Level-1 MOSFET Models
- Windows 11

---

## 🏗 6T SRAM Cell Architecture

A conventional 6T SRAM cell consists of:

- 2 Cross-Coupled CMOS Inverters
- 2 Access NMOS Transistors
- 2 Bit Lines (BL & BLB)
- 1 Word Line (WL)

The cross-coupled inverters store one bit of information, while the access transistors connect the cell to the bit lines during read and write operations.

---

## 📂 Repository Structure

```
6T-SRAM-LTspice/
│
├── README.md
├── 6T_SRAM_Cell_Design_and_Simulation_using_LTspice.pdf
├── LICENSE
│
├── LTspice_Files/
│   ├── SRAM_6T_HOLD.asc
│   ├── SRAM_6T_WRITE1.asc
│   ├── SRAM_6T_WRITE0.asc
│   ├── SRAM_6T_READ.asc
│   └── SRAM_6T_READ_CAP.asc
│
├── Schematics/
│   └── 6T_SRAM_Final_Schematic.png
│
└── Waveforms/
    ├── Hold.png
    ├── Write1.png
    ├── Write0.png
    ├── Read.png
    └── Read_with_Capacitance.png
```

---

# 🧪 Experiments Performed

## ✅ Experiment 1 – Hold Operation

**Objective**

Verify that the SRAM cell retains the stored data when the word line is LOW.

**Observation**

- Word Line remained LOW.
- The stored values of Q and QB remained unchanged throughout the simulation.

**Result**

✔ Successful Hold Operation.

---

## ✅ Experiment 2 – Write '1' Operation

**Objective**

Write logic '1' into the SRAM cell.

**Observation**

- BL = 1 V
- BLB = 0 V
- WL asserted HIGH.

The stored node switched successfully to:

Q = 1

QB = 0

**Result**

✔ Successful Write '1'.

---

## ✅ Experiment 3 – Write '0' Operation

**Objective**

Write logic '0' into the SRAM cell.

**Observation**

- BL = 0 V
- BLB = 1 V
- WL asserted HIGH.

The stored node changed to:

Q = 0

QB = 1

**Result**

✔ Successful Write '0'.

---

## ✅ Experiment 4 – Read Operation

**Objective**

Read the stored data without disturbing the memory content.

**Observation**

- Both bit lines were precharged.
- WL asserted HIGH.
- Stored data remained unchanged.

**Result**

✔ Non-destructive Read Operation verified.

---

## ✅ Experiment 5 – Read Operation with Bit-Line Capacitance

**Objective**

Study the effect of bit-line capacitance on SRAM read behavior.

**Method**

Bit-line capacitors were connected between:

- BL and Ground
- BLB and Ground

The discharge and recharge characteristics were observed during the read cycle.

**Observation**

- BLB discharged through the access transistor during read.
- After WL became LOW, BLB recharged through the precharge resistor.
- The RC charging/discharging effect was clearly observed.

**Result**

✔ Successful demonstration of the effect of bit-line capacitance on SRAM read performance.

---

# 📊 Key Results

| Experiment | Status |
|------------|--------|
| Hold Operation | ✅ Passed |
| Write '1' | ✅ Passed |
| Write '0' | ✅ Passed |
| Read Operation | ✅ Passed |
| Read with Bit-Line Capacitance | ✅ Passed |

---

# 📚 Key Concepts Learned

- CMOS Inverter Operation
- Cross-Coupled Latch
- Static Random Access Memory (SRAM)
- Hold Stability
- Read and Write Operations
- Word Line (WL)
- Bit Lines (BL & BLB)
- Access Transistors
- Parasitic Bit-Line Capacitance
- RC Charging and Discharging
- Transient Analysis using LTspice

---

# 🚀 Future Improvements

Possible extensions of this work include:

- Static Noise Margin (SNM) Analysis
- Write Margin Analysis
- Power Consumption Analysis
- Delay Analysis
- Monte Carlo Simulation
- Layout Design using KLayout
- SRAM Sense Amplifier Design

---

# 📖 References

1. Neil H. E. Weste and David Harris, *CMOS VLSI Design: A Circuits and Systems Perspective*.
2. Jan M. Rabaey, *Digital Integrated Circuits*.
3. LTspice XVII Documentation.
4. CMOS SRAM Design Literature.

---

# 👨‍💻 Author

**Marut Mahija Roy**

M.Tech – Semiconductor Materials and Devices (SMD)

Indian Institute of Technology Hyderabad

---

## ⭐ If you found this project useful, consider giving this repository a star!
