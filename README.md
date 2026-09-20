# Graph-Convolution-Neural-Network
ASIC Design Flow: Verilog RTL to GDSII Physical Implementation

## Problem Statement
Graph Neural Networks and GCNs require processing complex, non regular data structures that lead to significant memory bandwidth bottlenecks and compute inefficiencies on traditional general purpose processors (CPUs/GPUs). Key challenges include:
1. **Irregular memory pattern access**
2. **Strict Latency Constrains**
3. **Setting the boundary and I/O**
This project addresses these challenges by hardware accelerating the linear transformation, sparse aggregation, and classification phases with custom processing blocks and an optimized physical layout.

## Architecture and Features:
Consists of three microarchitecture stages integrated with registered I/O boundary flip flops.
1. **Transformation Block:** High throughput matrix multiplier executing weight linear transformations.
2. **Aggregation Unit:** Special unit optimized for the sparse data structures to aggregate neighbor node features efficiently.
3. **Argmax Classifier:** Hardware decision logic that compares scores across all target classes and categorizes the node based on the maximum value.

## Tools and Software Used:
1. **RTL Design:** VS Code, ModelSim
2. **Synthesis and Timing Analysis:** Synopsys Design Compiler
3. **Physical Design & APR:** Cadence Innovus
4. **Design Verification:** Siemens Calibre

## Results and Outcome:
The design successfully passed full ASIC implementation with zero violations.
1. **Clock Frequency and Latency:** Total execution time of **600 clock cycles**, satisfied the low latency requirement of **< 100 ns**.
2. **Timing Constrains:** **Zero setup and hold violations** with a small margin of positive slack in post Synthesis and post Auto Place & Route CTS.
3. **Physical Design:** Achieved **100% clean DRC and LVS** verification with zero manufacturing or schematic mismatch errors.
4. **Interface Design:** Registered boundary flip flops validated for noise immunity and clean integration into SoC environments.

**Through this project, I gained hands on experience in the complete RTL to GDSII ASIC design flow. Verilog architecture, logic synthesis, floorplanning, CTS, timing analysis, and physical design while optimizing dedicated hardware for sparse AI workloads.**
