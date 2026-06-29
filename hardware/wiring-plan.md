# Wiring Plan

This document describes the wiring configuration of the obstacle-avoiding robot.

---

# Current Hardware

- Arduino Nano
- HC-SR04 Ultrasonic Sensor
- SG90 Servo Motor
- TB6612FNG Motor Driver (replacing L298N)
- 2× TT Gear Motors
- 2×18650 Li-ion Battery Pack

---

# Pin Connections

## Ultrasonic Sensor

| HC-SR04 | Arduino Nano |
|---------|--------------|
| VCC | 5V |
| GND | GND |
| TRIG | D9 |
| ECHO| D10 |

---

## Servo Motor

| Servo | Arduino Nano |
|-------|--------------|
| Signal | D11 |
| VCC | 5V |
| GND | GND |

---

## TB6612FNG Motor Driver

| TB6612FNG | Arduino Nano |
|-----------|--------------|
| PWMA | D5 (PWM) |
| AIN1 | D8 |
| AIN2 | D7 |
| PWMB | D6 (PWM) |
| BIN1 | D4 |
| BIN2 | D3 |
| STBY | 5V |
| VCC | 5V |
| VM | Battery + |
| GND | Common GND |

---

## Motors

| Motor | Driver Output |
|-------|---------------|
| Left Motor | A01 / A02 |
| Right Motor | B01 / B02 |

---

## Power Distribution

- 2×18650 Battery → TB6612FNG VM
- Arduino powered separately through USB during development.
- All grounds connected together.

---

## Notes

- The original design used an L298N motor driver.
- Due to inconsistent motor performance, the system is being upgraded to the TB6612FNG.
- Wiring diagrams and photos will be added after final assembly.
