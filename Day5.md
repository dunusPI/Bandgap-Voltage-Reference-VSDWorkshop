# Day 5: Reference Branch Circuit

**Concepts covered:** Introduction to the reference branch circuit and the design of R2.

## Reference Branch Circuit

<img width="800" alt="Reference branch circuit" src="https://github.com/user-attachments/assets/45346c72-b014-4120-934c-1bf4d1c5581a" />

The reference branch is the third branch of the BGR. It is where the CTAT and PTAT voltages generated earlier are added together to give the final reference voltage Vref.

MP3 mirrors the bias current into this branch, so the current I3 is the same as I1 and I2. This current flows through R2 and the diode-connected BJT Q3, and Vref is taken at the top of R2.

- The voltage across Q3 (VBE) is CTAT in nature.
- The voltage across R2 is PTAT in nature, since it is driven by the PTAT current.
- Vref is the addition of the CTAT and PTAT voltages.
- R2 = α × R1

Writing this out:

Vref = VBE3 + I3 × R2

Since I3 is the same PTAT current that flows through R1 (I = Vt ln(N) / R1) and R2 = α R1, this becomes

Vref = VBE3 + α Vt ln(N)

## Design of R2 Resistance

<img width="800" alt="Design of R2 resistance" src="https://github.com/user-attachments/assets/ebb649ff-c798-4c59-8744-f82bb60ade0b" />

The temperature coefficient of Vref should be zero. All the other values are known, so α can be calculated easily, and then R2 = α × R1.

Known values:

- dVQ3/dT = -1.6 mV/°C
- dVt/dT = 85 µV/°C

Setting the temperature coefficient of Vref to zero:

d(VR2)/dT + d(VQ3)/dT = 0

Since VR2 = α × VR1:

d(α × VR1)/dT + d(VQ3)/dT = 0

Since VR1 = Vt ln(N):

d(α × Vt ln(N))/dT + d(VQ3)/dT = 0

α and ln(N) are constants, so they come out of the derivative:

(α × ln(N)) × d(Vt)/dT + d(VQ3)/dT = 0

Solving for α:

α × ln(N) = 1.6 mV / 85 µV ≈ 18.8

For N = 8, ln(8) ≈ 2.08, so α ≈ 9 and R2 = 9 × R1.

## Lab

To be added soon.
