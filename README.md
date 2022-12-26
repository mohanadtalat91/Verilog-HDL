# Write a Verilog HDL code that does the following:


* Usee only the MINIMUM number of the follwing components: Full-adders, 4x1 Multiplexers, 2x1 Multiplexers, or, and, not, xor gates.
* A full-adder counts only as 1 component, not counting the small components inside. Also, a multiplexer counts as 1 component.
* At the beginning of the file, a comment including the components I've used and the number of them.
* Implementation of multiplexers using structural Verilog descriptions.
* The input is two selection inputs, and two signed integers in 2's complement form: A and B, each integer is 3-bits.
* The output is a signed integer in 2's complement from: G, its size is 3-bits.
* When the selection inputs are 00, G = A-1
* When the selection inputs are 01, G = A+B
* When the selection inputs are 10, G = A-B
* When the selection inputs are 11, G = -B
* Provide a test benchs that tests all aspects of the implemented circuit with at least 40 test cases on various input values randomly.
* You are not allowed to use behavioral Verilog descriptions (if, switch, ..etc) for multiplexers or any other aspects except for test bench.
* Used structured Verilog descriptions for all aspects, except for test bench, so I used behavioral Verilog description for test bench only.
* The Verilog HDL code must be able to be compiled in the same way with the instructions below.

## Run

> Open cmd at the same dircetory and type ``` iverilog -o assv ass_cir.v ```


> Then type in the next line ``` vvp assv  ```
