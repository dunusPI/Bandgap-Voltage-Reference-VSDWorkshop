Day 1- 
Concepts covered: Introduction to Bandgap Voltage Reference, its applications and the principles of BGR.


Introduction to bandgap
<img width="1350" height="763" alt="image" src="https://github.com/user-attachments/assets/18a9d09f-21ad-4d40-b9ad-f8c8a8aa143b" />
A BGR is a type of circuit that provides a reference voltage thats constant regardless of PVT(process, voltage, Temperature) variations
Its called Bandgap Voltage reference because, as the temperature tends to zero the output voltage of BGR is 1.2V which is close to the band gap energy of silicon


Why BGR?
A battery over the time of its usage it looses its voltage and drops, and hence not suitable to a reference voltage where there is a need for fixed reference.
A power supply is not suitable its gives a noisy output and ripples.
A voltage reference IC with a Zener diode is viable but its external and additional resistors and capacitors are required for changing voltage and not useful for low voltage applications.

A BGR is useful as it can be integrated into any process technologies with CMOS, Bi-CMOS, Bipolar without the need on external components

Applications Of BGR

1. Low Dropout regulators
   <img width="580" height="650" alt="image" src="https://github.com/user-attachments/assets/b7a2440c-beae-4c51-9d3a-c097ccb22d68" />

2. DC-DC Buck Converters
   <img width="721" height="605" alt="image" src="https://github.com/user-attachments/assets/298cf9a6-54a0-4e61-be88-e8cff73a24b5" />

3. Analog to Digital Converter
   <img width="556" height="615" alt="image" src="https://github.com/user-attachments/assets/320aeb0f-1ce7-40aa-96fe-d78fb2a5dc5c" />

4. Digital to Analog Converter
   <img width="761" height="484" alt="image" src="https://github.com/user-attachments/assets/1fdf696b-479d-4bde-8677-a46c1a677bb4" />

Bandgap Voltage Reference Principle
<img width="1241" height="730" alt="image" src="https://github.com/user-attachments/assets/65aec3aa-10c8-4006-844c-7a6702b7021c" />
The BGR consists of a CTAT voltage generation circuit, which shows a negative TC

   



