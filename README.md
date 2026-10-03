````markdown
# 5-Stage Pipelined RISC Processor

The design focuses on:

A 5-stage pipelined RISC processor with forwarding, hazard detection, and branch prediction support.
P3 lays out the skeleton of the processor.
P4 makes the processor to be pipelined.
P5 adds the hazard detection unit.
P6 adds the forwarding units.
P7 adds multicycle cache memory.

## Project Architecture

### High-Level Design

```text
+-------------------+
| Instruction Fetch |
+-------------------+
          |
          v
+-------------------+
| Instruction Decode|
+-------------------+
          |
          v
+-------------------+
| Execute Stage     |
+-------------------+
          |
          v
+-------------------+
| Memory Stage      |
+-------------------+
          |
          v
+-------------------+
| Writeback Stage   |
+-------------------+
````

### Main Components

* **ALU**

  * Arithmetic and logical operations
* **Register File**

  * Dual-read single-write architecture
* **Control Unit**

  * Generates datapath control signals
* **Pipeline Registers**

  * IF/ID, ID/EX, EX/MEM, MEM/WB
* **Hazard Detection Unit**

  * Handles stalls and data hazards
* **Forwarding Unit**

  * Reduces pipeline stalls

---

## Features

* [x] 5-stage pipelined architecture
* [x] Data forwarding
* [x] Hazard detection
* [x] Branch handling
* [x] Parameterized modules
* [x] Testbench support
* [ ] Cache implementation
* [ ] Branch predictor

---

## Getting Started

### Prerequisites

Install:

* Icarus Verilog / ModelSim / QuestaSim
* GTKWave
* Make

Example (Ubuntu):

```bash
sudo apt install iverilog gtkwave make
```

---

## Running Simulation

### Compile

```bash
make compile
```

### Run Tests

```bash
make test
```

### Open Waveforms

```bash
gtkwave waveform/output.vcd
```

---

## Example Test Output

```text
[PASS] ALU addition test
[PASS] Register file write/read
[PASS] Pipeline forwarding
[PASS] Branch instruction test
```

## Verification Strategy

The design was verified using:

* Directed testbenches
* Randomized testing
* Waveform inspection
* Corner-case validation

Key verified scenarios:

* RAW hazards
* Load-use hazards
* Branch flush behavior
* Memory operations
