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
5. Next, is the inverter which will allow for the DC to be converted to AC.
5b. Also, there is PWM generator to allow for the inverter to have the rapidly switching mechanism.
6. The AC voltage is then passed through a passive filter.
7. Lastly, we have the resistive AC load that repersents our home.

## Why it works
Key Stages & Components
Solar Panels (PV Array) – Converts sunlight into DC electricity via the photovoltaic effect. Temperature affects the semiconductor band gap, influencing electron release and overall efficiency.

DC Output – Electrons flow in a single direction, producing direct current (DC).

Capacitor (Ripple Reduction) – Smooths voltage fluctuations from the solar output and protects circuit components.

Boost Converter –

Switch Closed (IGBT/Diode ON): Current flows through the inductor, storing energy in its magnetic field.

Switch Open: Inductor releases stored energy (acting like a “second battery”), boosting voltage before charging the capacitor.

Controlled by a 50% duty cycle pulse generator for regulated switching.

Inverter – Converts DC to AC using diodes or IGBT switches. Pulse Width Modulation (PWM) shapes the output into a smoother sine wave.

Passive Filter (LC) – Removes high-frequency components from the waveform, producing a clean AC sine wave.

Load (Resistor) – Represents the home’s AC power consumption.
## Acknowledgement
Based on the tutorial video by [Solar-Powered Home in Simulink](https://www.youtube.com/watch?v=RQcMuLC8_DE). Big thanks for the clear walkthrough. I used it as a foundation, then added custom improvements.

## Improvements
While the base model follows the tutorial, I made small changes to enhance clarity and usability:
- Added descriptive comments and signal labels
- Organized blocks into subsystems for better readability
