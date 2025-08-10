#  Solar-Powered Home Simulation in MATLAB Simulink

This repository contains my personalized MATLAB Simulink model of a solar-powered residential system, developed after following the tutorial “Solar-Powered Home in Simulink” on YouTube.

##  What I Built  
- A working Simulink model replicating a solar-powered home system with generation, load, and energy conversion and boost components.
- Custom enhancements to the tutorial model, including improved load profiles and explanation of system process.

## How it works
1.Solar PV is dependent on irradiance(sunlight) and Temperature. 
2.PV array is providing the Direct Current( this our source). 
3.We have a capacitor attached in parallel. Since our 24 hour days are not all sunlight, we won’t have a constant supply. since the capacitor does not allow for the sudden changes, and protects the other circuit compents
4. The boost converter(inductor, switch, diode, and capacitor) will boost the DC voltage.
4b. Additionally, we have added a pulse generator to the IGBT/Diode swich (50% duty cycle)
5. Next, is the inverter which will allow for the DC to be converted to AC
6. Lastly, we have the resistive AC load that repersents our home

## Why it works
1. Solar panels require irradiance(sunlight) to function becuase they use the sunlight as an energy source to allow for the photons to transfer energy to the electrons to create a current via the photovoltaic effect. Temperature influences the "band gap" energy of semiconductor materials, which governs how much energy is required to release electrons.
2. When electrons are released in the semiconductor material, they flow in one direction classifying it as direct current (DC)
3. Since the capacitor does not allow for the sudden changes, and protects the other circuit components. The capacitor will reduce the ripple factor, as the supply from the solar panel is varying.
4. When the IGBT/Diode is closed, the current in the passing through the inductor is large. This stores the energy in magnetic field. However, when the switch is opened, the current decreases through the inductor. To oppose the change, the voltage across the inductor rises rapidly. This voltage(across inductor) combines with the input voltage to allow for the current to pass through the diode as it becomes foward-biased and thus charging the capacitor. The capacitor then charges the load with a higher voltage then the input voltage. **What is interesting is that when the switch is opened, the inductor's energy release acts as a "second battery". This allows for the capacitor to provide a stepped up DC voltage to the load.**


4.Now, we have our boost converter. This is comprised of an inductor, switch(IGBT/Diode) and a capacitor. 
## Acknowledgement
Based on the tutorial video by [Solar-Powered Home in Simulink](https://www.youtube.com/watch?v=RQcMuLC8_DE). Big thanks for the clear walkthrough. I used it as a foundation, then added custom improvements.

## Improvements
While the base model follows the tutorial, I made small changes to enhance clarity and usability:
- Added descriptive comments and signal labels
- Organized blocks into subsystems for better readability
