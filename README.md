# VHDL Integer Range Synthesis Issue

This repository demonstrates a common problem encountered when using integer ranges in VHDL code intended for synthesis.  Specifically, using an integer range for counters can lead to suboptimal or incorrect results.  The `counter.vhdl` file shows the problematic code, while `counter_fixed.vhdl` provides a corrected version.

## Problem

The original `counter.vhdl` uses an `integer` type with a range for the counter.  Synthesis tools might not handle this efficiently, potentially leading to a larger implementation than necessary. 

## Solution

The `counter_fixed.vhdl` uses a `std_logic_vector` to represent the counter, which is far more suitable for synthesis as it maps directly to hardware registers. This provides a more efficient implementation and better compatibility across different synthesis tools. 

## How to run

1.  Use a VHDL simulator (like ModelSim or GHDL) to simulate both versions and compare the results.
2.  Use a synthesis tool (like Xilinx Vivado or Intel Quartus) to synthesize both versions. Observe the resource utilization (LUTs, FFs, etc.) to see the improvement after changing to `std_logic_vector`.