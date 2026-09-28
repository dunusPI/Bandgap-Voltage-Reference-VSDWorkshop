# Day 3: PTAT Voltage Generation

**Concepts covered:** PTAT voltage generation circuit, its principle, and the design of the resistor R1.

## PTAT Voltage Generation

<img width="800" alt="PTAT voltage generation" src="https://github.com/user-attachments/assets/c3ba00ac-3eee-4803-9bf6-fdd92f58896c" />

A PTAT voltage can be generated using two diode-connected BJTs, Q1 and Q2, with an area ratio of 1:N (Q2 is N times larger than Q1). A current mirror, op-amp or VCVS forces nodes A and B to the same voltage V, so the same current I flows through both branches.

Q1 carries the full current, so

V = Vt ln(I / Is)

Q2 is N times larger, so its current density is I/N, and

V1 = Vt ln((I/N) / Is)

Subtracting the two, the Is terms cancel:

V - V1 = Vt ln(N)

This difference appears across R1. Vt is PTAT and ln(N) is a constant, so the voltage across R1 is PTAT.

The temperature coefficient of Vt is

Vt = kT/q, so d(Vt)/dT = k/q ≈ 86 µV/K

- V (across R1 and Q2): CTAT in nature, but with a smaller slope
- V1 (across Q2): CTAT in nature, but with a larger slope
- V - V1 (across R1): PTAT in nature

## Design of R1 Resistance

<img width="800" alt="Design of R1 resistance" src="https://github.com/user-attachments/assets/a421e55b-416c-4056-8da4-5255d0d5220c" />

R1 depends on the power consumption and silicon area budget.

R1 = Vt ln(N) / I

- As the circuit current increases, the resistance decreases, and so does the area.
- As the circuit current decreases, the resistance increases, and so does the area.
- The resistance value also depends on the number of BJTs used in branch 2 (N).

For example, for I = 10 µA and N = 8, R1 is calculated to be about 5.4 kΩ.

## Lab 5 Component

### Circuit

The circuit used for the simulation is shown below.

<img width="650" alt="PTAT circuit used in simulation" src="https://github.com/user-attachments/assets/c5589297-6ebd-4d43-a7eb-c2651eaad15d" />

### SPICE code

Below is the SPICE code for the PTAT voltage generation circuit.

<img width="800" alt="SPICE code for PTAT circuit" src="https://github.com/user-attachments/assets/f9612e67-b424-4c4d-9fb7-a7ccb654183a" />

### Generating the PTAT voltage

The idea of PTAT generation is to take the difference between two unequal CTAT voltages. The voltage vs temperature curve below shows the two CTAT voltages: V(qp2), the emitter voltage of Q2, and V(ra1), the node at the top of the 5.15 kΩ resistor R1.

<img width="800" alt="V(qp2) and V(ra1) vs temperature" src="https://github.com/user-attachments/assets/4fdcba37-4f90-481c-95fa-969d597fe26b" />

From the theoretical calculation, V(ra1) - V(qp2) = Vt ln(8). This difference is plotted below.

<img width="800" alt="V(ra1) - V(qp2) vs temperature" src="https://github.com/user-attachments/assets/5cbca6e4-40eb-41d1-ba2e-c82718330210" />

The plot has a positive slope, so the voltage has a positive temperature coefficient.

### Branch currents

Our design choice was for the same current to flow through Q1 and Q2. The current is given by

I = Vt ln(8) / R1

For T = 300 K and R1 = 5.15 kΩ, Vt = 0.026 V, so I ≈ 10.5 µA. This is the theoretically calculated value.

Below is the current plot from the simulation. The currents in both branches are equal.

<img width="800" alt="Branch currents vs temperature" src="https://github.com/user-attachments/assets/a30f9277-d542-4df4-b9d3-a22fccdad51b" />

<img width="800" alt="Branch current at 27 degrees C" src="https://github.com/user-attachments/assets/33805e36-f81e-4f2e-bcac-1a5923f69098" />

<img width="299" alt="Current value at 27 degrees C" src="https://github.com/user-attachments/assets/b7c47999-a752-4e29-b0b7-7e6b1e867d9c" />

At 27 °C (300 K), the simulated current is about 10.8 µA, which is close to the theoretically calculated value.
