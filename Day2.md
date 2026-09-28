Concepts Covered: CTAT Voltage generation circuit-- principles, design equations, and Spice simulation for labs

CTAT Voltage generation circuits

<img width="996" height="409" alt="image" src="https://github.com/user-attachments/assets/9fa99801-dd5d-4f4b-95ab-52cf0afb6f4d" />

As in principle a CTAT voltage generation circuits can be made with a electronic device which shows negative temperature coefficient. Above are shown two methods, one with a normal diode and other with a diode connected BJT.
Diode connected BJTs are prefered because of their ease in manufacturing and fabrication process. 
As shown below,
For a diode, below is the fabrication structure
<img width="530" height="307" alt="image" src="https://github.com/user-attachments/assets/9b42be5e-3d1e-44c9-9095-c8448ab5a8cf" />
In fab process we generally make the P-Sub as the ground, and hence diode structure is not possible here
We go with BJT as diode as the ease of integrating its structure with the CMOS process as shown below
<img width="871" height="359" alt="image" src="https://github.com/user-attachments/assets/95fcc764-8797-4489-97b1-b9e56c9a06d6" />
The above image also shows that the current from emitter to collector is not affected by current from emitter to base.

Showing the negative temperature coefficients
<img width="1344" height="755" alt="image" src="https://github.com/user-attachments/assets/debdcf61-3452-4d45-bb79-62b4b6e93b70" />
As seen from above the PN junction between the Emitter and base provides the negative temperature coefficient.
<img width="452" height="145" alt="image" src="https://github.com/user-attachments/assets/c9b8b6f2-bea1-4e81-b276-8cdcb1675376" />
This formula gives for Vt=700mV and T=300k the TC is around -1.9mV/K

Variation of the Slope with respect to number of transistors
<img width="1215" height="348" alt="image" src="https://github.com/user-attachments/assets/11e58caa-7a82-421a-8ae1-3fce84c07cde" />
The more the number of transistors more 

