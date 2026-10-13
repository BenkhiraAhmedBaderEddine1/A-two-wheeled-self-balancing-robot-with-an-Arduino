═══════════════════════════════════════════════════════════════


    >⩊<  TWO-WHEELED SELF-BALANCED ROBOT WITH ARDUINO      >⩊<  

 
                    ꧁⎝ 𓆩༺✧༻𓆪 ⎠꧂
                    
═══════════════════════════════════════════════════════════════

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



  # TABLE OF CONTENTS

**ABSTRACT**

**CHAPTER 1: GENERAL INTRODUCTION**  
1.1 Introduction  
1.2 Problem Statement  
1.3 Project Aim  
1.4 Project Objectives  
1.5 Project Scope  
1.6 Project Motivation and Importance  

**CHAPTER 2: BACKGROUND AND RELATED CONCEPTS**  
2.1 What Is a Self-Balancing Robot?  
2.2 The Inverted Pendulum  
2.3 Feedback Control  
2.4 Open-Loop and Closed-Loop Control  
2.5 Role of Real-Time Processing  

**CHAPTER 3: GENERAL DESCRIPTION OF THE ROBOT**  
3.1 Project Description  
3.2 Description of the Robot in the Photographs  
3.3 Main Functional Units  
3.4 Expected Operating Behaviour  

**CHAPTER 4: HARDWARE COMPONENTS**  
4.1 Arduino Uno  
4.2 MPU6050 Accelerometer and Gyroscope  
4.3 DC Geared Motors  
4.4 Wheels  
4.5 L298N Motor Driver  
4.6 Battery and Power Supply  
4.7 Chassis and Mounting Hardware  
4.8 Connecting Wires and Connectors  
4.9 Optional Components  

**CHAPTER 5: SOFTWARE REQUIREMENTS**  
5.1 Arduino IDE  
5.2 Programming Language  
5.3 Required Libraries  
5.4 Software Development Process  

**CHAPTER 6: MECHANICAL DESIGN AND ASSEMBLY**  
6.1 Mechanical Design Requirements  
6.2 Assembly Procedure  
6.3 Mechanical Considerations  

**CHAPTER 7: ELECTRICAL CONNECTIONS AND WIRING**  
7.1 MPU6050 Connections  
7.2 L298N Connections  
7.3 Power Connections  
7.4 Importance of Correct Motor Polarity  

**CHAPTER 8: MATHEMATICAL MODEL OF THE ROBOT**  
8.1 Introduction  
8.2 Main Variables  
8.3 Angle Error  
8.4 Why the Wheels Must Move  
8.5 Control Signal  
8.6 Limitations of the Simplified Model  

**CHAPTER 9: SENSOR MEASUREMENT AND ANGLE ESTIMATION**  
9.1 Accelerometer-Based Angle  
9.2 Gyroscope-Based Angle  
9.3 Why Both Sensors Are Needed  
9.4 Sensor Calibration  

**CHAPTER 10: COMPLEMENTARY FILTER**  
10.1 Definition  
10.2 Advantages of the Complementary Filter  
10.3 Limitations  

**CHAPTER 11: PID CONTROL THEORY**  
11.1 What Is PID?  
11.2 Proportional Term (P)  
11.3 Integral Term (I)  
11.4 Derivative Term (D)  
11.5 Complete PID Equation  
11.6 Choosing the Initial PID Values  
11.7 PID Tuning Procedure  

**CHAPTER 12: SYSTEM ALGORITHM AND FLOWCHART**  
12.1 Control Algorithm  
12.2 Flowchart  
12.3 Pseudocode  

**CHAPTER 13: COMPLETE ARDUINO C++ PROGRAM**  
13.1 Purpose of the Program  
13.2 Full Source Code  
13.3 Important Technical Notes About This Code  

**CHAPTER 14: EXPLANATION OF THE PROGRAM**  
14.1 Library Inclusion  
14.2 Sensor Initialization  
14.3 Motor Control  
14.4 Sensor Reading  
14.5 Angle Estimation  
14.6 PID Calculation  
14.7 Safety Logic  
14.8 Serial Diagnostics  

**CHAPTER 15: IMPLEMENTATION AND CALIBRATION PROCEDURE**  
15.1 Stage One: Hardware Inspection  
15.2 Stage Two: Install the Software  
15.3 Stage Three: Verify the IMU  
15.4 Stage Four: Verify Motor Direction  
15.5 Stage Five: Tune the Controller  
15.6 Stage Six: Floor Testing  
15.7 Stage Seven: Document the Final Configuration  

**CHAPTER 16: TESTING AND EXPERIMENTAL EVALUATION**  
16.1 Purpose of Testing  
16.2 Test One: Sensor Functionality  
16.3 Test Two: Motor Functionality  
16.4 Test Three: Controller Response  
16.5 Test Four: Balancing Performance  
16.6 Test Five: Repeatability  
16.7 Test Six: Battery Performance  
16.8 Test Results Table  
16.9 Performance Indicators  

**CHAPTER 17: RESULTS AND DISCUSSION**  
17.1 Expected Results  
17.2 Interpretation of Successful Operation  
17.3 Interpretation of Unsuccessful Operation  
17.4 Scientific Reporting of Results  

**CHAPTER 18: ADVANTAGES OF THE PROJECT**  
18.1 Educational Advantages  
18.2 Technical Advantages  
18.3 Research Advantages  

**CHAPTER 19: DISADVANTAGES AND LIMITATIONS**  
19.1 Inherent Instability  
19.2 Sensitivity to PID Parameters  
19.3 Sensor Errors  
19.4 Power Consumption  
19.5 Motor Mismatch  
19.6 Limited Position Control  
19.7 Mechanical Sensitivity  
19.8 Limited Fault Protection  

**CHAPTER 20: SAFETY CONSIDERATIONS**

**CHAPTER 21: COMMON PROBLEMS AND TROUBLESHOOTING**  
21.1 Recommended Troubleshooting Order  

**CHAPTER 22: FUTURE IMPROVEMENTS**  
22.1 Wheel Encoders  
22.2 Bluetooth Control  
22.3 Wi-Fi and Telemetry  
22.4 Battery Monitoring  
22.5 Better Motor Driver  
22.6 Improved State Estimation  
22.7 Obstacle Detection  
22.8 Autonomous Navigation  
22.9 Better Safety System  
22.10 Advanced Control Methods  

**CHAPTER 23: APPLICATIONS**

**CHAPTER 24: PROJECT COST AND BUDGET CONSIDERATIONS**  
Bill of Materials (BOM)

**CHAPTER 25: PROJECT MANAGEMENT AND WORK PLAN**  
Project Implementation Plan

**CHAPTER 26: CONCLUSION**

**REFERENCES**

**APPENDICES**  
Appendix A: Glossary of Technical Terms  
Appendix B: Abbreviations


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


CHAPTER 10: COMPLEMENTARY FILTER

10.1 Definition

   A complementary filter combines two measurements with different characteristics to obtain a more useful estimate.
For this robot, the filter combines the integrated gyroscope angle and the accelerometer-derived angle.
The discrete-time equation is:

The complementary filter combines the gyroscope and accelerometer measurements to estimate the robot's tilt angle:

$$
\theta_k = \alpha(\theta_{k-1} + \omega_k \Delta t) + (1-\alpha)\theta_{\mathrm{acc},k}
$$

where:

- $\theta_k$ is the filtered angle.
- $\theta_{k-1}$ is the previous filtered angle.
- $\omega_k$ is the angular rate in radians per second (rad/s), or degrees per second if the angle calculation uses degrees consistently.
- $\Delta t$ is the sample interval in seconds.
- $\alpha$ is the filter coefficient.
- $\theta_{\mathrm{acc},k}$ is the accelerometer angle.

For the reference program, $\alpha = 0.95$ is a starting value.

This means that the filter gives more weight to the short-term gyroscope estimate while still using the accelerometer to correct long-term drift.


10.2 Advantages of the Complementary Filter

- It is computationally inexpensive.
- It is suitable for small microcontrollers.
- It combines fast motion response with a gravity-based reference.
- It is relatively straightforward to implement and debug.
10.3 Limitations
The filter does not eliminate all measurement errors.
Its performance depends on sensor orientation, noise, vibration, and the selected coefficient. If the accelerometer angle is calculated using the wrong axes, filtering will not correct the underlying problem.
A more advanced estimator, such as a Kalman filter, may be considered in a later version if the project requires improved estimation performance.


CHAPTER 11: PID CONTROL THEORY

11.1 What Is PID?

PID stands for Proportional, Integral, and Derivative.
It is a widely used feedback-control method that calculates a control output from the error between a desired state and the measured state.
For the robot, the main error is the difference between the target upright angle and the estimated tilt angle.
The controller calculates a corrective output and sends it to the motors.

11.2 Proportional Term

The proportional term is:

## 11.2 Proportional Term (P)

The proportional term is:

$$
P(t) = K_p e(t)
$$

It responds to the current angle error.

A larger error produces a larger proportional correction, subject to the output limits.

If $K_p$ is too low, the motors may not correct the tilt strongly enough.

If $K_p$ is too high, the robot may oscillate, overshoot, or produce sudden motor movements.

## 11.3 Integral Term (I)

The integral term is:

$$
I(t) = K_i \int_0^t e(\tau)\,d\tau
$$

It accumulates the error over time.

Integral action can reduce persistent bias, such as a small steady-state error caused by asymmetry or other disturbances.

However, excessive integral action may accumulate while the motor output is saturated. This is known as **integral windup** and can cause large overshoots.

For this reason, the reference code limits the accumulated integral term.

Many self-balancing robots are initially tuned using PD control, with $K_i = 0$, before integral action is introduced.

## 11.4 Derivative Term (D)

The derivative term is:

$$
D(t) = K_d \frac{de(t)}{dt}
$$

It responds to the rate at which the error changes.

Derivative action helps damp oscillations by responding to rapid changes in the error.

However, the derivative term can amplify sensor noise. The angle estimator and sensor filtering therefore matter when choosing $K_d$.

## 11.5 Complete PID Equation

The continuous-time PID equation is:

$$
u(t) = K_p e(t) + K_i \int_0^t e(\tau)\,d\tau + K_d \frac{de(t)}{dt}
$$

The digital implementation uses discrete measurements and an estimate of the elapsed time.

In the reference code, the integral term is updated as follows:

$$
I_k = I_{k-1} + e_k \Delta t
$$

The derivative term is calculated as:

$$
D_k = \frac{e_k - e_{k-1}}{\Delta t}
$$

The controller output is then:

$$
u_k = K_p e_k + K_i I_k + K_d D_k
$$

The result is constrained to a permitted PWM range to prevent the controller from requesting motor outputs beyond the allowed limits.



## 11.6 Choosing the Initial PID Values

The program uses these example values:

| Parameter | Initial Example |
|---|---:|
| $K_p$ | 18.0 |
| $K_i$ | 0.0 |
| $K_d$ | 0.75 |
| Nominal loop frequency | 200 Hz |
| Maximum initial PWM | 200 out of 255 |
| Fallen-angle threshold | 35 degrees |

These are starting values, not validated settings for the pictured robot.

The appropriate values depend on the chassis, motors, battery, sensor orientation, and the way the controller's output is scaled.


## 11.7 PID Tuning Procedure


**Step 1: Verify the sensor.**

Tilt the robot by hand and inspect the reported angle.

**Step 2: Verify motor direction.**

Lift the wheels off the ground and confirm that the wheels respond in the corrective direction when the body tilts. Keep hands and objects clear of moving parts.

**Step 3: Start with $K_i = 0$.**

Begin with proportional and derivative (PD) control.

**Step 4: Increase $K_p$ gradually.**

Increase the proportional gain until the robot responds strongly enough to correct a small tilt. If it oscillates violently, reduce the gain.

**Step 5: Adjust $K_d$.**

Increase the derivative gain gradually to reduce oscillations. Excessive derivative gain may produce noisy or twitchy motor behaviour.

**Step 6: Introduce integral action only if necessary.**

If a persistent bias remains after the PD controller has been tuned, add a small integral gain and monitor the response carefully.

**Step 7: Record every test.**

Record the gains, battery condition, observed behaviour, and whether the robot balances.

Never change all three gains randomly at the same time. Adjust one parameter at a time so that the effect of each change can be understood.


CHAPTER 12: SYSTEM ALGORITHM AND FLOWCHART

12.1 Control Algorithm

The robot follows a repeated control algorithm.
1. Start the Arduino.
2. Initialize the serial interface and I²C communication.
3. Initialize the MPU6050 sensor.
4. Configure the motor-driver pins.
5. Read the initial sensor measurements.
6. Wait until the next control-loop interval.
7. Read acceleration and angular velocity.
8. Calculate the accelerometer angle.
9. Update the complementary filter.
10. Calculate the angle error.
11. Check whether the robot has exceeded the safe tilt threshold.
12. If it has fallen too far, stop the motors and reset the integral term.
13. Otherwise, calculate the proportional, integral, and derivative terms.
14. Combine the terms into the PID output.
15. Limit the output to the permitted motor command.
16. Drive both motors in the appropriate direction.
17. Print diagnostic information periodically.
18. Repeat the control loop.


12.2 Flowchart

![image alt](https://github.com/BenkhiraAhmedBaderEddine1/A-two-wheeled-self-balancing-robot-with-an-Arduino/blob/2e44d9df00284bb487ec69f9cbc20239e057194e/Flowchart)

12.3 Pseudocode


https://github.com/BenkhiraAhmedBaderEddine1/A-two-wheeled-self-balancing-robot-with-an-Arduino/blob/db758341db401ce87531407c80972933324c0887/Pseudocode





CHAPTER 13: COMPLETE ARDUINO C++ PROGRAM

13.1 Purpose of the Program

The following program is a complete reference implementation for a self-balancing robot using:
- Arduino Uno.
- MPU6050 IMU.
- L298N motor driver.
- Two geared DC motors.
- Complementary angle filtering.
- PID control.
- PWM motor commands.
- A fallen-angle safety stop.
- Serial diagnostics.
It is intended as a starting point for the hardware configuration described in this report. Sensor-axis selection and motor direction must be verified on the actual robot before free-standing operation.

13.2 Full Source Code
  
Create a new sketch in Arduino IDE and use the following code.

https://github.com/BenkhiraAhmedBaderEddine1/A-two-wheeled-self-balancing-robot-with-an-Arduino/blob/fdbc8dcdadfec16db83f10d50b0284296ec2d95e/Arduino_Code.ino

13.3 Important Technical Notes About This Code

The code above provides the complete reference control loop, but there are several details that must be handled correctly.
First: sensor-axis calibration. The accelerometer formula and gyroscope axis must represent the same physical rotation. The example uses accelerometer Y/Z and gyroscope X. If the sensor is rotated on your chassis, you must change both consistently.
Second: motor polarity. The left and right motor polarities may not be identical because the motors can be mounted facing opposite directions. Test them with the wheels raised.
Third: upright reference. The value targetAngle = 0.0 is only an initial setting. The correct upright reference must be determined for the actual sensor mounting and chassis.
Fourth: control-loop timing. The code targets a 5 ms interval, but sensor communication and program execution affect the actual sampling rate. The loop timing should be measured during testing.
Fifth: safety stop. The fallen-angle threshold stops the motors after excessive tilt. It is not a substitute for an emergency power switch. A falling robot can reach the threshold quickly, and the robot may still be unstable before it falls.
Sixth: hardware compatibility. The code uses the Adafruit MPU6050 library. It is not intended to run unchanged with an entirely different IMU, motor driver, or pin arrangement.
Seventh: actual balancing performance. A program compiling successfully does not prove that the robot will balance. Correct signs, motor torque, mechanical alignment, power supply, and PID tuning are essential.

CHAPTER 14: EXPLANATION OF THE PROGRAM

14.1 Library Inclusion



----------------------------------
#include <Wire.h>                
#include <Adafruit_MPU6050.h>    
#include <Adafruit_Sensor.h>     
#include <math.h>                
----------------------------------


Wire.h enables I²C communication. The Adafruit libraries provide the interface to the MPU6050. The mathematical library supplies functions such as atan2() and fabs().
14.2 Sensor Initialization


Adafruit_MPU6050 mpu;  

This creates the object used to communicate with the sensor.
The initialiseMPU() function checks whether the sensor is detected and configures the accelerometer range, gyroscope range, and sensor bandwidth.
If the sensor is not detected, the program stops the motors and reports an error.

14.3 Motor Control

The setOneMotor() function determines the direction of one motor using its two H-bridge input pins. The PWM pin controls the effective motor power.
The driveMotors() function applies a common signed command to both motors.
This simple arrangement is appropriate for an initial reference implementation, but it does not compensate for differences between the two motors. Wheel encoders and separate motor commands can improve control in a more advanced version.

14.4 Sensor Reading

The function mpu.getEvent() reads the current sensor measurements.
The accelerometer values are used to calculate a gravity-based angle estimate. The gyroscope provides angular velocity for the complementary filter.

14.5 Angle Estimation

The filter first predicts the new angle using the gyroscope, then combines this prediction with the accelerometer angle.
The resulting estimate is used as the feedback variable in the PID controller.

14.6 PID Calculation

The program calculates:
- P: proportional correction.
- I: integral correction.
- D: derivative correction.
These terms are added together to form the control output.
The output is then constrained to the selected PWM range.

14.7 Safety Logic
  
If the estimated angle exceeds the fallen-angle threshold, the program stops the motors and clears the accumulated integral error.
This prevents the controller from continuing to apply balancing commands while the robot is far from its intended operating range.

14.8 Serial Diagnostics

The Serial Monitor displays:
- Estimated angle.
- Angle error.
- Proportional contribution.
- Integral contribution.
- Derivative contribution.
- Combined PID output.
- Motor command.
These measurements are valuable when tuning the controller and diagnosing instability.


CHAPTER 15: IMPLEMENTATION AND CALIBRATION PROCEDURE

15.1 Stage One: Hardware Inspection

Before uploading the program, inspect the chassis, motor mounting, wheel alignment, sensor mounting, and wiring.
Confirm that the motor supply matches the motors and driver.
Check that the logic supply is appropriate for the Arduino and IMU.

15.2 Stage Two: Install the Software

Install Arduino IDE and the required libraries.
Select the correct Arduino board and serial port. Compile the program and correct any library or configuration errors before testing the motors.

15.3 Stage Three: Verify the IMU

Power the controller and open the Serial Monitor at 115200 baud.
Tilt the chassis forward and backward by hand.
Verify that the reported angle changes smoothly and in the expected direction.
If the angle is reversed or does not respond as expected, correct the sensor-axis selection and sign conventions.

15.4 Stage Four: Verify Motor Direction

Raise the robot so that the wheels cannot propel it across the floor.
Apply small motor commands in a controlled test.
Verify the physical direction of each motor and confirm that the two wheels can move in the direction required to catch a forward or backward tilt.
If a correction makes the tilt worse, stop testing immediately. Check the sensor sign, gyro axis, and motor polarity before continuing.

15.5 Stage Five: Tune the Controller

Begin with integral gain set to zero.
Adjust proportional gain gradually, followed by derivative gain.
Avoid aggressive testing. Use a hand support or suitable stand and an accessible power switch during early trials.
Only introduce a small integral gain if a persistent error remains after the PD response is satisfactory.

15.6 Stage Six: Floor Testing

Once the sensor readings and motor directions are verified, place the robot on a level surface.
Use a clear test area, keep hands and cables away from the wheels, and be ready to disconnect motor power.
Record each test rather than relying on memory.
15.7 Stage Seven: Document the Final Configuration
Record the final hardware models, pin assignments, sensor orientation, target angle, PID gains, battery specification, and test conditions.
This information is necessary for reproducing the results and defending the project during an academic presentation.

CHAPTER 16: TESTING AND EXPERIMENTAL EVALUATION

16.1 Purpose of Testing

Testing determines whether the assembled robot operates as intended and identifies problems in the sensor, controller, motor driver, power supply, or mechanical structure.
The tests should progress from simple component checks to controlled balancing experiments.

16.2 Test One: Sensor Functionality

Objective: Confirm that the MPU6050 provides usable measurements.
Procedure:
1. Power the Arduino and IMU.
2. Open the Serial Monitor.
3. Tilt the robot slowly forward and backward.
4. Observe the estimated angle.
5. Repeat the test several times.
Expected observation: The reported angle changes consistently with the robot's physical tilt.
Record: Sensor detection, angle direction, angle variation, and any noise or unexpected jumps.

16.3 Test Two: Motor Functionality
   
Objective: Confirm that both motors operate correctly.
Procedure:
1. Raise the robot so the wheels cannot touch the floor.
2. Apply small motor commands.
3. Verify the left motor's direction.
4. Verify the right motor's direction.
5. Check that the wheels rotate without obstruction.
Expected observation: Both motors respond to the commands, and their directions are understood.

16.4 Test Three: Controller Response
   
Objective: Determine whether the PID controller responds to small changes in angle.
Procedure:
1. Keep the robot supported.
2. Tilt it slightly.
3. Observe the measured angle and PID output.
4. Observe whether the motor command changes in response.
5. Check that the correction acts against the tilt.
Expected observation: The motor command changes when the angle error changes.
A changing motor command alone does not prove that the control direction is correct. The direction must also be verified physically.

16.5 Test Four: Balancing Performance
   
Objective: Evaluate whether the robot can maintain its upright position.
Procedure:
1. Place the robot on a level surface.
2. Ensure the motor direction and safety settings have been verified.
3. Start from a small, controlled tilt.
4. Observe the robot's response.
5. Record the time before it falls, if it falls.
6. Repeat under the same conditions.
Expected observation: A properly configured robot should move its wheels to reduce small tilts. With suitable tuning and adequate hardware, it may remain upright for a measurable period.
The actual outcome must be observed and recorded. Do not claim successful balancing if the robot has not been tested.

16.6 Test Five: Repeatability
   
Objective: Determine whether the robot behaves consistently over repeated trials.
Repeat the balancing test at least five times under similar conditions.
Record the number of successful trials, balancing duration, PID settings, and any unusual behaviour.

16.7 Test Six: Battery Performance
   
Objective: Determine whether the power supply affects balancing.
Record battery voltage before and after the tests.
Observe whether the robot's response changes as the battery discharges.
If motor output becomes weak or inconsistent, check the battery condition, wiring, motor-driver losses, and current capacity.

16.8 Test Results Table

Complete the following table with actual measurements from your robot.

| Test | Parameter | Actual Result |
|---|---|---|
| IMU Test | Sensor detected | __________ |
| IMU Test | Angle direction correct | __________ |
| Motor Test | Left motor direction verified | __________ |
| Motor Test | Right motor direction verified | __________ |
| PID Test | Final `Kp` | __________ |
| PID Test | Final `Ki` | __________ |
| PID Test | Final `Kd` | __________ |
| Balance Test | Longest balancing time | __________ seconds |
| Repeatability | Successful trials out of five | __________ / 5 |
| Power Test | Initial battery voltage | __________ volts |
| Power Test | Final battery voltage | __________ volts |


16.9 Performance Indicators

The project can be evaluated using several quantitative indicators.
Balancing duration: The time for which the robot remains within a defined safe angular range.
Maximum angular deviation: The largest absolute angle reached during a trial.
Settling time: The time required for the robot's angle to return to a specified range after a small disturbance.
Repeatability: The proportion of trials that meet the defined success criterion.
Control activity: The frequency and magnitude of changes in the motor command.
Power behaviour: Battery voltage changes and any resets or interruptions during operation.
A clear definition of the success criterion should be established before collecting data. For example, the project may define a successful trial as maintaining the robot within a specified angle range for a specified duration. The limits should be selected to match the hardware and experimental objectives.

CHAPTER 17: RESULTS AND DISCUSSION

17.1 Expected Results

The expected result of this project is a two-wheeled robot that uses sensor feedback to correct deviations from its upright position.
When the body tilts, the IMU detects the movement. The Arduino estimates the angle and calculates the PID output. The motor driver then applies the corresponding corrective command to the wheels.
If the system has been assembled correctly and the controller is appropriately tuned, the robot should respond to small tilts by moving the wheels in a direction that helps restore balance.
However, the quality of the response depends on the physical robot and its calibration.

17.2 Interpretation of Successful Operation

A successful balancing trial would demonstrate that:
- The sensor provides useful measurements.
- The angle-estimation algorithm works adequately.
- The feedback direction is correct.
- The motors have sufficient torque.
- The PID controller produces an appropriate response.
- The power system supports the required motor current.
- The mechanical structure is suitable for the control task.
A stable trial is evidence that these subsystems work together under the tested conditions.

17.3 Interpretation of Unsuccessful Operation
  
If the robot falls immediately, the problem may be related to incorrect sensor axes, incorrect motor polarity, insufficient torque, inappropriate PID gains, or poor mechanical balance.
If the robot oscillates repeatedly, the controller may be too aggressive, the derivative response may be insufficient, or the sensor may be noisy.
If the robot balances briefly but then drifts, wheel-position feedback, motor mismatch, sensor bias, or battery changes may be contributing factors.
A structured troubleshooting process is more useful than changing multiple settings at random.

17.4 Scientific Reporting of Results
  
The photographs show the robot's assembly process, but they do not establish its final balancing performance.
Therefore, the report does not assign an invented balancing duration, success rate, or measured angle error.
After completing the tests, insert the measured values and explain how the PID settings affected the response.
A suitable results paragraph should describe what actually happened, identify the final settings, and discuss any remaining limitations.

CHAPTER 18: ADVANTAGES OF THE PROJECT

18.1 Educational Advantages

The project integrates several important engineering disciplines into one system.
Students gain experience in:
- Microcontroller programming.
- C++ programming.
- Electronic circuit connections.
- Motor-driver operation.
- IMU sensor measurements.
- Sensor fusion.
- PID control.
- Real-time systems.
- Mechanical assembly.
- Experimental testing.

18.2 Technical Advantages
  
Closed-loop control: The robot reacts to its measured condition instead of relying on fixed motor commands.
Compact mechanical design: Two wheels and a small chassis provide a compact platform for experimentation.
Accessible development tools: Arduino and the associated software libraries are widely used in educational robotics.
Expandable architecture: Additional sensors, encoders, wireless modules, and control algorithms can be added.
Practical demonstration: The system makes an abstract concept—feedback control—visible through physical motion.

18.3 Research Advantages
  
The robot can be used to compare different controller settings and angle-estimation techniques.
It provides a platform for investigating response time, oscillations, disturbances, battery performance, and the effects of mechanical changes.

CHAPTER 19: DISADVANTAGES AND LIMITATIONS

19.1 Inherent Instability

The robot is dynamically unstable. It requires continuous feedback and can fall if the control loop stops or becomes incorrect.

19.2 Sensitivity to PID Parameters

A controller that is poorly tuned may oscillate, respond too slowly, or drive the robot further from balance.
The same PID parameters will not necessarily work on two robots with different masses, wheels, motors, or batteries.

19.3 Sensor Errors

Accelerometer measurements are affected by vibration and linear acceleration.
Gyroscope measurements may drift because of bias.
Incorrect axis selection or inconsistent signs can make the angle estimate unsuitable for control.

19.4 Power Consumption

The motors may draw considerable current when correcting disturbances. This can shorten battery life and cause supply-voltage drops.

19.5 Motor Mismatch

Two nominally identical motors may have different speeds, friction, or torque.
A controller that sends the same command to both motors may not produce perfectly symmetrical movement.

19.6 Limited Position Control

The reference program primarily controls body angle. It does not use wheel encoders to maintain a fixed position.
As a result, the robot may remain approximately upright while gradually rolling away from its starting position.

19.7 Mechanical Sensitivity

Loose mounting points, wheel misalignment, a flexible chassis, or a shifting battery can negatively affect performance.

19.8 Limited Fault Protection

The reference code includes a fallen-angle stop but does not implement a full emergency-stop circuit, battery management system, motor-current protection system, or independent safety controller.
These features should be considered for a more robust design.


CHAPTER 20: SAFETY CONSIDERATIONS


Safety is an important part of the project's design and testing.
1. Disconnect the power before changing wiring.
2. Confirm the battery voltage and polarity before connecting it.
3. Never connect the motors directly to Arduino GPIO pins.
4. Use a motor driver rated for the motors' expected current.
5. Secure the battery and electronic modules.
6. Keep fingers, hair, clothing, and loose wires away from rotating wheels.
7. Lift the wheels before the first motor-direction tests.
8. Use an accessible switch to disconnect motor power.
9. Do not leave the powered robot unattended.
10. Stop testing if the driver becomes excessively hot, the battery swells, wiring overheats, or the controller resets repeatedly.
11. Avoid short circuits and exposed conductive connections.
12. Perform initial tests on a clear surface away from stairs, people, and fragile objects.
The software safety stop is useful, but it must not be treated as a replacement for safe electrical design and an accessible means of removing power.

# CHAPTER 21: COMMON PROBLEMS AND TROUBLESHOOTING

| Problem | Possible Cause | Recommended Action |
|---|---|---|
| MPU6050 is not detected | Incorrect wiring or power supply | Check SDA, SCL, VCC, GND, and the module documentation. |
| Angle readings are reversed | Incorrect sensor-axis convention | Correct the accelerometer formula and gyroscope axis/sign. |
| Motors do not move | Incorrect driver wiring or missing motor power | Verify the motor supply, enable pins, driver inputs, and common ground. |
| Robot falls faster when correcting | Incorrect feedback sign or motor polarity | Stop testing and verify sensor signs and motor directions. |
| Robot oscillates rapidly | Excessive proportional gain or inadequate damping | Reduce `Kp` gradually and tune `Kd` carefully. |
| Robot responds too slowly | Insufficient control response or motor torque | Check PID gains, motor capability, power supply, and control-loop timing. |
| Motors only vibrate | Insufficient supply current, mechanical binding, or unsuitable PWM | Check the battery, motor driver, wiring, and wheel freedom. |
| Arduino repeatedly resets | Supply-voltage drop or electrical interference | Separate motor and logic power appropriately and improve grounding. |
| Robot slowly rolls away | No wheel-position feedback | Add wheel encoders and a suitable outer control loop. |
| Motor driver overheats | Excessive current or power dissipation | Check motor stall current and consider a more efficient motor driver. |
| Angle readings are noisy | Vibration or loose IMU mounting | Secure the sensor and inspect filtering and mechanical mounting. |
| Balancing performance changes as the battery discharges | Changing motor voltage and available torque | Monitor battery voltage and evaluate the power system. |



21.1 Recommended Troubleshooting Order

Use this order to isolate problems efficiently:
1. Check power and wiring.
2. Verify that the IMU is detected.
3. Verify the angle measurement and sensor axes.
4. Verify both motor directions with the wheels raised.
5. Verify that the control response opposes the tilt.
6. Tune proportional gain.
7. Tune derivative gain.
8. Introduce integral gain only if required.
9. Investigate mechanical and power limitations.
10. Repeat controlled tests and document the changes.

CHAPTER 22: FUTURE IMPROVEMENTS

22.1 Wheel Encoders

Wheel encoders measure wheel rotation and allow the controller to estimate wheel speed and displacement.
They can help the robot control its position and reduce unwanted drift.
An improved controller may use an inner balancing loop and an outer wheel-speed or position loop.

22.2 Bluetooth Control

A Bluetooth module can allow a user to send movement commands from a phone.
Possible commands include:
- Move forward.
- Move backward.
- Turn left.
- Turn right.
- Stop.
- Adjust speed.
- Change operating mode.
The balancing loop should continue to operate locally on the controller, even when no remote movement command is being received.

22.3 Wi-Fi and Telemetry
  
A Wi-Fi-enabled microcontroller can transmit sensor measurements, estimated angle, PID output, battery voltage, and motor commands to a computer or dashboard.
This would make tuning and performance evaluation easier.

22.4 Battery Monitoring
  
A voltage-monitoring circuit can detect a low battery condition and reduce the risk of unstable operation caused by insufficient motor power.
Battery monitoring should be designed for the battery chemistry and voltage range being used.

22.5 Better Motor Driver

Replacing the L298N with an appropriate modern MOSFET-based driver can reduce voltage losses and improve efficiency, provided that the replacement is correctly rated for the motor current and supply voltage.

22.6 Improved State Estimation

A Kalman filter or another suitable estimator may improve angle estimation under certain operating conditions.
However, the benefits should be demonstrated experimentally rather than assumed. A correctly configured complementary filter may be sufficient for a basic educational robot.

22.7 Obstacle Detection

An ultrasonic or time-of-flight distance sensor could allow the robot to detect obstacles.
Obstacle avoidance should be added only after the balancing controller operates reliably.

22.8 Autonomous Navigation

With suitable wheel encoders, wireless communication, and additional sensors, the robot could be extended to perform movement commands or simple navigation tasks.

22.9 Better Safety System

Future versions could include:
- A physical emergency-stop switch.
- A fuse.
- Battery-voltage monitoring.
- Motor-current monitoring.
- A watchdog.
- Improved cable management.
- A protective enclosure for the electronics.
22.10 Advanced Control Methods
The robot can also be used to compare PID control with other approaches, such as state-space control, linear-quadratic regulation, or model-based control.
These approaches generally require additional modelling and validation. PID remains a reasonable starting point because it is accessible and comparatively straightforward to implement.


CHAPTER 23: APPLICATIONS

Self-balancing robots and related control systems have several potential applications.
Educational robotics: They demonstrate embedded control, sensor fusion, and system dynamics.
Control engineering laboratories: They provide a practical platform for studying unstable systems.
Research and prototyping: They can be used to compare controllers and sensor-estimation techniques.
Mobile robotic platforms: Two-wheeled balancing mechanisms can be used in experimental transportation and service-robot concepts.
Embedded systems training: They demonstrate the integration of sensors, actuators, communication interfaces, and real-time software.
Autonomous robotics development: They provide a base for adding navigation, wireless control, and other capabilities.
These are general application areas; they do not mean that the specific educational prototype is ready for commercial or human-carrying use.


CHAPTER 24: PROJECT COST AND BUDGET CONSIDERATIONS

The total cost depends on the components already available, the motor specifications, and the quality of the power system.
Because the exact component models and purchase prices are unknown, a reliable total cost cannot be stated for your particular robot.
Use the following table to calculate your actual project budget.

## Bill of Materials (BOM)

| Component | Quantity | Unit Price | Total |
|---|---:|---:|---:|
| Arduino Uno or compatible board | 1 | ______ | ______ |
| MPU6050 module | 1 | ______ | ______ |
| Dual H-bridge motor driver | 1 | ______ | ______ |
| Geared DC motors | 2 | ______ | ______ |
| Wheels | 2 | ______ | ______ |
| Chassis and motor brackets | 1 set | ______ | ______ |
| Battery and holder | 1 set | ______ | ______ |
| Switch, fuse, and wiring | 1 set | ______ | ______ |
| Fasteners and mounting materials | 1 set | ______ | ______ |
| Optional encoders or wireless module | As needed | ______ | ______ |
| **Total Project Cost** | | | **______** |

The cost can be reduced by reusing suitable components, but the motor driver and battery should not be selected solely on the basis of the lowest price. Current capacity, reliability, and electrical compatibility are important.

CHAPTER 25: PROJECT MANAGEMENT AND WORK PLAN


## Project Implementation Plan

| Phase | Main Activities | Deliverable |
|---|---|---|
| Phase 1 | Research and component selection | Project design |
| Phase 2 | Mechanical assembly | Completed chassis |
| Phase 3 | Wiring and power checks | Verified electrical system |
| Phase 4 | IMU integration | Verified angle measurements |
| Phase 5 | Motor-driver testing | Verified motor directions |
| Phase 6 | PID implementation | Working control program |
| Phase 7 | Calibration and tuning | Selected controller settings |
| Phase 8 | Experimental testing | Recorded results |
| Phase 9 | Analysis and documentation | Final report |
| Phase 10 | Presentation preparation | Demonstration and oral defence |
A structured work plan helps organize the project and reduces the likelihood of discovering major problems late in development.


CHAPTER 26: CONCLUSION

The Two-Wheeled Self-Balanced Robot with Arduino is an educational robotics project that demonstrates the integration of mechanical design, electronic hardware, embedded programming, sensor fusion, and feedback control.
The robot's principal challenge is its inherent instability. Its body must remain near an upright position while the wheels move to compensate for changes in inclination.
The Arduino provides the computational platform for reading sensor measurements and calculating motor commands. The MPU6050 provides acceleration and angular velocity measurements, and the complementary filter combines them to estimate the robot's tilt.
The PID controller calculates a corrective signal based on the difference between the desired upright angle and the estimated actual angle. The motor driver applies the resulting commands to the two geared DC motors.
The project also demonstrates the importance of practical engineering considerations. A correct control algorithm alone is insufficient if the sensor axes are incorrectly configured, the motor directions are reversed, the battery cannot supply enough current, or the mechanical structure is unsuitable.
The reference C++ implementation provides a starting point for an Arduino Uno, MPU6050, and L298N configuration. It includes sensor initialization, angle estimation, PID calculations, PWM motor control, basic fallen-angle protection, and diagnostic output.
The final performance must be established through physical testing. Actual balancing duration, repeatability, and controller settings should be documented rather than assumed.
Future improvements, particularly wheel encoders, improved motor drivers, battery monitoring, wireless telemetry, and additional safety features, can increase the robot's functionality and reliability.
In conclusion, the project provides a practical demonstration of feedback control and offers a foundation for further study in robotics, automation, and embedded control engineering.


# APPENDIX A: GLOSSARY OF TECHNICAL TERMS

| Term | Definition |
|---|---|
| Arduino | An electronics development platform commonly used for embedded systems and robotics. |
| Microcontroller | An integrated circuit that executes a program and controls connected hardware. |
| C++ | A programming language used to implement the robot's control logic. |
| IMU | Inertial Measurement Unit; a sensor system that measures acceleration and angular velocity. |
| Accelerometer | A sensor that measures acceleration along specified axes. |
| Gyroscope | A sensor that measures angular velocity. |
| I²C | A serial communication interface used by the Arduino to communicate with the IMU. |
| PWM | Pulse-Width Modulation; a technique used to regulate effective motor power. |
| H-bridge | An electronic circuit that allows a motor to be driven in either direction. |
| PID | Proportional–Integral–Derivative control. |
| Feedback | Information about a system's measured condition that is used to adjust its control input. |
| Setpoint | The desired value that the controller attempts to maintain. |
| Error | The difference between the desired value and the measured value. |
| Sensor Fusion | Combining information from multiple sensors to improve an estimate. |
| Complementary Filter | A filter that combines measurements with different frequency characteristics. |
| Inverted Pendulum | A system with its centre of mass above a pivot, requiring active control to remain upright. |
| Stability | The ability of a system to remain near its desired state or recover after a disturbance. |
| Oscillation | Repeated movement above and below a desired state. |
| Overshoot | The amount by which a response passes beyond its desired target. |
| Integral Windup | Excessive accumulation of the integral term when a controller cannot produce its requested output. |
| Calibration | Adjusting a system's reference values and settings to match the actual hardware. |
| Stall Current | The current drawn by a motor when its shaft is prevented from rotating under specified electrical conditions. |
| Dead Zone | A range of input values in which a motor does not respond sufficiently to overcome friction and other effects. |

# APPENDIX B: ABBREVIATIONS

| Abbreviation | Full Form |
|---|---|
| IMU | Inertial Measurement Unit |
| PID | Proportional–Integral–Derivative |
| PWM | Pulse-Width Modulation |
| DC | Direct Current |
| IDE | Integrated Development Environment |
| I²C | Inter-Integrated Circuit |
| ADC | Analog-to-Digital Converter |
| MCU | Microcontroller Unit |
| RPM | Revolutions Per Minute |
| P | Proportional |
| I | Integral |
| D | Derivative |
| GND | Ground |
| SDA | Serial Data |
| SCL | Serial Clock |
| VCC | Positive Supply Connection |
