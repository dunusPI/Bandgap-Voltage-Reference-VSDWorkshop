# Day 7: Complete BGR Circuit

**Concepts covered:** The complete bandgap voltage reference circuit, and a summary of Days 1 to 6.

## Complete BGR Circuit

<img width="800" alt="Complete BGR circuit" src="https://github.com/user-attachments/assets/078b7a78-d3d7-4a7e-8d02-357bf971a74c" />

The complete circuit is made of four blocks, each of which was covered on an earlier day:

- **SBCM (self-biased current mirror):** MP1, MP2, MN1 and MN2, which set up a supply-independent current (Day 4).
- **CTAT and PTAT generation:** Q1 with the 1:N ratio Q2 and resistor R1 (Days 2 and 3).
- **Reference branch:** MP3, R2 and Q3, where the CTAT and PTAT voltages are added to give Vref (Day 5).
- **Start-up circuit:** MP4, MP5 and MN3, which get the circuit out of the zero-current state at power-up (Day 6).

## Summary of Days 1 to 6

**Day 1: Introduction to BGR.** A BGR provides a reference voltage that stays constant across process, voltage and temperature (PVT) variations. Batteries, power supplies and Zener references are not suitable as an on-chip reference. A BGR combines a CTAT and a PTAT voltage so that the temperature dependence cancels, giving about 1.2 V, close to the bandgap energy of silicon.

**Day 2: CTAT voltage generation.** The base-emitter voltage (VBE) of a diode-connected BJT has a negative temperature coefficient. BJTs are used instead of a plain diode because they integrate easily with the CMOS process. The slope becomes more negative with more transistors, and less negative as the collector current (current density) increases.

**Day 3: PTAT voltage generation.** Two BJTs with an area ratio of 1:N carrying the same current give a voltage difference of Vt ln(N) across R1. Since Vt = kT/q, this voltage is PTAT. R1 is designed from R1 = Vt ln(N) / I, so it depends on the current and on N.

**Day 4: Self-biased current mirror.** A normal current mirror's output changes with the supply voltage. A self-biased mirror derives Iref from Iout, which makes the current largely supply independent. Adding Rs sets a unique current level.

**Day 5: Reference branch.** The current I3 is the same as I1 and I2. The voltage across Q3 is CTAT and the voltage across R2 is PTAT, so Vref is their sum. R2 = α × R1, and α is chosen so that the temperature coefficient of Vref is zero.

**Day 6: Start-up circuit.** A self-biased mirror has a degenerate state where all transistors are off and no current flows. The start-up circuit injects current at power-up to leave this state, then turns itself off once the loop is running.

## Putting It Together

The reference voltage is

Vref = VBE3 + α Vt ln(N)

The first term is CTAT and the second is PTAT. Setting the total temperature coefficient to zero gives

α × ln(N) = |dVBE3/dT| / (dVt/dT)

The design flow is then:

1. Choose the bias current I and the area ratio N.
2. Calculate R1 = Vt ln(N) / I.
3. Calculate α from the zero temperature coefficient condition.
4. Calculate R2 = α × R1.

For example, with I = 10 µA and N = 8, R1 is about 5.4 kΩ. Using the slide values of -1.6 mV/°C and 85 µV/°C, α is about 9, so R2 is about 49 kΩ and Vref is about 1.2 V.

## Lab

### Circuit

The circuit used for the simulation is shown below.

<img width="800" alt="BGR circuit used in simulation" src="https://github.com/user-attachments/assets/eb7fe610-e9bc-40f6-82d4-290ab73bf489" />

### SPICE code

The SPICE code spans the two images below.

<img width="800" alt="SPICE code, part 1" src="https://github.com/user-attachments/assets/55bc45f4-388c-4259-a63f-721a8c5bfaa8" />

<img width="800" alt="SPICE code, part 2" src="https://github.com/user-attachments/assets/f108dac4-8d7b-4293-88cf-4260bdef9ae2" />

### BGR response

The BGR response is shown below.

<img width="800" alt="Vref vs temperature" src="https://github.com/user-attachments/assets/36312a65-bf9c-43a2-8996-af16aebf12f2" />

We designed for Vref = 1.2 V, but the highest value of Vref in the response is 1.235 V. The curve has the expected umbrella shape, as discussed in the theory. The peak-to-peak variation of Vref is 3.3 mV.

### Verifying the circuit

**1. Equal voltages at the VCVS inputs.** The two inputs of the VCVS should be at the same voltage, so v(qp1) and v(ra1) should be equal (see the circuit diagram).

<img width="800" alt="v(qp1) and v(ra1) vs temperature" src="https://github.com/user-attachments/assets/ae13e051-57b5-44db-ae0c-705f8d914437" />

Both voltages stay at the same level across the whole temperature sweep.

**2. Equal currents in the two branches.** The currents in the branches Vid1 and Vid2 should be the same.

<img width="800" alt="Branch currents Vid1 and Vid2" src="https://github.com/user-attachments/assets/05de6468-a168-4ed8-80f6-c9e03bfc8bd5" />

The current is the same in both branches.

**3. CTAT and PTAT voltages cancel.**

The CTAT voltage is the VBE of Q3.

<img width="800" alt="VBE of Q3 vs temperature" src="https://github.com/user-attachments/assets/8dc594eb-ccee-4a0f-88b8-a26bdf2fbbdb" />

The slope is -1.636 mV/K.

<img width="683" alt="CTAT slope measurement" src="https://github.com/user-attachments/assets/659dae15-0a5c-4408-8ce3-8d1a541b9e28" />

The PTAT voltage is Vref - VBE(Q3).

<img width="800" alt="Vref minus VBE of Q3 vs temperature" src="https://github.com/user-attachments/assets/ae0a4271-90ed-42c5-bc4b-a42c27e32ab1" />

The slope is +1.646 mV/K.

<img width="581" alt="PTAT slope measurement" src="https://github.com/user-attachments/assets/fcded23e-d85b-47a0-b3c7-ee1e077d913e" />

The two slopes are very close in magnitude and opposite in sign, so the CTAT and PTAT voltages cancel. The overall curve is shown below.

<img width="800" alt="Overall Vref curve" src="https://github.com/user-attachments/assets/ba84afdb-09fd-4a80-b5df-72926ccc0aa7" />

**4. Scaling of the PTAT voltage in the reference branch.** The PTAT voltage in the reference branch is

Vref - VBE3 = Vt ln(8) × R2 / R1

while across R1 the PTAT voltage is

V(ra1) - VBE2 = Vt ln(8)

In our circuit R1 = 5 kΩ and R2 = 45 kΩ, so the PTAT slope in the reference branch should be about 9 times the slope across R1.

Slope of the PTAT voltage in the reference branch:

<img width="620" alt="PTAT slope in reference branch" src="https://github.com/user-attachments/assets/645f1c94-2428-408b-8e85-0cf98b746681" />

Slope = 1.638 mV/K

Slope of the PTAT voltage across R1:

<img width="622" alt="PTAT slope across R1" src="https://github.com/user-attachments/assets/a46a7f1d-baac-4852-9e3c-524438bbb336" />

Slope = 0.1897 mV/K

α = 1.638 / 0.1897 ≈ 8.63, which is roughly 9, so the scaling is verified.
  
   

   
   










