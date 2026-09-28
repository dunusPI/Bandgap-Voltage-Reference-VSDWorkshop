# Day 4: Self-Biased Current Mirror

**Concepts covered:** Self-biased current mirror: principle, why self-bias, supply independence, and SPICE simulation in the lab.

## Why a Self-Biased Current Mirror?

A reference generation circuit must also be independent of the supply voltage, in addition to process and temperature. The temperature dependency is taken care of by the CTAT and PTAT voltage generation circuits.

These circuits require a constant current source to work, as established earlier. This current must also be supply independent, so we take the help of CMOS current mirrors.

## Issues with Normal Current Mirrors

<img width="800" alt="Normal current mirror" src="https://github.com/user-attachments/assets/b542b0d2-304b-4fc0-b203-fab244c86686" />

As seen above, the current Iout varies with variations in the supply voltage Vdd, which is an undesirable result.

For a less sensitive solution, the circuit should bias itself, i.e. Iref must be derived from Iout.

## Self-Biased Current Mirror

<img width="506" alt="Self-biased current mirror" src="https://github.com/user-attachments/assets/aa2e956a-a14f-437e-bf34-d4e48a0bb2d6" />

In the topology above, we replicate Iout to be Iref. Here Mp1 and Mp2 replicate Iout and define Iref. We call this bootstrapping.

Since each diode-connected device is fed from a current source, Iout and Iref are relatively independent of the supply.

### Issues with the above topology

1. The circuit can support any current value.
2. There is a problem of start-up.

The first issue can be tackled by adding a resistor Rs to MN2, as shown below.

<img width="528" alt="Self-biased current mirror with Rs" src="https://github.com/user-attachments/assets/1cbff47b-38d9-4968-a86b-23ce07c27253" />

Here Rs defines a unique current level, and the gain of this circuit is less than one, hence it is stable. Below is the equation for Iout in terms of Rs.

<img width="660" alt="Iout equation in terms of Rs" src="https://github.com/user-attachments/assets/f4a49ae5-02b0-433b-99ba-168dc8998b28" />

The second issue will be dealt with later.

## Advantages and Limitations of the Self-Biased Current Mirror

<img width="800" alt="Advantages and limitations" src="https://github.com/user-attachments/assets/3173adc4-f94f-4d1a-9ffe-4b583861ff09" />

