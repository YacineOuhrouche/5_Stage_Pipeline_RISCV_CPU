# RV32I 5-Stage Pipelined Processor (Verilog)

## Overview
This project implements a 32-bit RISC-V (RV32I) 5-stage pipelined processor in Verilog.  
The pipeline consists of IF, ID, EX, MEM, and WB stages with pipeline registers between each stage.

## Supported Instructions
- **R-type:** ADD, SUB, AND, OR, XOR, SLT, SLTU, SLL, SRL, SRA  
- **I-type:** ADDI, ANDI, ORI, XORI, SLTI, SLTIU, SLLI, SRLI, SRAI  
- **Load/Store:** LW, SW  
- **Branch:** BEQ, BNE, BLT, BGE, BLTU, BGEU  
- **Jump:** JAL, JALR  
- **Upper Immediate:** LUI, AUIPC  

## Features
- 5-stage pipelined architecture  
- Forwarding for data hazard resolution  
- Load-use hazard detection with stall insertion  
- Control hazard handling with pipeline flush  
- Branch and jump resolution in EX stage  

---
## Development Environment
- Verilog / SystemVerilog  
- VSCode  
- Icarus Verilog (simulation)  
- Verilator (linting)  
- Yosys (synthesis and area estimation)  
- OpenSTA (timing analysis)  
- Surfer (waveform visualization)

- 
## Datapath
- Operand selection using forwarding and ALU input muxes  
- Branch comparator and decision logic in EX stage  
- PC redirect logic for branches and jumps  
- Writeback selection between ALU result, memory data, and PC+4  

<img width="468" height="258" alt="image" src="https://github.com/user-attachments/assets/21be525a-01c1-4120-ad53-ea5bc20ee330" />

---

## Verification

The design was verified using directed test programs and simulation waveforms:
- Normal execution (no hazards)  
- Data hazards resolved with forwarding  
- Load-use hazards with stall insertion  
- Control hazards with pipeline flush

# waveform (hazard)
<img width="1069" height="624" alt="hazard" src="https://github.com/user-attachments/assets/24e3d35c-852a-49ff-bb2d-e5e8becb1a68" />

---

## Analysis
- **Timing Analysis:** Performed using OpenSTA to evaluate critical path and maximum clock frequency  
- **Area Estimation:** Synthesized with Yosys to estimate hardware usage and approximate transistor count  
- **Power Analysis:** Evaluated to understand power-performance trade-offs

  # Yosys synthesis results
<img width="238" height="263" alt="image" src="https://github.com/user-attachments/assets/47869c0e-3816-4ef7-b8c3-9566d2cc2547" />

# OpenSTA power analysis results
<img width="468" height="138" alt="image" src="https://github.com/user-attachments/assets/eb5ccced-0c44-4bf1-a9e4-ddee0088206c" />

--


## RTL Organization
<img width="233" height="403" alt="image" src="https://github.com/user-attachments/assets/94c58103-364d-4998-ba0d-54fd3bdf5dda" />

## Report
For full design details, datapath diagrams, and analysis, see:  
**RISCV-32I-5-STAGE-PIPELINED.pdf**

