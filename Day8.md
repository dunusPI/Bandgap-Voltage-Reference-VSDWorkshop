# Day 8: Complete BGR Pre-layout Simulation(Lab 7 Component)

**Concepts covered:** Process corners (tt, ff, ss), and pre-layout simulation of the complete bandgap voltage reference across these corners.

## Process Corners: tt, ff and ss

No two chips are manufactured identically. Small variations in the fabrication process (doping, oxide thickness, channel length and width, etc.) shift the transistor parameters from their nominal values. This is the "P" in PVT. To make sure a circuit still works under these variations, foundries provide **process corners**, which are sets of device models representing the extremes of the manufacturing spread.

The two letters in a corner name refer to the NMOS and PMOS respectively:

| Corner | NMOS | PMOS | Meaning |
|--------|------|------|---------|
| **tt** | Typical | Typical | Nominal process, the expected average behaviour |
| **ff** | Fast | Fast | Both devices are at the fast extreme |
| **ss** | Slow | Slow | Both devices are at the slow extreme |

**Fast devices** (ff) typically have a lower threshold voltage and higher carrier mobility, so they drive more current for the same bias.

**Slow devices** (ss) typically have a higher threshold voltage and lower carrier mobility, so they drive less current for the same bias.

There are also skewed corners, fs and sf, where one device type is fast and the other slow. They are not used in this lab.

### Why corners matter for a BGR

A bandgap reference is meant to be insensitive to PVT variations, so it has to be verified across corners as well as across temperature. In each corner the mirror transistors, and depending on the PDK the resistors and BJTs, take slightly different values. This shifts the bias current and the CTAT/PTAT balance, and therefore the shape of the Vref vs temperature curve and its temperature coefficient. The simulations below compare Vref across the three corners.

## Lab 7 Component

### Circuit

The circuit used for the simulation is shown below.

<img width="705" alt="Complete BGR circuit used in pre-layout simulation" src="https://github.com/user-attachments/assets/3df82928-4f13-4a88-93dc-e84164c62d75" />

### SPICE code

The SPICE code is given below, spread over three images.

<img width="800" alt="SPICE code, part 1" src="https://github.com/user-attachments/assets/e2bd93d3-7d28-402d-bda4-3dabc3b2f1ce" />

<img width="800" alt="SPICE code, part 2" src="https://github.com/user-attachments/assets/883d7284-b86b-4332-bfb5-6ed67665892b" />

<img width="822" alt="SPICE code, part 3" src="https://github.com/user-attachments/assets/1bd800de-d0d8-4f02-9011-c4201668245a" />

### Simulation performed

DC simulation of Vref vs temperature, comparing the tt, ff and ss corners.

### DC simulation: tt vs ff vs ss corner

**tt corner**

<img width="800" alt="Vref vs temperature, tt corner" src="https://github.com/user-attachments/assets/4846b3b4-3043-48c1-b7de-dda70268e04f" />

The temperature coefficient for this corner is 25 ppm/°C (from my calculation).

**ff corner**

<img width="800" alt="Vref vs temperature, ff corner" src="https://github.com/user-attachments/assets/8d7ce6e5-f508-4a17-afcc-af0710ce97ad" />

The temperature coefficient for this corner is 10 ppm/°C. This is the best compensated of the three corners, with the lowest ppm.

**ss corner**

<img width="800" alt="Vref vs temperature, ss corner" src="https://github.com/user-attachments/assets/9b96ee82-2395-48ef-80b6-1a78ec957e98" />

The temperature coefficient for this corner is 45 ppm/°C, the highest of the three corners.

### Summary

| Corner | Temperature coefficient |
|--------|-------------------------|
| tt | 25 ppm/°C |
| ff | 10 ppm/°C |
| ss | 45 ppm/°C |

    
   

   
   





