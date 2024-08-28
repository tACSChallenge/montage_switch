# montage_switch

This  contains the design for a TACS (Transcranial Alternating Current Stimulation) montage switch circuit. The circuit is designed to facilitate switching between three different stimulation montages - there are three different montages (combinations) for the tACS stimulation:


1. Occipital tACS (Condition A):
   * Negative pole: O1, Oz, and O2 (linked together)
   * Positive pole: CPz, CP5, and CP6 (linked together)

2. Retinal control stimulation (Condition B):
   * Negative pole: Two electrodes on the cheeks under the left and right eyes (linked together)
   * Positive pole: CPz, CP5, and CP6 (linked together)

3. Cutaneous control stimulation (Condition C):
   * Positive pole: Oz
   * Negative pole: O1 and O2 (linked together)

These three montages are designed to target different areas and serve different purposes in the experiment:
* Condition A targets the occipital cortex
* Condition B primarily stimulates the retina
* Condition C mainly stimulates the skin under the occipital electrodes

## Circuit Diagram

The circuit diagram provides a complete schematic for the TACS montage switch. Here are the key components and features:

1. BNC Input: Triggers the montage switching mechanism.
2. Debounce Circuit: Ensures clean trigger signals from the BNC input.
3. CD4017 Decade Counter: Controls the state of the montage selection.
4. CD4052 Multiplexers (3): Route the stimulation signals to the appropriate electrodes for each montage.
5. Stim+ and Stim- Inputs: Connect to the stimulation device.
6. Outputs: O1, Oz, O2, CPz, CP5, CP6, L Cheek, R Cheek for connecting to the electrodes.
7. Power Supply: VCC (+5V) and GND connections for powering the circuit components.

The circuit uses color-coded connections for easy signal tracing:
- Blue: Trigger signal
- Purple: Control signal
- Red: Stim+ signal
- Blue: Stim- signal
- Green: Output signal
- Dashed Purple: Extended control signal
- Dashed Red: VCC connection
- Dashed Black: GND connection

This design allows for automated switching between the three montages using BNC trigger pulses, facilitating efficient experimentation with different stimulation configurations.
![circuit](https://github.com/user-attachments/assets/49fad51c-54ec-4a39-b3e7-d51735917ae3)


## Implementation Notes

- The CD4017 counter advances with each BNC trigger pulse, cycling through the three montage states.
- The CD4052 multiplexers route the Stim+ and Stim- signals to the appropriate electrodes based on the current state.
- Proper isolation and safety measures should be implemented when connecting this circuit to stimulation devices and subjects.
- Additional features like current limiting and emergency stop functionality may be necessary for safety in a complete system.

## Signature
UH
