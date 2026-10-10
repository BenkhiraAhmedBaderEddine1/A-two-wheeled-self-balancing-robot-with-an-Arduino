TWO-WHEELED SELF-BALANCED ROBOT WITH ARDUINO    



![image alt](https://github.com/BenkhiraAhmedBaderEddine1/A-two-wheeled-self-balancing-robot-with-an-Arduino/blob/354edce1c81626b03f01c1e5464b5f6d2d65f731/photo_2026-10-10_20-07-09.jpg)



![image alt](https://github.com/BenkhiraAhmedBaderEddine1/A-two-wheeled-self-balancing-robot-with-an-Arduino/blob/4be9c890e0d06a799f6e3fac5e0ee70fd9792f87/photo_2026-10-10_20-06-58.jpg)


![image alt](https://github.com/BenkhiraAhmedBaderEddine1/A-two-wheeled-self-balancing-robot-with-an-Arduino/blob/354edce1c81626b03f01c1e5464b5f6d2d65f731/photo_2026-10-10_20-06-54.jpg)


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
