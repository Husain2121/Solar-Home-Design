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
<details> <summary>**1. Solar Panels (PV Array)**</summary>
Converts sunlight into DC electricity via the photovoltaic effect.

Temperature affects the semiconductor band gap, which changes the energy needed to release electrons.

</details> <details> <summary>**2. DC Output**</summary>
Electrons flow in a single direction, producing direct current (DC).

</details> <details> <summary>**3. Capacitor (Ripple Reduction)**</summary>
Smooths voltage fluctuations from the solar panel output and protects other circuit components.

</details> <details> <summary>**4. Boost Converter**</summary>
Switch Closed (IGBT/Diode ON) → Current flows through the inductor, storing energy in its magnetic field.

Switch Open → Inductor releases stored energy (acting like a “second battery”), boosting voltage before charging the capacitor.

Controlled by a 50% duty cycle pulse generator to regulate switching.

</details> <details> <summary>**5. Inverter**</summary>
Converts DC to AC using diodes or IGBT switches.

Pulse Width Modulation (PWM) shapes the waveform into a smoother sine wave.

</details> <details> <summary>**6. Passive Filter (LC)**</summary>
Removes high-frequency components from the waveform, producing a clean AC sine wave.

</details> <details> <summary>**7. Load (Resistor)**</summary>
Represents the AC power consumption of the home.

</details>
## Acknowledgement
Based on the tutorial video by [Solar-Powered Home in Simulink](https://www.youtube.com/watch?v=RQcMuLC8_DE). Big thanks for the clear walkthrough. I used it as a foundation, then added custom improvements.

## Improvements
While the base model follows the tutorial, I made small changes to enhance clarity and usability:
- Added descriptive comments and signal labels
- Organized blocks into subsystems for better readability
