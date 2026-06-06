# Day 1 - Introduction to RTL Design, Simulation and Synthesis

## Objective

The objective of Day 1 was to set up the RTL design environment, understand the basic RTL design flow, perform Verilog simulations, and get introduced to synthesis using Yosys.

---

## Environment Setup

The first task was to set up the workshop environment on my system.

### Steps Performed

* Installed Oracle VirtualBox.
* Imported the workshop virtual machine image provided during the workshop.
* Launched the Ubuntu environment inside VirtualBox.
* Logged in using the workshop credentials and configured the setup.
* Created the required working directory inside the VSD user workspace.
* Cloned the workshop repositories containing RTL design examples, standard cell libraries, and supporting files.
* Verified that all required tools were available and functioning correctly.

This setup helped me understand how an RTL design environment is organized and how different tools are integrated into the digital design flow.

---

## Introduction to RTL Design

During the session, I learned that RTL (Register Transfer Level) is a way of describing the behavior of a digital circuit using hardware description languages such as Verilog.

Instead of directly creating hardware, RTL allows designers to describe the intended functionality of a circuit before it is physically implemented.

---

## Verilog Simulation Flow

I was introduced to the simulation flow using Icarus Verilog and GTKWave.

### Simulation Process

1. Provide the design file and testbench as inputs.
2. Compile the design using Icarus Verilog.
3. Execute the generated simulation file.
4. Generate a VCD (Value Change Dump) file.
5. Open the VCD file using GTKWave.
6. Observe and verify the waveform outputs.

Through this process, I understood how simulation helps verify the functionality of a design before synthesis.

---

## Understanding Testbench and Design Files

### Design File

The design file contains the actual RTL logic that defines the functionality of the circuit.

### Testbench

The testbench provides input stimulus to the design and helps verify whether the output matches the expected behavior.

I observed how both files work together during simulation to validate a digital design.

---

## Introduction to Synthesis

I learned that synthesis is the process of converting RTL code into a gate-level representation that can be physically implemented.

The synthesis tool used during the workshop was **Yosys**.

### Synthesis Flow

* Read the standard cell library (.lib file).
* Read the RTL design.
* Perform synthesis.
* Map the design to available standard cells.
* Generate the gate-level netlist.
* Visualize the synthesized circuit.
* Export the generated netlist.

The generated netlist represents the hardware implementation of the RTL design using logic gates and their interconnections.

---

## Important Concepts Learned

### RTL

RTL describes the functionality and behavior of digital circuits using Verilog before hardware implementation.

### Netlist

A netlist is a gate-level representation of a design that contains gates and their connections.

### Standard Cell Library

The library contains different logic cells and gate variants used by the synthesis tool during technology mapping.

### Simulation vs Synthesis

| Simulation              | Synthesis                               |
| ----------------------- | --------------------------------------- |
| Verifies functionality  | Converts RTL to hardware representation |
| Uses design + testbench | Uses design + standard cell library     |
| Produces waveforms      | Produces gate-level netlist             |

---

## Yosys Commands Explored

During the synthesis flow, I became familiar with the following commands:

```bash
yosys
read_liberty
read_verilog
synth -top
abc -liberty
show
write_verilog
```

These commands are used to read libraries, synthesize designs, perform technology mapping, visualize logic, and generate netlists.

---

## Learning Outcomes

By the end of Day 1, I was able to:

* Successfully set up the workshop environment.
* Understand the RTL design flow.
* Run Verilog simulations and observe waveforms.
* Understand the purpose of testbenches.
* Learn the difference between simulation and synthesis.
* Generate and visualize synthesized hardware using Yosys.
* Understand the role of netlists and standard cell libraries in digital design.

---

## Conclusion

Day 1 provided a strong foundation in RTL design by introducing the complete flow from Verilog coding and simulation to synthesis and gate-level implementation. The hands-on exercises helped me understand how digital circuits are verified and transformed into hardware-ready representations.
