# Day 1: Introduction to Bandgap Voltage Reference

**Concepts covered:** Introduction to bandgap voltage reference, its applications, the principle of BGR, and the components of a BGR.

## Introduction to Bandgap

<img width="700" alt="Introduction to bandgap" src="https://github.com/user-attachments/assets/18a9d09f-21ad-4d40-b9ad-f8c8a8aa143b" />

A BGR is a circuit that provides a reference voltage that stays constant regardless of PVT (process, voltage, temperature) variations.

It is called a bandgap voltage reference because, as the temperature tends to 0 K, the output voltage of the BGR extrapolates to about 1.2 V, which is close to the bandgap energy of silicon.

## Why BGR?

- A battery loses voltage over the time of its usage, so it is not suitable where a fixed reference is needed.
- A power supply gives a noisy output with ripple.
- A voltage reference IC with a Zener diode is viable, but it is external, needs additional resistors and capacitors to change the voltage, and is not useful for low-voltage applications.

A BGR is useful because it can be integrated into any process technology (CMOS, BiCMOS, Bipolar) without the need for external components.

## Applications of BGR

**1. Low Dropout Regulators**

<img width="450" alt="LDO" src="https://github.com/user-attachments/assets/b7a2440c-beae-4c51-9d3a-c097ccb22d68" />

**2. DC-DC Buck Converters**

<img width="550" alt="DC-DC buck converter" src="https://github.com/user-attachments/assets/298cf9a6-54a0-4e61-be88-e8cff73a24b5" />

**3. Analog to Digital Converters**

<img width="450" alt="ADC" src="https://github.com/user-attachments/assets/320aeb0f-1ce7-40aa-96fe-d78fb2a5dc5c" />

**4. Digital to Analog Converters**

<img width="600" alt="DAC" src="https://github.com/user-attachments/assets/1fdf696b-479d-4bde-8677-a46c1a677bb4" />

## Bandgap Voltage Reference Principle

<img width="700" alt="BGR principle" src="https://github.com/user-attachments/assets/65aec3aa-10c8-4006-844c-7a6702b7021c" />

The BGR consists of a CTAT voltage generation circuit, which has a negative temperature coefficient, and a PTAT voltage generation circuit, which has a positive temperature coefficient. When both are combined by a summing circuit, we get a voltage that remains constant regardless of temperature.

## BGR Types

<img width="700" alt="BGR types" src="https://github.com/user-attachments/assets/87c931cc-d5bc-4d7f-993c-5e1e6bcec805" />

### Self-biased current mirror based BGR: advantages and limitations

<img width="650" alt="Self-biased current mirror BGR" src="https://github.com/user-attachments/assets/070c3358-e271-4b35-82e2-9534933543b4" />

## Components of BGR

<img width="600" alt="Components of BGR" src="https://github.com/user-attachments/assets/013ba6bf-3a5c-4e3a-80a5-39ce5dbcdc70" />
