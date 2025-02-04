# VHDL Counter Overflow Bug

This repository demonstrates a subtle bug in a VHDL counter implementation. The counter lacks proper overflow handling, which can lead to incorrect results without a clear error message. The `buggy_counter.vhdl` file contains the flawed code, while `fixed_counter.vhdl` presents the corrected version.

## Bug Description

The `buggy_counter` entity increments its internal count on each rising clock edge without checking if it has reached the upper limit (15). When the counter reaches its maximum value, it wraps around to 0, producing incorrect output. This behavior is silent and might be difficult to detect.

## Solution

The `fixed_counter` entity solves the overflow problem by adding a conditional statement that checks if the counter has reached its upper limit before incrementing. If the counter is already at the maximum value, it remains unchanged, preventing the overflow.  This ensures the counter behaves as expected.

## How to Reproduce

1. Simulate `buggy_counter.vhdl` and observe the incorrect count value after it reaches 15.
2. Simulate `fixed_counter.vhdl` to see the correct counter behavior.