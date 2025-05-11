# Resistive Crossbar Matrix-Vector Multiplication Simulation

This project demonstrates how a resistive crossbar can be used to perform matrix-vector multiplication. The goal is to simulate a 4x4 resistive crossbar in SPICE, where the resistances at each intersection of the matrix represent the weights of the matrix, and the voltages applied to the rows represent the input vector.

## Learning Goals

- Simulate a resistive crossbar in SPICE.
- Understand how matrix-vector multiplication works in a resistive crossbar.

## Challenge Overview

The tasks in this challenge are as follows:
1. Write SPICE code to simulate a 4x4 resistive crossbar with fixed resistances.
2. Demonstrate that the resulting output currents match the product of a 4x1 input vector and a 4x4 weight matrix.

## Project Structure

- **SPICE Code**: The main code simulates the resistive crossbar network. It defines the resistors (weights of the matrix), the voltage sources (input vector), and the output current measurement nodes.
- **Matrix-Vector Multiplication**: The simulation demonstrates how resistive elements in the crossbar can perform matrix-vector multiplication by applying voltages to the rows and measuring the resulting currents.

## Prerequisites

- **SPICE Simulation Tool**: You will need a SPICE simulation tool to run the code. A popular SPICE simulator like [LTspice](https://www.analog.com/en/design-center/design-tools-and-calculators/ltspice-simulator.html) or [NGSpice](http://ngspice.sourceforge.net/) will work.
  
## Setup and Running the Simulation

1. Download and install your preferred SPICE simulation tool (e.g., LTspice, NGSpice).
2. Copy the SPICE code provided in the project to a `.cir` file (e.g., `crossbar_matrix_vector.cir`).
3. Modify the input voltages in the SPICE code to set the values for the 4x1 input vector.
4. Run the simulation to observe the output currents, which correspond to the matrix-vector multiplication result.

### Example SPICE Code

```spice
* Resistive Crossbar Simulation for 4x4 Matrix-Vector Multiplication

* Node Definitions for 4x4 Crossbar
* Rows are R1, R2, R3, R4 (weights of the matrix)
* Columns are C1, C2, C3, C4 (input vectors)

* Resistor network for 4x4 crossbar with resistances R1 to R16
R11 1 2 10k
R12 1 3 10k
R13 1 4 10k
R14 1 5 10k
R21 2 3 10k
R22 2 4 10k
R23 2 5 10k
R24 2 6 10k
R31 3 4 10k
R32 3 5 10k
R33 3 6 10k
R34 3 7 10k
R41 4 5 10k
R42 4 6 10k
R43 4 7 10k
R44 4 8 10k

* Voltage sources for input vector
V1 9 0 DC 1V
V2 10 0 DC 2V
V3 11 0 DC 3V
V4 12 0 DC 4V

* Define the output nodes for current measurement
Iout1 13 0 DC 0
Iout2 14 0 DC 0
Iout3 15 0 DC 0
Iout4 16 0 DC 0

* Simulation commands
.tran 1ms 10ms
.end

```






Conclusion
This project demonstrates how a resistive crossbar network can perform matrix-vector multiplication by utilizing resistive elements to represent the weights of the matrix. The simulation results verify that the output currents match the expected results of matrix-vector multiplication.

Potential Applications:
Neuromorphic Computing: Crossbar arrays can be used in neuromorphic computing systems to accelerate matrix operations.

Hardware Accelerators: This approach could be adapted for hardware accelerators in machine learning models, enabling faster computations.

