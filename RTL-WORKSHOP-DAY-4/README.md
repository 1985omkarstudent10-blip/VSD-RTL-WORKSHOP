# Day 4 - Gate Level Simulation, Blocking vs Non-Blocking Assignments and Synthesis-Simulation Mismatch

## Objective

The objective of Day 4 was to understand Gate Level Simulation (GLS), learn the difference between blocking and non-blocking assignments in Verilog, and study the common reasons behind synthesis-simulation mismatches.

Through practical examples and simulations, I explored how RTL designs are verified after synthesis and how coding styles affect circuit behavior.

---

## Introduction to Gate Level Simulation (GLS)

One of the most important topics covered during this session was Gate Level Simulation (GLS).

GLS is performed after synthesis to verify that the synthesized netlist behaves exactly as intended and produces the same functionality as the original RTL design.

### Why GLS is Required

The RTL simulation verifies the design behavior before synthesis.

However, after synthesis, the RTL is converted into a gate-level netlist using standard cells from the technology library.

GLS helps verify:

* Functional correctness after synthesis.
* Proper netlist generation.
* Timing behavior of the synthesized design.
* Consistency between RTL and gate-level implementation.

---

## GLS Flow

In a normal RTL simulation:

```text
RTL Design + Testbench → Icarus Verilog → VCD File → GTKWave
```

For Gate Level Simulation:

```text
Netlist + Gate-Level Verilog Models + Testbench
                    ↓
               Icarus Verilog
                    ↓
                 VCD File
                    ↓
                 GTKWave
```

Unlike RTL simulation, the design under test is replaced by the synthesized gate-level netlist.

The same testbench can be reused to verify that the synthesized design behaves correctly.

---

## Gate-Level Verilog Models

During GLS, gate-level Verilog models are included along with the netlist.

These models represent the actual standard cells used during synthesis.

I learned that these models can also contain timing information, allowing GLS to be used for timing verification in addition to functional verification.

---

## Understanding Synthesis-Simulation Mismatch

Another important concept discussed was synthesis-simulation mismatch.

A mismatch occurs when:

* RTL simulation produces one result.
* Synthesized hardware or gate-level simulation produces a different result.

Such mismatches can lead to unexpected hardware behavior.

---

## Causes of Synthesis-Simulation Mismatch

### Incomplete Sensitivity Lists

When using an always block, all signals that affect the output should be included in the sensitivity list.

Missing signals may cause simulation results that differ from synthesized hardware.

Example:

```verilog
always @(sel)
```

Instead of:

```verilog
always @(*)
```

Using `always @(*)` ensures that all dependent signals are automatically included.

---

### Improper Coding Style

Another common reason for mismatches is incorrect usage of procedural assignments.

Following proper Verilog coding practices helps avoid these issues.

---

## Blocking vs Non-Blocking Assignments

A major portion of Day 4 focused on understanding the difference between blocking and non-blocking assignments.

Both are used inside always blocks but behave differently.

---

## Blocking Assignments

Syntax:

```verilog
=
```

### Characteristics

* Statements execute one after another.
* Order of execution is important.
* Each statement completes before the next one starts.
* Commonly used for combinational logic.

### Observation

I observed that changing the order of blocking statements can change the resulting behavior of the circuit.

Therefore, blocking assignments must be used carefully.

---

## Non-Blocking Assignments

Syntax:

```verilog
<=
```

### Characteristics

* Right-hand side values are evaluated together.
* Updates occur simultaneously at the end of the time step.
* Order of statements generally does not affect the result.
* Commonly used for sequential logic.

### Observation

Non-blocking assignments provide behavior that closely matches actual flip-flops and sequential hardware.

Because of this, they are preferred for sequential circuit design.

---

## Blocking Assignment Caveat

One of the examples demonstrated how the order of blocking statements can affect the output.

If an intermediate variable is used before it is updated, the output may be calculated using an older value.

This highlighted the importance of carefully arranging statements when using blocking assignments.

---

## Key Difference Observed

| Blocking Assignment                                   | Non-Blocking Assignment              |
| ----------------------------------------------------- | ------------------------------------ |
| Executes sequentially                                 | Executes concurrently                |
| Order matters                                         | Order generally does not matter      |
| Common in combinational logic                         | Common in sequential logic           |
| Can introduce unintended behavior if used incorrectly | Models flip-flop behavior accurately |

---

## Practical Activities Performed

During the session, I:

* Simulated RTL designs.
* Generated synthesized netlists.
* Performed Gate Level Simulation using Icarus Verilog.
* Compared RTL and gate-level simulation flows.
* Studied synthesis-simulation mismatches.
* Analyzed blocking and non-blocking assignment behavior.
* Observed the effect of incomplete sensitivity lists.
* Investigated examples demonstrating coding pitfalls.

---

## Learning Outcomes

By the end of Day 4, I was able to:

* Understand the purpose of Gate Level Simulation.
* Perform simulation using synthesized netlists.
* Understand the role of gate-level Verilog models.
* Identify common causes of synthesis-simulation mismatch.
* Differentiate between blocking and non-blocking assignments.
* Understand why non-blocking assignments are preferred for sequential circuits.
* Recognize the importance of complete sensitivity lists.
* Analyze coding practices that can affect synthesized hardware behavior.

---

## Conclusion

Day 4 provided valuable insights into post-synthesis verification and RTL coding practices. Through Gate Level Simulation and practical examples, I learned how synthesized hardware is verified and how proper Verilog coding techniques help avoid mismatches between simulation and actual hardware implementation.
