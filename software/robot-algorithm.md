# Obstacle Avoidance Algorithm

## Objective

Enable the robot to navigate autonomously while avoiding obstacles using an HC-SR04 ultrasonic sensor mounted on an SG90 servo motor.

---

# High-Level Algorithm

1. Move forward.
2. Measure the distance in front of the robot.
3. If the measured distance is greater than the safety threshold:
   - Continue moving forward.
4. Otherwise:
   - Stop.
   - Rotate the servo to the left.
   - Measure and store the left distance.
   - Rotate the servo to the right.
   - Measure and store the right distance.
   - Return the servo to the center position.
   - Compare the measured distances.
   - Turn toward the side with greater free space.
   - Resume forward movement.

---

# Decision Parameters

| Parameter| Value |
|----------|-------|
| Safe Distance | 20 cm |
| Scan Directions | Left, Right |
| Sensor | HC-SR04 |
| Servo | SG90 |

---

# Future Algorithm Improvements

- Dynamic obstacle distance threshold
- Speed adjustment based on obstacle distance
- Smoother turning behavior
- Path memory
- Dead-end detection
- AI-assisted navigation

---

# Pseudocode

,,,

    loop:
      move_forward()
   
    distance = measure_front()

    if distance > SAFE_DISTANCE:
        continue

    stop()

    left = scan_left()
    right = scan_right()

    if left > right:
        turn_left()
    else:
        turn_right()

    move_forward()
    
,,,

---

Implementation Status

- [x] Algorithm designed
- [ ] Arduino implementation
- [ ] Hardware testing
- [ ] Performance optimization
