# FISC‑V Processor

![Build Status](https://img.shields.io/badge/build-passing-brightgreen) ![License](https://img.shields.io/badge/license-MIT-blue) ![Language](https://img.shields.io/badge/language-Verilog-orange)

A lightweight, educational RISC‑V‐compliant CPU core written in Verilog – perfect for FPGA prototyping, SoC integration, and learning computer‑architecture from the ground up.

---

## 🚀 Features

- **ISA Compatibility**  
  Implements the full RV32I base integer instruction set (with Zicsr and Zifence support).

- **5‑Stage Pipeline**  
  - Instruction Fetch (IF)  
  - Instruction Decode & Register Read (ID)  
  - Execute & ALU (EX)  
  - Memory Access (MEM)  
  - Write‑Back (WB)

- **Hazard Management**  
  - Full data‑forwarding unit  
  - Stall logic for load–use hazards  
  - Simple static branch prediction (predict‑not‑taken)

- **Bus Interfaces**  
  - Instruction & data bus (Wishbone)  
  - Optional AXI4‑lite wrapper for AMBA‑based systems

- **Configurable Parameters**  
  - Register‑file size  
  - Endianness (little/big)

- **Toolchain Support**  
  - Works with Verilator for cycle‑accurate simulation  
  - Ready for synthesis on major FPGA families (Xilinx, Intel/Altera)  

---

## 📐 Architecture Overview

