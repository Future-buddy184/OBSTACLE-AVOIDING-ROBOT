# Robot Architecture

## System Overview

The robot consists of four primary subsystems:

1. Power System
2. Control System
3. Sensing System
4. Drive System

---

## Block Diagram

```
          +----------------------+
          |   2×18650 Battery    |
          +----------+-----------+
                     |
                     v
          +----------------------+
          |  TB6612FNG Driver    |
          +----------+-----------+
                     ^
                     |
          +----------+-----------+
          |    Arduino Nano      |
          +----+-----------+-----+
               |           |
               |           |
               v           v
        HC-SR04 Sensor   Servo Motor
               |
               v
      Distance Measurement

Arduino Nano
      |
      v
TB6612FNG
      |
      +----------------+
      |                |
      v                v
 Left Motor      Right Motor
```

---

## Subsystem Description

### Power System

- 2×18650 Li-ion battery pack
- Supplies power to the motor driver
- Arduino powered through regulated supply

---

### Control System

- Arduino Nano
- Reads sensor data
- Runs obstacle avoidance algorithm
- Controls motor driver

---

### Sensing System

- HC-SR04 Ultrasonic Sensor
- Mounted on servo motor
- Measures surrounding distances

---

### Drive System

- TB6612FNG Motor Driver
- Two BO gear motors
- Differential drive steering

---

## Data Flow

1. Ultrasonic sensor measures distance.
2. Arduino processes the readings.
3. Decision algorithm selects movement.
4. Motor driver receives control signals.
5. Motors move the robot.
6. Process repeats continuously.

---

## Planned Upgrades

- Bluetooth communication
- Camera module
- Computer vision
- AI-assisted navigation
- Additional sensors
