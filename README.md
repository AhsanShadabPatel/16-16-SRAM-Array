# 🧠 16×16 SRAM Memory Array Design using Cadence Virtuoso  
*A high‑speed, low‑power VLSI memory design project*

## 📌 Overview  
This repository contains the design and analysis of a **16×16 Static Random Access Memory (SRAM) array** implemented using the **Cadence Virtuoso** toolset. The project focuses on achieving **low power consumption**, **fast access time**, and **robust read/write performance**, making it suitable for cache memory and embedded SoC applications.

SRAM dominates modern SoC area—often exceeding **70–90%** of total chip space—making efficient memory design essential for performance, cost, and scalability. This project demonstrates a complete SRAM subsystem built from the ground up using a 6T SRAM cell and all required peripheral circuits.

---

## 🚀 Key Features  
- ✔️ **6T SRAM Cell** optimized for stability and density  
- ✔️ **16×16 Memory Array** (256 bits total)  
- ✔️ **4:16 Row Decoder** for word‑line selection  
- ✔️ **Precharge Circuit** for BL/BLB initialization  
- ✔️ **Write Driver** for full‑swing write operations  
- ✔️ **Sense Amplifier** for fast differential readout  
- ✔️ **Hierarchical Cadence Virtuoso design flow**  
- ✔️ **Verified read/write operations through simulation**  

---

## 🧩 System Architecture  

### **1. 6T SRAM Cell**  
- Two cross‑coupled inverters form a latch  
- Two NMOS access transistors controlled by the word line  
- Supports non‑destructive read and stable write operations  
- Transistor sizing optimized for noise margin and stability  

### **2. Precharge Circuit**  
- Precharges BL and BLB to **VDD = 1 V**  
- PMOS device (W = 240 nm) ensures fast charging  
- Disabled during active read/write cycles  

### **3. Write Driver**  
- Discharges one bit line to write data into the cell  
- Controlled by **Write Enable (WE)**  
- Uses stacked NMOS pass‑transistor structure  
- Ensures strong logic “0” write capability  

### **4. Sense Amplifier**  
- Detects small BL–BLB voltage differences  
- Converts differential input to full‑swing digital output  
- Critical for fast and reliable read operations  

### **5. 4:16 Row Decoder**  
- NAND‑based design for area efficiency  
- Inputs: A, B, C, D  
- Outputs: WL1–WL16  
- Activates exactly one word line per address  

### **6. 16×16 Memory Array**  
- 256 SRAM cells arranged in 16 rows × 16 columns  
- Each column includes:  
  - 1 Sense Amplifier  
  - 1 Write Driver  
  - 1 Precharge Circuit  
- Differential readout (Read, ReadBar) for robustness  

---

## 📐 Design Flow  
1. Schematic design of each block in Cadence Virtuoso  
2. Transistor sizing for speed, power, and stability  
3. Symbol creation for hierarchical design  
4. Integration into full 16×16 array  
5. Simulation of:  
   - Read operation  
   - Write operation  
   - Precharge behavior  
   - Decoder activation  
6. Waveform analysis for access time and power  

---

## 📊 Results  
- Successful **read and write operations** verified  
- Low access time achieved due to efficient sensing  
- Reduced power consumption through optimized transistor sizing  
- Stable operation across the full 16×16 array 

---

