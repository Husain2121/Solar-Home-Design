#  Solar-Powered Home Simulation in MATLAB Simulink

This repository contains my personalized MATLAB Simulink model of a solar-powered residential system, developed after following the tutorial “Solar-Powered Home in Simulink” on YouTube.

##  What was built  
- A working Simulink model replicating a solar-powered home system with generation, load, and energy conversion and boost components.
- Custom enhancements to the tutorial model, including improved load profiles and explanation of system process.

## How it works
<details> <summary>1. Solar Panels (PV Array)</summary>
Converts sunlight into DC electricity via the photovoltaic effect.

Temperature affects the semiconductor band gap, which changes the energy needed to release electrons.

</details> <details> <summary>2. DC Output</summary>
Electrons flow in a single direction, producing direct current (DC).

</details> <details> <summary>3. Capacitor (Ripple Reduction)</summary>
Smooths voltage fluctuations from the solar panel output and protects other circuit components.

</details> <details> <summary>4. Boost Converter</summary>
Switch Closed (IGBT/Diode ON) → Current flows through the inductor, storing energy in its magnetic field.

Switch Open → Inductor releases stored energy (acting like a “second battery”), boosting voltage before charging the capacitor.

Controlled by a 50% duty cycle pulse generator to regulate switching.

</details> <details> <summary>5. Inverter</summary>
Converts DC to AC using diodes or IGBT switches.

Pulse Width Modulation (PWM) shapes the waveform into a smoother sine wave.

</details> <details> <summary>6. Passive Filter (LC)</summary>
Removes high-frequency components from the waveform, producing a clean AC sine wave.

</details> <details> <summary>7. Load (Resistor)</summary>
Represents the AC power consumption of the home.

</details>

## Why it works
<details> <summary>1. Solar Panels (PV Array)</summary>
Solar panels require irradiance (sunlight) to function. They use sunlight as an energy source, allowing photons to transfer energy to electrons, generating current via the photovoltaic effect.

Temperature effect: Temperature influences the band gap energy of semiconductor materials, which determines how much energy is needed to release electrons.

</details> <details> <summary>2. Direct Current (DC) Generation</summary>
When electrons are released in the semiconductor material, they flow in a single direction, producing direct current (DC).

</details> <details> <summary>3. Capacitor (Ripple Reduction)</summary>
The capacitor smooths voltage fluctuations and protects other components in the circuit.

It reduces the ripple factor caused by the varying supply from the solar panel.

</details> <details> <summary>4. Boost Converter</summary>
Switch Closed (IGBT/Diode ON): Current passes through the inductor, storing energy in its magnetic field.

Switch Open: The current decreases through the inductor, and to oppose the change, the voltage across the inductor rises rapidly.

This voltage combines with the input voltage to forward-bias the diode, charging the capacitor.

The capacitor then provides a stepped-up DC voltage to the load.

The pulse generator runs at a 50% duty cycle, controlling the IGBT switching for voltage boosting.

</details> <details> <summary>5. Inverter</summary>
The inverter converts DC to AC using a configuration of diodes or IGBT switches.

Current alternates between two paths to produce an AC square wave.

Pulse Width Modulation (PWM) smooths the waveform into a sine wave.

</details> <details> <summary>6. Passive Filter (LC)</summary>
An inductor-capacitor (LC) filter removes unwanted high-frequency components, producing a pure AC sine wave from the PWM output.

</details> <details> <summary>7. Load (Resistor)</summary>
A resistor represents the AC load that consumes the delivered power.

</details>

## Tools and Components
**Design Software:** MATLAB Simulink

**Component Values and Amount:** Inductor - 0.02H (x2), Capicitor - 0.006F (x3), Resistor - 1 Ω (x1), Diode - 0.8Vf (x1), IGBT/Diode (x1), Inverter (x1), PWM Generator 2-Level (x1), Pulse Generator (x1), Voltage Reader (x3), and Scope (x3)

## Results
**Output Waveforms:** 1st Waveform (after solar array) - 120V DC. 2nd Waveform(after boost converter) - 240V DC. 3rd Waveform (after inverter and passive filter) - 240V AC. 
## Acknowledgement
Based on the tutorial video by [Solar-Powered Home in Simulink](https://www.youtube.com/watch?v=RQcMuLC8_DE). Big thanks for the clear walkthrough. I used it as a foundation, then added custom improvements.

## Improvements
While the base model follows the tutorial, I made small changes to enhance clarity and usability:
- Added descriptive comments and signal labels
- Organized blocks into subsystems for better readability
