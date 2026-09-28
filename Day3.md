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


