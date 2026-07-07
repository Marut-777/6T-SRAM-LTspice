# 6T SRAM Cell Design and Simulation using LTspice

Design and simulation of a conventional 6-Transistor (6T) Static Random Access Memory (SRAM) cell using LTspice. This project demonstrates the basic operations of an SRAM memory cell through transient simulations and analyzes the effect of bit-line capacitance during the read operation.

---

## Project Overview

This project was developed to understand the working principle of a CMOS 6T SRAM cell. The complete cell was designed in LTspice using CMOS transistor models, and its functionality was verified by performing the following operations:

- Hold Operation
- Write '1' Operation
- Write '0' Operation
- Read Operation
- Read Operation with Bit-Line Capacitance

The project also demonstrates the impact of parasitic bit-line capacitance on SRAM read performance.

---

## SRAM Cell Architecture

The implemented SRAM cell consists of:

- 2 Cross-Coupled CMOS Inverters
- 2 NMOS Access Transistors
- Word Line (WL)
- Bit Line (BL)
- Bit Line Bar (BLB)
- VDD = 1 V

The storage nodes are:

- Q
- QB

---

## LTspice Model Parameters

### NMOS

```
.model CMOSN NMOS (
+ LEVEL=1
+ VTO=0.45
+ KP=200u
+ LAMBDA=0.02
)
```

### PMOS

```
.model CMOSP PMOS (
+ LEVEL=1
+ VTO=-0.45
+ KP=100u
+ LAMBDA=0.02
)
```

---

## Simulation Specifications

| Parameter | Value |
|-----------|-------|
| Simulator | LTspice XVII |
| Supply Voltage | 1 V |
| Analysis | Transient |
| Simulation Time | 100 ns |
| Word Line Pulse | 20 ns |
| Technology | CMOS |

---

# Experiments Performed

## Experiment 1 – Hold Operation

### Objective

Verify that the SRAM cell retains the stored data when the Word Line remains LOW.

### Observation

- WL remains LOW.
- Access transistors remain OFF.
- Q and QB retain their initial values.
- No disturbance is observed.

**Result:** Hold operation verified successfully.

---

## Experiment 2 – Write '1' Operation

### Objective

Store logic '1' inside the SRAM cell.

### Conditions

BL = 1

BLB = 0

WL = Pulse

### Observation

- Access transistors turn ON.
- Internal nodes switch correctly.
- Final state:

Q = 1

QB = 0

**Result:** Write '1' operation verified.

---

## Experiment 3 – Write '0' Operation

### Objective

Store logic '0' inside the SRAM cell.

### Conditions

BL = 0

BLB = 1

WL = Pulse

### Observation

The internal nodes reverse their logic.

Final state:

Q = 0

QB = 1

**Result:** Write '0' operation verified.

---

## Experiment 4 – Read Operation

### Objective

Verify correct reading of stored data.

### Conditions

BL = 1

BLB = 1

WL = Pulse

### Observation

- Stored data is sensed without changing the stored value.
- Q and QB remain stable.

**Result:** Read operation verified.

---

## Experiment 5 – Read Operation with Bit-Line Capacitance

### Objective

Study the effect of parasitic bit-line capacitance during read operation.

### Additional Components

- BL Capacitor
- BLB Capacitor
- Pull-up Resistors

### Observation

- Bit-line voltage changes more slowly.
- Increased RC delay.
- Slower sensing compared to ideal read operation.

**Result:** Successfully demonstrated the influence of bit-line capacitance.

---

# Simulation Results

| Experiment | Status |
|------------|--------|
| Hold | Passed |
| Write '1' | Passed |
| Write '0' | Passed |
| Read | Passed |
| Read with Capacitance | Passed |

---

# Repository Structure

```
6T-SRAM-LTspice/
│
├── README.md
├── 6T_SRAM_Illustrated_Project_Report.pdf
│
├── LTspice_Files/
│   ├── SRAM_6T_HOLD.asc
│   ├── SRAM_6T_WRITE1.asc
│   ├── SRAM_6T_WRITE0.asc
│   ├── SRAM_6T_READ.asc
│   └── SRAM_6T_READ_with_cap.asc
│
├── Images/
│   ├── SRAM_Schematic.png
│   ├── Hold_Waveform.png
│   ├── Write1_Waveform.png
│   ├── Write0_Waveform.png
│   ├── Read_Waveform.png
│   └── Read_with_Capacitance.png
```

---

# How to Run

1. Open LTspice XVII.
2. Open any `.asc` schematic.
3. Click **Run**.
4. Observe the transient waveforms.
5. Compare the node voltages for each experiment.

---

# Future Improvements

- Static Noise Margin (SNM) Analysis
- Read Delay Measurement
- Write Delay Measurement
- Power Consumption Analysis
- Process Variation Analysis
- Monte Carlo Simulation
- Sense Amplifier Design
- SRAM Array Design (4×4 / 8×8)

---

# Author

**Marut Mahija Roy**

M.Tech – Semiconductor Materials and Devices

Indian Institute of Technology Hyderabad

---

# License

This project is released under the MIT License.
