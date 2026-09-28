# Day 2: CTAT Voltage Generation Circuit

**Concepts covered:** CTAT voltage generation circuit: principles, design equations, and SPICE simulation for the labs.

## CTAT Voltage Generation Circuits

<img width="800" alt="CTAT generation circuits" src="https://github.com/user-attachments/assets/9fa99801-dd5d-4f4b-95ab-52cf0afb6f4d" />

In principle, a CTAT voltage generation circuit can be made with any electronic device that shows a negative temperature coefficient. Two methods are shown above: one with a normal diode and the other with a diode-connected BJT.

Diode-connected BJTs are preferred because of their ease of manufacturing and fabrication.

For a diode, the fabrication structure is shown below.

<img width="530" alt="Diode fabrication structure" src="https://github.com/user-attachments/assets/9b42be5e-3d1e-44c9-9095-c8448ab5a8cf" />

In the fabrication process we generally make the P-substrate the ground, and hence this diode structure is not possible here.

We go with the BJT as a diode because its structure integrates easily with the CMOS process, as shown below.

<img width="800" alt="BJT structure in CMOS process" src="https://github.com/user-attachments/assets/95fcc764-8797-4489-97b1-b9e56c9a06d6" />

The image above also shows that the current from emitter to collector is not affected by the current from emitter to base.

## Negative Temperature Coefficient

<img width="800" alt="Negative temperature coefficient of VBE" src="https://github.com/user-attachments/assets/debdcf61-3452-4d45-bb79-62b4b6e93b70" />

As seen above, the PN junction between the emitter and base provides the negative temperature coefficient.

<img width="452" alt="Temperature coefficient equation" src="https://github.com/user-attachments/assets/c9b8b6f2-bea1-4e81-b276-8cdcb1675376" />

For VBE = 700 mV and T = 300 K, this formula gives a temperature coefficient of around -1.9 mV/K.

## Variation of the Slope with the Number of Transistors

<img width="800" alt="Slope vs number of transistors" src="https://github.com/user-attachments/assets/11e58caa-7a82-421a-8ae1-3fce84c07cde" />

The more BJTs there are, the more negative the slope becomes. This is because VBE drops significantly with more transistors while the collector current is kept fixed.

## Variation of the Slope with Collector Current

<img width="756" alt="Slope vs collector current" src="https://github.com/user-attachments/assets/6cddae00-a367-4338-8dad-8910037284a7" />

As we increase the collector current, the current density increases and the slope becomes less and less negative.

## Lab 4 Component

### SPICE code

Below is the SPICE code for the CTAT voltage generation circuit.

<img width="767" alt="SPICE code for CTAT circuit" src="https://github.com/user-attachments/assets/dc3234aa-2f75-4c01-b92b-9f0604f4aa97" />

### VBE vs temperature

The voltage vs temperature curve is shown below.

<img width="800" alt="VBE vs temperature" src="https://github.com/user-attachments/assets/3ac41726-fadd-428e-91f7-1717390446c1" />

- Slope measured from simulation: -1.723 mV/K
- Slope from theoretical calculation: -1.88 mV/K

### Effect of the number of BJTs

The voltage vs temperature curve for m = 8 (BJT multiplier) is shown below.

<img width="800" alt="VBE vs temperature for m = 8" src="https://github.com/user-attachments/assets/cf549510-bb7c-43bd-943e-92abc0119350" />

The slope measured from simulation is -1.91 mV/K, which is more negative than for a single BJT, in line with the discussion above.

### Effect of the collector current

The voltage vs temperature curve for a varying current is shown below. The current was varied from 1.25 µA to 10 µA.

<img width="800" alt="VBE vs temperature for varying current" src="https://github.com/user-attachments/assets/6e894485-6864-4ea1-ad2f-34f58410aacb" />

- Slope at 10 µA: -1.7345 mV/K
- Slope at 1.25 µA: -1.918 mV/K

The slope becomes less negative as the current increases, in line with the discussion above.

<img width="491" alt="Slope measurements for varying current" src="https://github.com/user-attachments/assets/fb90698f-95f6-4662-af40-b6b753d3fed8" />
