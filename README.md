# RTL Design and Synthesis Workshop Documentation

## Overview

This repository contains my documentation, observations, lab activities, and learning outcomes from the RTL Design and Synthesis Workshop. Throughout the workshop, I explored the complete digital design flow starting from RTL design and simulation to synthesis, optimization, gate-level simulation, and coding practices for efficient hardware implementation.

The workshop provided hands-on experience with industry-standard open-source tools such as:

* Icarus Verilog (iverilog)
* GTKWave
* Yosys
* SKY130 Standard Cell Libraries

---

## Workshop Structure

### Day 1 – Introduction to RTL Design and Synthesis

Topics Covered:

* Linux and VirtualBox environment setup
* RTL design fundamentals
* Verilog design and testbench concepts
* Simulation using Icarus Verilog
* Waveform analysis using GTKWave
* Introduction to Yosys synthesis flow
* Understanding netlists and standard cell libraries

Key Learning:

I learned the complete RTL-to-Gate-Level flow, including simulation, synthesis, netlist generation, and verification.

---

### Day 2 – Timing Libraries, Synthesis Approaches and Flip-Flops

Topics Covered:

* Understanding SKY130 Liberty (.lib) files
* Process, Voltage and Temperature (PVT) corners
* Hierarchical vs Flattened synthesis
* D Flip-Flop coding styles
* Synchronous and Asynchronous reset/set behavior

Key Learning:

I understood how technology libraries characterize standard cells and how synthesis tools map RTL logic to hardware using these libraries.

---

### Day 3 – Combinational and Sequential Logic Optimization

Topics Covered:

* Constant propagation
* Boolean logic optimization
* Sequential optimization
* Removal of unused logic
* Optimization during synthesis

Key Learning:

I learned how synthesis tools simplify logic to reduce hardware area, improve efficiency, and eliminate unnecessary circuitry.

---

### Day 4 – Gate Level Simulation and Coding Practices

Topics Covered:

* Gate Level Simulation (GLS)
* Netlist verification
* Blocking vs Non-Blocking assignments
* Synthesis-Simulation mismatch
* Sensitivity list considerations

Key Learning:

I understood how to verify synthesized hardware using GLS and learned coding practices that help avoid mismatches between simulation and hardware implementation.

---

### Day 5 – Latch Inference and Advanced RTL Coding

Topics Covered:

* If-Else statements
* Case statements
* Inferred latches
* Complete vs incomplete coding styles
* For loops
* Generate blocks
* Ripple Carry Adder implementation

Key Learning:

I learned how coding style affects synthesized hardware and how to avoid unintended latch inference while designing scalable digital circuits.

---

## Tools Used

| Tool              | Purpose                  |
| ----------------- | ------------------------ |
| Ubuntu Linux      | Development Environment  |
| Oracle VirtualBox | Virtual Machine Platform |
| Icarus Verilog    | RTL Simulation           |
| GTKWave           | Waveform Analysis        |
| Yosys             | Logic Synthesis          |
| SKY130 PDK        | Standard Cell Library    |

---

## Repository Structure

```text
RTL-Design-and-Synthesis-Workshop/
│
├── Day1/
├── Day2/
├── Day3/
├── Day4/
├── Day5/
│
└── README.md
```

Each folder contains:

* Day-wise documentation
* Lab observations
* Learning outcomes
* Screenshots of simulations and synthesis results

---

## Overall Learning Outcomes

By completing this workshop, I gained practical experience in:

* RTL Design using Verilog
* Digital Logic Simulation
* Testbench Development
* Logic Synthesis using Yosys
* Understanding Standard Cell Libraries
* Timing and PVT Concepts
* Combinational and Sequential Optimization
* Gate-Level Simulation
* Verilog Coding Best Practices
* Hardware-Oriented Thinking and Design Methodology

---

## Conclusion

This workshop provided a strong foundation in digital design and RTL development. The combination of theory, simulation, synthesis, optimization, and verification helped me understand how Verilog designs are transformed into hardware-ready implementations. The hands-on labs strengthened my understanding of modern VLSI design flows and open-source EDA tools.
