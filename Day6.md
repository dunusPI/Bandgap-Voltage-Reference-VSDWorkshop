# Day 6: Start-up Circuit

**Concepts covered:** Why a start-up circuit is needed in a self-biased current mirror, and how the start-up circuit works.

## Why Start-up?

<img width="800" alt="Start-up circuit" src="https://github.com/user-attachments/assets/4b8f43c1-afef-4d81-8ffb-702f347cf190" />


In a self-biased current mirror there exist degenerate points, which occur when all the transistors in the current mirror circuit are off. In this state no current flows through the circuit, and nothing pushes it out of that state on its own. This is called the start-up problem.

To fix it, a start-up circuit (MP4, MP5 and MN3 in the dashed box above) is added to the BGR. Its job is to inject a small current into the core circuit at power-up, so the circuit leaves the zero-current state and settles at the intended operating point.

## Working of the Start-up Circuit

- Initially, the circuit current is zero.
- net2 follows VDD.
- When the net2 voltage is one Vt (threshold voltage) more than the net6 voltage, current flows through MP5 and pulls the net1 node voltage up.

Once net1 rises, the NMOS mirror devices (MN1 and MN2) turn on. This makes the self-biased loop start conducting, and the circuit moves to its normal operating point.

## Start-up Circuit Turns Itself Off

Once the loop is running, the net2 voltage drops below the level needed to keep MP5 on. The start-up circuit then stops injecting current, so it does not disturb the BGR during normal operation.

## Lab

To be added soon.
