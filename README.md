h

>⩊<  TWO-WHEELED SELF-BALANCED ROBOT WITH ARDUINO      >⩊<  

・・・・


・・・・・・・・・・


・・・・・・・・・・・・・・・


・・・・・・・・・・・・・・・・・・・・


・・・・・・・・・・・・・・・・・・・・・・・・・


・・・・・・・・・・・・・・・・・・・・・・・・・・・・・・



![image alt](https://github.com/BenkhiraAhmedBaderEddine1/A-two-wheeled-self-balancing-robot-with-an-Arduino/blob/354edce1c81626b03f01c1e5464b5f6d2d65f731/photo_2026-10-10_20-07-09.jpg)




・・・・・・・・・・
・・・・・・・・・・
・・・・・・・・・・
![image alt](https://github.com/BenkhiraAhmedBaderEddine1/A-two-wheeled-self-balancing-robot-with-an-Arduino/blob/4be9c890e0d06a799f6e3fac5e0ee70fd9792f87/photo_2026-10-10_20-06-58.jpg)



・・・・・・・・・・
・・・・・・・・・・
・・・・・・・・・・

![image alt](https://github.com/BenkhiraAhmedBaderEddine1/A-two-wheeled-self-balancing-robot-with-an-Arduino/blob/354edce1c81626b03f01c1e5464b5f6d2d65f731/photo_2026-10-10_20-06-54.jpg)



・・・・・・・・・・
・・・・・・・・・・
・・・・・・・・・・


ABSTRACT

  The Two-Wheeled Self-Balanced Robot with Arduino is a small mobile robotic system designed to maintain its upright position using real-time feedback control. Unlike a conventional four-wheeled robot, which is naturally stable on a flat surface, a two-wheeled robot is dynamically unstable and must continuously adjust its wheel motion to prevent falling.
The main objective of this project is to design, assemble, program, and test a self-balancing robot using an Arduino-compatible microcontroller, an inertial measurement unit (IMU), two geared DC motors, and a motor driver. The MPU6050 sensor measures acceleration and angular velocity, allowing the system to estimate the inclination of the robot's body. The Arduino processes these measurements and calculates the corrective motor response using a PID controller.
A complementary filter combines accelerometer and gyroscope measurements to obtain a more useful estimate of the robot's tilt. The PID controller compares the estimated angle with the desired upright angle and generates a control signal. This signal is applied to the motors through an H-bridge driver, moving the wheels forward or backward to restore balance.
The project demonstrates important engineering concepts, including embedded programming, sensor fusion, feedback control, motor control, mechanical assembly, and experimental system tuning. It also provides a platform for future development, such as wireless control, wheel encoders, obstacle detection, and autonomous navigation.
The project is educationally valuable because it combines theoretical knowledge with practical implementation. However, successful balancing depends on correct electrical connections, mechanical design, sensor orientation, motor polarity, battery performance, and PID parameter tuning.
Keywords: Self-balancing robot, Arduino, C++, PID controller, MPU6050, gyroscope, accelerometer, DC motor, feedback control, robotics.

TABLE OF CONTENTS


  1. General Introduction
  2. Problem Statement
  3. Project Aim
  4. Project Objectives
  5. Project Scope
  6. Project Motivation and Importance
  7. Background and Related Concepts
  8. General Description of the Robot
  9. Working Principle
  10. System Architecture
  11. Hardware Components
  12. Software Requirements
  13. Mechanical Design and Assembly
  14. Electrical Connections and Wiring
  15. Mathematical Model of the Robot
  16. Sensor Measurement and Angle Estimation
  17. Complementary Filter
  18. PID Control Theory
  19. PID Parameter Tuning
  20. System Algorithm and Flowchart
  21. Complete Arduino C++ Program
  22. Explanation of the Program
  23. Implementation and Calibration Procedure
  24. Testing and Experimental Evaluation
  25. Results and Discussion
  26. Advantages of the Project
  27. Disadvantages and Limitations
  28. Safety Considerations
  29. Common Problems and Troubleshooting
  30. Future Improvements
  31. Applications
  32. Project Cost and Budget Considerations
  33. Project Management and Work Plan
  34. Conclusion
  35. References
  36. Appendices



CHAPTER 1: GENERAL INTRODUCTION


1.1 Introduction


  Robotics is an important branch of modern engineering that combines mechanical systems, electronic circuits, sensors, actuators, control theory, and computer programming to create machines capable of performing useful tasks.
Robots are used in manufacturing, healthcare, transportation, education, agriculture, logistics, and many other fields. As robotic systems become more advanced, there is increasing interest in machines that can move efficiently while maintaining stability.
A self-balancing robot is an example of a dynamically controlled robotic system. It uses sensors and a feedback controller to maintain its body in an upright position despite disturbances.
The two-wheeled self-balancing robot is particularly interesting because its mechanical structure resembles an inverted pendulum. Its centre of mass is located above the axle, and the robot cannot remain upright without continuous correction.
The robot therefore needs to measure its inclination, calculate the required correction, and move its wheels in the appropriate direction.
In this project, an Arduino microcontroller performs the main control operations. An MPU6050 sensor provides acceleration and angular velocity measurements, while two DC motors produce the corrective movement.
A PID controller is used to calculate the motor command from the difference between the desired angle and the measured angle.
The project is a practical demonstration of how mathematical models and control algorithms can be implemented in a real embedded system.


1.2 Problem Statement


  A two-wheeled robot has a fundamental stability problem: its narrow support line does not provide passive balance.
If the robot tilts forward, gravity creates a rotational tendency that causes it to fall. If the robot tilts backward, the same problem occurs in the opposite direction.
A manually controlled robot cannot reliably correct these movements quickly enough. The system therefore requires automatic feedback.
The main engineering problem is:
How can a low-cost microcontroller use sensor measurements and a suitable control algorithm to continuously adjust two motor speeds and maintain the upright position of a two-wheeled robot?
This problem includes several technical challenges:
- Measuring the inclination of the robot accurately.
- Combining noisy sensor measurements.
- Calculating the correct control response.
- Driving two motors with suitable speed and direction.
- Reducing oscillations and overshoot.
- Handling battery-voltage variations.
- Preventing unstable motor commands when the robot falls.
- Achieving reliable operation with limited computing resources.
The project addresses these challenges through sensor fusion, PID control, and systematic experimental calibration.


1.3 Project Aim


  The primary aim is to design, construct, program, and evaluate a two-wheeled self-balancing robot using Arduino and a PID-based feedback control system.


1.4 Project Objectives


  The specific objectives are:
    1. Design a compact two-wheeled robotic platform.
    2. Assemble the chassis, motors, wheels, battery, and electronic components. 
    3. Connect an MPU6050 sensor to the microcontroller using I²C communication.
    4. Read accelerometer and gyroscope data in real time.
    5. Estimate the robot's tilt angle using a complementary filter.
    6. Implement a PID controller in C++.
    7. Control motor direction and power using a dual H-bridge driver.
    8. Determine the correct sensor axes and motor polarity.
    9. Tune the controller to reduce the robot's inclination and oscillation.
    10. Evaluate the robot using repeatable experimental tests.
    11. Identify the system's limitations and propose future improvements.


1.5 Project Scope

The project focuses on balancing the robot in one main plane: forward and backward.

The reference implementation includes:
    - Tilt sensing.
    - Gyroscope-based angular-rate measurement.
    - Complementary filtering.
    - PID control.
    - Two DC motor outputs.
    - Pulse-width modulation (PWM).
    - Basic fallen-robot protection.
    - Serial debugging and calibration.

The basic implementation does not include automatic navigation, obstacle avoidance, or a complete wheel-position controller. These can be added in later versions.


1.6 Project Motivation and Importance


  The main motivation is to demonstrate the practical relationship between electronics, programming, mechanics, and control engineering.
The project is important for several reasons.
First, it introduces students to real-time embedded systems, in which the controller must repeatedly read sensors and update outputs within a limited time.
Second, it demonstrates closed-loop control. Rather than sending a fixed motor command, the robot continuously measures its condition and adjusts its response.
Third, it introduces sensor fusion, a technique used in drones, mobile robots, and many navigation systems.
Fourth, it provides practical experience with C++ programming, electrical wiring, PWM motor control, and experimental debugging.
Finally, the robot provides a foundation for more advanced robotics projects involving autonomous movement, wireless communication, and intelligent control.


CHAPTER 2: BACKGROUND AND RELATED CONCEPTS
 
 
 
  2.1 What Is a Self-Balancing Robot?
  
  A self-balancing robot is a robotic system that automatically maintains its balance by controlling its movement in response to changes in its body orientation.
A two-wheeled self-balancing robot has two wheels positioned on the same axle. Unlike a conventional wheeled robot, it cannot remain upright while stationary unless its control system continuously compensates for disturbances.
The robot moves its wheels beneath its centre of mass to reduce the inclination of its body.


  2.2 The Inverted Pendulum
  
  The fundamental physical model of the robot is the inverted pendulum.
An ordinary pendulum hangs below its pivot and returns naturally toward its lowest position after a small disturbance. An inverted pendulum has its mass above its pivot and is unstable without active control.
For the robot:


  - The body represents the pendulum.
  - The wheel axle acts as the pivot.
  - The wheels provide corrective motion.
  - The motors generate the torque needed to move the wheels.
  - The controller determines how the robot should react.


Simplified physical model

![image alt](https://github.com/BenkhiraAhmedBaderEddine1/A-two-wheeled-self-balancing-robot-with-an-Arduino/blob/78eb45064f3a3249232c3215cf17343dfc2532ca/Sch%C3%A9ma%20technique%20d%E2%80%99un%20robot%20%C3%A0%20deux%20roues.png)

Conceptual diagram: the body tilts by an angle θ while the wheels move to restore the upright position. This is a simplified model, not a mechanical drawing of the photographed chassis.



  2.3 Feedback Control


   Feedback control means that a system measures its actual state and uses the measurement to determine its next action.
In this project, the feedback loop operates as follows:
      1. The sensor measures the robot's motion.
      2. The Arduino estimates the tilt angle.
      3. The controller calculates the difference between the target and measured angles.
      4. The PID algorithm calculates a correction.
      5. The motor driver applies the correction to the motors.
      6. The wheels move, changing the robot's position and angle.
      7. The sensor measures the new condition, and the process repeats.

This process occurs many times per second.


   2.4 Open-Loop and Closed-Loop Control

  An open-loop controller sends motor commands without measuring whether the robot is balanced. Such a system cannot reliably compensate for unexpected disturbances.
A closed-loop controller measures the robot's state and changes its output accordingly.
The self-balancing robot uses closed-loop control because its motor commands depend on sensor feedback.

  2.5 Role of Real-Time Processing

  Balancing requires a fast response. If the controller waits too long between measurements, the body may tilt too far before the motors react.
The control loop must therefore have predictable timing, sufficiently low sensor latency, and a suitable sampling frequency.
The reference program aims for a nominal sampling frequency of 200 Hz, corresponding to a period of approximately 5 milliseconds. Actual timing should be measured and checked during testing.


CHAPTER 3: GENERAL DESCRIPTION OF THE ROBOT

  3.1 Project Description

  The Two-Wheeled Self-Balanced Robot with Arduino is a compact mobile robot consisting of a mechanical chassis, two powered wheels, an inertial sensor, a microcontroller, a motor driver, and a battery supply.
The chassis supports the electronic components and motors. The MPU6050 measures acceleration and angular velocity. The Arduino uses these measurements to estimate the robot's inclination and calculates the corrective motor signal through a PID controller.
The motor driver converts the controller's low-power electrical signals into the motor current required to drive the wheels.
When the robot tilts forward, the control system commands the wheels to move in the direction needed to catch the falling body. When it tilts backward, the corrective direction is reversed.
The robot repeats this process continuously to maintain an approximately upright posture.

  3.2 Description of the Robot in the Photographs

The supplied photographs show a small two-wheeled robot with:
   - A compact chassis.
   - Two yellow wheels.
   - Geared DC motors.
   - A battery holder.
   - Electronic modules and connecting wires.
   - A controller or control-circuit assembly.

     
  The photographs also show a workbench with tools and electronic components, suggesting that the robot is being assembled and adjusted.
The photographs do not establish the exact model of every electronic component. The remaining report therefore distinguishes the proposed reference design from details that must be 
verified on the actual robot.

   3.3 Main Functional Units

  The robot can be divided into five main functional units.
     1. Mechanical unit: The chassis, wheels, motor brackets, and fasteners support the robot.
     2. Sensing unit: The IMU measures body acceleration and angular velocity.
     3. Processing unit: The Arduino executes the control algorithm.
     4. Actuation unit: The motor driver and DC motors produce the corrective movement.
     5. Power unit: The battery supplies the motors and the electronics through appropriate power connections.
   3.4 Expected Operating Behaviour

  When the robot is tilted slightly from its upright position, the sensor detects the change in orientation. The controller calculates the angle error and generates a motor command.
If the controller has been correctly configured, the wheels move to oppose the fall. The body should return toward the upright reference.
A properly tuned robot may balance for a period on a level surface. Its actual balancing duration, stability, and repeatability must be established experimentally.



CHAPTER 4: HARDWARE COMPONENTS

  
   4.1 Arduino Uno


  The Arduino Uno is the main processing unit in the reference design.
It is based on the ATmega328P microcontroller and provides digital input/output pins, PWM outputs, analog inputs, serial communication, and I²C communication.
Its responsibilities are to:
    - Communicate with the IMU.
    - Process the sensor measurements.
    - Estimate the tilt angle.
    - Calculate the PID output.
    - Control the motors.
    - Display debugging information through the Serial Monitor.

   The Arduino Uno is suitable for an educational implementation because it is widely supported and easy to program.
However, its processing power and memory are limited compared with more advanced controllers. The control loop should be kept efficient.

4.2 MPU6050 Accelerometer and Gyroscope

   The MPU6050 is a six-axis inertial measurement unit containing a three-axis accelerometer and a three-axis gyroscope.
The accelerometer measures acceleration along the X, Y, and Z axes. When the robot is stationary, gravity provides a reference for estimating its inclination.
The gyroscope measures angular velocity around the three axes. It responds quickly to rotational motion and helps the controller track rapid changes in orientation.
The two sensors have complementary strengths and weaknesses.



| Sensor        | Main advantage                                        | Main limitation                                          |
|---------------|-------------------------------------------------------|----------------------------------------------------------|
| Accelerometer | Provides a gravity-based inclination reference        | Sensitive to vibration and linear acceleration           |
| Gyroscope     | Responds quickly to rotational movement               | Integrated measurements drift because of bias            |
| Combined IMU  | Provides information for a more useful angle estimate | Requires correct orientation, filtering, and calibration |



The MPU6050 communicates with the Arduino through the I²C interface.
For a typical Arduino Uno connection, SDA is connected to A4 and SCL to A5.
The actual sensor breakout board's supply requirements must be checked before applying power.
4.3 DC Geared Motors
Two geared DC motors drive the wheels.
A gear reduction system increases the available output torque and reduces the rotational speed, which is useful for a balancing robot.
The motors should have enough torque to accelerate the wheels and correct the body's inclination.
Important motor characteristics include:
- Rated voltage.
- No-load speed.
- Stall current.
- Gear ratio.
- Available torque.
- Mechanical friction.
- Differences between the left and right motors.
The motor driver's current rating must be suitable for the motor stall current. A motor that draws excessive current can overheat the driver or cause the Arduino to reset.

4.4 Wheels

  The wheels convert motor rotation into movement of the robot.
The wheel diameter affects the distance travelled for a given motor rotation and influences the dynamics of the system.
Both wheels should have similar diameters, grip, and alignment.
Loose wheels, unequal tyres, or a bent axle can make balancing significantly more difficult.

4.5 L298N Motor Driver
    
  The L298N is a dual H-bridge motor driver capable of controlling the direction of two brushed DC motors.
The Arduino cannot directly supply the current required by most geared DC motors. The driver provides the necessary motor-current switching.
The L298N receives:
     - Direction signals from Arduino digital outputs.
     - PWM signals for controlling effective motor power.
     - Power from a suitable motor supply.

The module must be wired according to its actual terminal labels and board design.
An important limitation is that the L298N has a relatively high voltage drop and can dissipate considerable heat. A modern MOSFET-based driver may be a better choice when motor current and efficiency are important.
4.6 Battery and Power Supply

The battery provides energy for the motors and electronics.
The supply voltage must be appropriate for the motor ratings and driver requirements.
A battery that cannot provide sufficient current may experience voltage sag during acceleration. This can cause inconsistent motor performance, controller resets, or failed balancing 
attempts.

The power system should include:
    - A suitable battery pack.
    - Correct polarity.
    - Secure electrical connections.
    - A power switch.
    - A fuse or other suitable overcurrent protection.
    - A regulated logic supply where required by the selected hardware.
The motors should not be powered directly from the Arduino's 5 V pin.

4.7 Chassis and Mounting Hardware

  The chassis supports the motors, wheels, battery, controller, and sensor.
It must be sufficiently rigid to prevent excessive vibration and movement of the sensor.
The MPU6050 should be firmly attached to the chassis, and its axis orientation should be documented.
The battery should also be secured because a moving battery changes the centre of mass and may cause unstable behaviour.

4.8 Connecting Wires and Connectors

   Jumper wires and suitable connectors provide electrical connections between the controller, IMU, motor driver, motors, and power supply.
Loose connections can create intermittent sensor readings or sudden motor interruptions.
Motor wiring should be kept away from the sensor wiring where practical, and all connections should be checked before power is applied.

4.9 Optional Components

  The basic robot can be improved with the following components:
      - Wheel encoders for measuring wheel rotation.
      - A Bluetooth module for wireless commands.
      - A Wi-Fi-enabled controller for telemetry.
      - A battery-voltage monitoring circuit.
      - An emergency-stop switch.
      - A buzzer or status LEDs.
      - A distance sensor for obstacle detection.
      - A current sensor for monitoring motor load.
These components are not required for the reference program but can improve the robot's functionality.

CHAPTER 5: SOFTWARE REQUIREMENTS
5.1 Arduino IDE
The Arduino IDE is used to write, compile, and upload the C++ program to the microcontroller.
It also provides a Serial Monitor for displaying sensor values, controller output, and debugging messages.
5.2 Programming Language
The project uses C++ with the Arduino framework.
The program is divided into functions for initialization, sensor reading, angle estimation, PID calculation, motor control, and diagnostics.
This structure makes the program easier to understand and modify.
5.3 Required Libraries
For the reference implementation, install the following libraries through the Arduino IDE Library Manager:
1. Adafruit MPU6050
2. Adafruit Unified Sensor
3. Adafruit BusIO, if not installed automatically as a dependency.
The program also uses the built-in Wire library for I²C communication.
5.4 Software Development Process
The recommended process is:
1. Install the Arduino IDE.
2. Install the required sensor libraries.
3. Connect the Arduino to the computer using USB.
4. Select the correct board and serial port.
5. Upload a sensor-reading test.
6. Verify the sensor axes and angle calculations.
7. Test the motor directions with the wheels lifted.
8. Upload the balancing program.
9. Adjust the PID parameters.
10. Record the final test results.

CHAPTER 6: MECHANICAL DESIGN AND ASSEMBLY

   6.1 Mechanical Design Requirements
The mechanical structure should be rigid, compact, and symmetrical where possible.
The two wheels must be aligned on a common axle, and the motors should be mounted securely.
The robot's centre of mass affects its response to disturbances. A high centre of mass generally changes the system's dynamics and may make it more difficult to control.
The exact ideal arrangement depends on the motor torque, wheel size, body mass, and controller performance.

   6.2 Assembly Procedure

Step 1: Prepare the chassis.
Inspect the chassis for cracks, loose fasteners, and parts that may obstruct the wheels.

Step 2: Mount the motors.
Attach the left and right geared motors using suitable brackets or fasteners.

Step 3: Install the wheels.
Fit the wheels securely and confirm that they rotate freely without rubbing against the chassis.

Step 4: Install the battery holder.
Secure the battery holder so the battery cannot shift during movement.

Step 5: Mount the Arduino.
Attach the controller to the chassis using suitable mounting points. Protect the board from accidental contact with conductive surfaces.

Step 6: Mount the IMU.
Attach the MPU6050 firmly. Record which sensor axis corresponds to forward/backward rotation.

Step 7: Mount the motor driver.
Place the driver where it has adequate space for wiring and heat dissipation.

Step 8: Route the wires.
Keep all wires clear of the wheels, gears, and other moving components.

Step 9: Check the centre of mass.
Inspect the assembled robot and confirm that the battery and other components cannot move unexpectedly.

Step 10: Inspect the assembly.
Before applying power, check all screws, electrical connections, wheel clearances, and component mounting points.


8.2 Main Variables
The following variables are useful for understanding the system:



   6.3 Mechanical Considerations
 
   The robot's behaviour depends on more than its code.
For example, a loose sensor can produce inconsistent measurements. A flexible chassis can introduce vibration. Unequal wheels can cause the robot to drift. Excessively heavy components can exceed the motor's available torque.
Mechanical improvements should therefore be considered part of the control-system development.



CHAPTER 7: ELECTRICAL CONNECTIONS AND WIRING

 7.1 MPU6050 Connections

For a typical Arduino Uno reference setup:

| MPU6050 Pin | Arduino Uno Pin |
|---|---|
| VCC | 5V only if the breakout board supports it; otherwise use the specified supply voltage |
| GND | GND |
| SDA | A4 |
| SCL | A5 |


The MPU6050's I²C address and voltage requirements depend on the particular module configuration.
7.2 L298N Connections
The following table defines the pin assignments used in the reference code.

| Arduino Pin | L298N Connection | Function |
|---|---|---|
| D5 | ENA | Left motor PWM speed control |
| D7 | IN1 | Left motor direction control |
| D8 | IN2 | Left motor direction control |
| D6 | ENB | Right motor PWM speed control |
| D9 | IN3 | Right motor direction control |
| D10 | IN4 | Right motor direction control |
| GND | GND | Common ground |
| Suitable external motor supply | Motor power terminal (+12V / VS, as supported by the module) | Supplies motor power |


The left and right motor outputs must be connected to the corresponding driver output terminals.
On many L298N modules, jumpers are fitted to the enable pins. If PWM speed control is required through D5 and D6, the relevant enable jumpers usually need to be removed. Confirm this against the actual module.
7.3 Power Connections
The motor supply must be selected according to the motor voltage, expected current, and driver specifications.
The Arduino and motor driver must share a common ground for their control signals to work reliably.
However, the logic power arrangement depends on the specific driver board. Follow the board's documentation rather than assuming that every terminal or jumper has the same function.
Do not connect the motor supply directly to the Arduino's 5 V pin.
7.4 Importance of Correct Motor Polarity
The motor directions are essential for balancing.
If the robot leans forward, the wheels must move in the direction that catches the falling body. If they move in the opposite direction, the feedback becomes destabilizing.
Each motor's physical forward direction depends on how its two wires are connected to the driver.
If a motor runs in reverse relative to the desired direction, its polarity can be reversed in software or by swapping its motor leads with the power disconnected.
The control direction must be verified experimentally before attempting a free-standing balance test.

CHAPTER 8: MATHEMATICAL MODEL OF THE ROBOT
8.1 Introduction
Mathematical modelling helps explain why the robot falls and how corrective motor movement can restore balance.
The two-wheeled robot can be approximated as an inverted pendulum mounted on a movable wheel axle.
A complete dynamic model would include the mass and inertia of the body, wheel radius, motor torque, gear ratio, friction, and electrical characteristics. The reference program does not calculate all these quantities explicitly; it uses measured feedback to control the angle.
8.2 Main Variables
The following variables are useful for understanding the system:

| Symbol | Description | Unit |
|---|---|---|
| \(\theta\) | Robot tilt angle | Radians or degrees |
| \(\theta_{\mathrm{ref}}\) | Desired upright angle | Radians or degrees |
| \(e\) | Angle error | Radians or degrees |
| \(\omega\) | Angular velocity | Radians/second (rad/s) |
| \(x\) | Wheel axle position | Metres (m) |
| \(v\) | Wheel axle velocity | Metres/second (m/s) |
| \(u\) | Controller output | PWM command or normalized control |
| \(K_p\) | Proportional gain | Depends on controller scaling |
| \(K_i\) | Integral gain | Depends on controller scaling and time |
| \(K_d\) | Derivative gain | Depends on controller scaling and time |



## 8.3 Angle Error

The angle error is calculated as:

$$
e(t) = \theta_{\mathrm{ref}} - \theta(t)
$$

where:

- $\theta_{\mathrm{ref}}$ is the target angle.
- $\theta(t)$ is the estimated actual angle.

The reference is often close to zero degrees when the robot is upright, but the correct value depends on sensor mounting and mechanical alignment.

If the sensor's zero angle does not correspond to the desired upright posture, the target angle must be calibrated.

## 8.4 Why the Wheels Must Move

Consider a robot leaning forward.

If the wheels remain stationary, gravity continues to rotate the body forward. By moving the wheels forward, the robot changes the location of the pivot relative to the body, helping bring the support point underneath the centre of mass.

The same principle applies in the backward direction.

The control system must therefore respond to the robot's body angle and angular velocity, not merely to whether the motors are rotating.

## 8.5 Control Signal

The PID algorithm generates a control output from the angle error:

$$
u(t) = K_p e(t) + K_i \int_0^t e(\tau)\,d\tau + K_d \frac{de(t)}{dt}
$$

The output is limited to a range appropriate for the motor driver.

In the reference implementation, the command is converted to a signed PWM value. Positive and negative values represent opposite motor directions.

The correct sign depends on the sensor coordinate system and motor wiring.

## 8.6 Limitations of the Simplified Model

The equations above describe the controller's error and output, not a complete physical model of the robot.

Actual motion depends on:

- Body mass and centre of mass.
- Wheel radius and inertia.
- Motor torque and gear ratio.
- Motor-driver voltage drop.
- Battery voltage.
- Friction and wheel traction.
- Sensor noise and bias.
- Control-loop timing.

These factors explain why PID values from one robot cannot automatically be copied to another robot.

# CHAPTER 9: SENSOR MEASUREMENT AND ANGLE ESTIMATION

## 9.1 Accelerometer-Based Angle

An accelerometer measures acceleration along three axes.

When the robot is stationary or moving slowly enough that linear acceleration is small, the gravity vector can be used to estimate its inclination.

For a particular sensor orientation, an angle can be calculated using an `atan2()` expression, for example:

$$
\theta_{\mathrm{acc}} = \mathrm{atan2}(a_y, a_z)
$$

where:

- $a_y$ is the acceleration measured along the sensor's Y-axis.
- $a_z$ is the acceleration measured along the sensor's Z-axis.

This formula is only correct for the specified axis convention. If the sensor is mounted differently, another combination of axes may be required.

## 9.2 Gyroscope-Based Angle

The gyroscope measures angular velocity.

If the measured angular rate is $\omega$, a simple discrete-time angle update is:

$$
\theta_k = \theta_{k-1} + \omega_k \Delta t
$$

where $\Delta t$ is the time elapsed between measurements.

This estimate responds quickly to rotation, but small measurement errors accumulate over time.

## 9.3 Why Both Sensors Are Needed

The accelerometer provides a long-term reference based on gravity but may be disturbed by linear acceleration.

The gyroscope responds rapidly to rotation but accumulates drift when its measurements are integrated.

Combining the two measurements gives a more useful estimate for balancing.

## 9.4 Sensor Calibration

Before balancing tests, confirm:

1. The sensor is firmly attached.
2. The robot's forward direction corresponds to the intended sensor axis.
3. The angle changes in the correct direction when the robot is tilted.
4. The gyroscope rate has the correct sign.
5. The upright target angle has been calibrated.
6. The readings are not dominated by vibration or loose connections.

Incorrect axis selection is one of the most important causes of failed self-balancing attempts.
