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
