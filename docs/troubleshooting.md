# Troubleshooting Log 
This document records the major hardware and software issues encountered during the development of the obstacle-avoiding robot, along with the steps taken to diagnose and resolve them.

## Issue 1: Robot only worked while Arduino Nano was connected through USB

### Symptoms
- Robot worked when connected to a computer through USB.
- Robot stopped working when USB was disconnected.

### Investigation 
- Verified power wiring.
- Checked common ground connections.
- Tested the L298N power regulator.
- Confirmed the Arduino Nano received power from the motor driver.

### Result
The Nano was successfully powered, but the motor driver did not reliably drive the motors using the available battery supply.

## Issue 2: Motor failed to rotate correctly

### Symptoms
- Motors occasionally vibrated.
- Motors sometimes rotated only after being pushed by hand.
- One motor worked while the other remained stationary.

### Investigation
- Tested each motor individually.
- Swapped motor connections.
- Verified wiring continuity using a multimeter.
- Measured motor driver output voltage.
- Tested Arduino digital outputs.

### Results
Both BO gear motors were confirmed to be funtional.

## Issue 3: L298N Motor Driver Behavior

### Observations
- Intermitted motor operation.
- Inconsistant output voltage.
- Driver occasionally worked after power cycling.
- Manual testing of motor driver inputs produced expected motor direction changes.

### Conclusion 
Based on repeated testings, the L298N motor driver became the primary suspect. Since motors, Arduino Nano, wiring, and control signals verified independently, the project will continue with a TB6612FNG motor driver for comparision and further testing.

## Next Steps

- Replace the L298N motor driver with a TB6612FNG.
- Retest both BO motors using the new driver.
- Upgrade the power system to two 18650 Li-ion cells.
- Verify stable operation before implementing obstacle avoidance.
