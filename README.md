This Arduino code is designed to control a two-wheeled robot that can move forward, backward, left, or right based on input from two sensors. The robot uses an H-bridge motor driver to control the direction and speed of the motors.

### Code Explanation

1. **Pin Definitions:**
   - The pins connected to the motor driver's inputs (`in1`, `in2`, `in3`, `in4`) and the enable pins (`enA`, `enB`) are defined.
   - `in1` and `in2` control one motor, while `in3` and `in4` control the other.
   - The `enA` and `enB` pins are used to control the speed of the motors using PWM (Pulse Width Modulation).

2. **Speed Variables:**
   - `M1_Speed` and `M2_Speed` are the speeds of the motors when moving forward or backward.
   - `LeftRotationSpeed` and `RightRotationSpeed` are used for turning left or right, potentially at different speeds.

3. **Setup Function:**
   - The setup function initializes the motor control pins as outputs.
   - The sensors connected to analog pins `A0` and `A1` are initialized as inputs.

4. **Loop Function:**
   - The main loop reads the values from the left and right sensors.
   - Based on the sensor readings, it decides whether the robot should move forward, turn left, turn right, or stop.
   - Sensor readings are printed to the serial monitor for debugging purposes.

5. **Movement Functions:**
   - `front()`: Moves the robot forward.
   - `back()`: Moves the robot backward.
   - `right()`: Turns the robot right by setting the motors to spin in opposite directions or at different speeds.
   - `left()`: Turns the robot left by setting the motors to spin in opposite directions or at different speeds.
   - `Stop()`: Stops all motor activity by setting all motor pins to LOW.

### Sensor Logic:
- The robot has two sensors:
  - If both sensors detect nothing (`LEFT_SENSOR == 0 && RIGHT_SENSOR == 0`), the robot moves forward.
  - If only the left sensor detects something (`LEFT_SENSOR == 1`), the robot turns right.
  - If only the right sensor detects something (`RIGHT_SENSOR == 1`), the robot turns left.
  - If both sensors detect something, the robot continues to move forward.

### Use Case:
This code can be used in a simple line-following or obstacle-avoiding robot, where sensors are used to detect the presence of a line or obstacle, and the robot adjusts its direction accordingly. The motor speed and direction are controlled through the H-bridge, allowing for smooth and controlled movements.
