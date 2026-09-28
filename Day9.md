# Day 9: Transient Analysis of the Complete BGR Circuit

**Concepts covered:** Transient simulation of the complete BGR circuit, the start-up behaviour, and the circuit without the start-up block.

## Lab

### Circuit

The circuit used for the simulation is shown below.

<img width="800" alt="Complete BGR circuit used in transient simulation" src="https://github.com/user-attachments/assets/6a420903-2df9-47f8-b247-97e4035350a8" />

### Transient simulation

The power supply Vdd is varied from 0 to 2 V with a rise time of 1 µs.

**1. Vdd and Vref**

<img width="800" alt="Vdd and Vref vs time" src="https://github.com/user-attachments/assets/70d896b5-5c38-402c-87fe-597b7104e3c8" />

Vref starts to rise just before 1 µs, reaches 1.12 V at around 1.1 µs, and settles there. The start-up time is hence around 1.1 µs.

**2. Vdd, net1 and net2**

<img width="800" alt="Vdd, net1 and net2 vs time" src="https://github.com/user-attachments/assets/499d7cc8-c1a1-432d-811f-f5090dc3fc5a" />

V(net2) follows Vdd, but at around 1 µs it starts to drop. Meanwhile V(net1) rises, and the two meet at the same voltage of 1.325 V at around 1.4 µs. At this point the start-up circuit is isolated.

**3. Vdd, net2 and net6**

<img width="800" alt="Vdd, net2 and net6 vs time" src="https://github.com/user-attachments/assets/b772902a-c93b-49fa-855e-4be8f219345a" />

Both V(net2) and V(net6) rise as Vdd rises, but with a difference between them. Once this difference reaches around 0.6 V (close to 1 µs in the plot above), the start-up circuit turns on. The voltage at net2 then decreases while net6 keeps increasing. Once V(net2) is equal to V(net1), the start-up circuit turns off (isolated) and all the nodes settle at a fixed value.

**4. Current through MP6**

<img width="800" alt="Current through MP6 vs time" src="https://github.com/user-attachments/assets/9f6686fb-6b1b-45bd-97c7-ce51337670aa" />

This is the current responsible for the start-up current in the BGR.

**5. Current through the start-up circuit after isolation**

<img width="800" alt="Start-up circuit current after isolation" src="https://github.com/user-attachments/assets/594b63b5-e2f8-493e-b786-57fb272412bd" />

**6. Transient analysis without the start-up circuit**

<img width="800" alt="Transient response without the start-up circuit" src="https://github.com/user-attachments/assets/396a4851-6196-48c3-bdf4-f0a96c7cc3f9" />

Without the start-up circuit, net2 stays very close to Vdd and net1 stays very close to ground, so we get very little or no Vref from the BGR.
