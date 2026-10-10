/*
  PROJECT:
  Two-Wheeled Self-Balanced Robot with Arduino

  REFERENCE HARDWARE:
  - Arduino Uno
  - MPU6050 accelerometer and gyroscope
  - L298N dual H-bridge motor driver
  - Two geared DC motors

  SOFTWARE:
  - C++ / Arduino framework
  - Adafruit MPU6050 library
  - Adafruit Unified Sensor library
  - Wire library

  IMPORTANT:
  This is a reference implementation.
  Verify the sensor axes, motor polarity, power wiring,
  and PID settings for your actual robot.

  SAFETY:
  - Test with wheels lifted first.
  - Keep hands away from moving wheels.
  - Use a suitable motor power supply.
  - Disconnect power before changing wiring.
*/

#include <Wire.h>
#include <Adafruit_MPU6050.h>
#include <Adafruit_Sensor.h>
#include <math.h>

// --------------------------------------------------
// 1. SENSOR OBJECT
// --------------------------------------------------

Adafruit_MPU6050 mpu;

// --------------------------------------------------
// 2. MOTOR DRIVER PINS
// --------------------------------------------------

// Left motor
const int ENA = 5;   // PWM speed
const int IN1 = 7;
const int IN2 = 8;

// Right motor
const int ENB = 6;   // PWM speed
const int IN3 = 9;
const int IN4 = 10;

// --------------------------------------------------
// 3. SENSOR AXIS CONFIGURATION
// --------------------------------------------------

/*
  These defaults assume:
  - Pitch angle is calculated from accelerometer Y and Z.
  - Pitch angular velocity is measured on gyro X.

  This pairing is NOT correct for every MPU6050 mounting.

  Change the accelerometer formula and gyro axis together
  to match your physical sensor orientation.

  If the robot becomes less stable when the motors respond,
  stop the test and check the signs before proceeding.
*/

// --------------------------------------------------
// 4. PID PARAMETERS
// --------------------------------------------------

float Kp = 18.0f;
float Ki = 0.0f;
float Kd = 0.75f;

// Desired upright angle.
// Calibrate this value for your chassis.
float targetAngle = 0.0f;

// Maximum accumulated integral error.
const float MAX_INTEGRAL = 80.0f;

// --------------------------------------------------
// 5. FILTER AND SAFETY SETTINGS
// --------------------------------------------------

// Complementary filter coefficient.
// Gyroscope contribution is 0.95;
// accelerometer correction is 0.05.
const float ALPHA = 0.95f;

// Nominal control-loop period: 5 ms = 200 Hz.
const unsigned long LOOP_US = 5000UL;

// Initial motor-output limit.
const int MAX_PWM = 200;

// A fallen robot is stopped beyond this tilt angle.
const float FALL_ANGLE_DEG = 35.0f;

// --------------------------------------------------
// 6. MOTOR POLARITY
// --------------------------------------------------

/*
  Set each polarity to +1 or -1 after testing.

  If a motor turns opposite to the required direction,
  reverse its polarity or swap its motor wires.

  The two motors may need different polarity settings
  because they face opposite directions on the chassis.
*/

const int LEFT_POLARITY = 1;
const int RIGHT_POLARITY = 1;

// --------------------------------------------------
// 7. GLOBAL VARIABLES
// --------------------------------------------------

float angleDeg = 0.0f;
float integralTerm = 0.0f;
float previousError = 0.0f;

unsigned long previousMicros = 0;
unsigned long lastPrintMs = 0;

bool sensorReady = false;

// --------------------------------------------------
// 8. ACCELEROMETER ANGLE
// --------------------------------------------------

float readAccelPitchDeg(
    float ax,
    float ay,
    float az
) {
  /*
    Example axis convention only.

    Verify the axis convention for the actual sensor.
    Use the matching gyro axis in the control loop.
  */

  return atan2(ay, az) * 180.0f / PI;
}

// --------------------------------------------------
// 9. MOTOR CONTROL
// --------------------------------------------------

void setOneMotor(
    int pwmPin,
    int inA,
    int inB,
    int command,
    int polarity
) {
  command *= polarity;

  command = constrain(command, -255, 255);

  int magnitude = abs(command);

  analogWrite(pwmPin, magnitude);

  if (command > 0) {

    digitalWrite(inA, HIGH);
    digitalWrite(inB, LOW);

  } else if (command < 0) {

    digitalWrite(inA, LOW);
    digitalWrite(inB, HIGH);

  } else {

    digitalWrite(inA, LOW);
    digitalWrite(inB, LOW);

  }
}

// --------------------------------------------------
// 10. COMMAND BOTH MOTORS
// --------------------------------------------------

void driveMotors(int command) {

  command = constrain(command, -MAX_PWM, MAX_PWM);

  setOneMotor(
      ENA,
      IN1,
      IN2,
      command,
      LEFT_POLARITY
  );

  setOneMotor(
      ENB,
      IN3,
      IN4,
      command,
      RIGHT_POLARITY
  );
}

// --------------------------------------------------
// 11. STOP MOTORS
// --------------------------------------------------

void stopMotors() {

  analogWrite(ENA, 0);
  analogWrite(ENB, 0);

  digitalWrite(IN1, LOW);
  digitalWrite(IN2, LOW);

  digitalWrite(IN3, LOW);
  digitalWrite(IN4, LOW);
}

// --------------------------------------------------
// 12. INITIALIZE THE IMU
// --------------------------------------------------

bool initialiseMPU() {

  if (!mpu.begin()) {
    return false;
  }

  mpu.setAccelerometerRange(
      MPU6050_RANGE_4_G
  );

  mpu.setGyroRange(
      MPU6050_RANGE_500_DEG
  );

  mpu.setFilterBandwidth(
      MPU6050_BAND_21_HZ
  );

  return true;
}

// --------------------------------------------------
// 13. SETUP
// --------------------------------------------------

void setup() {

  Serial.begin(115200);

  Wire.begin();

  // Configure motor pins.
  pinMode(ENA, OUTPUT);
  pinMode(IN1, OUTPUT);
  pinMode(IN2, OUTPUT);

  pinMode(ENB, OUTPUT);
  pinMode(IN3, OUTPUT);
  pinMode(IN4, OUTPUT);

  // Motors must remain stopped at startup.
  stopMotors();

  Serial.println(
      F("Self-balancing robot starting...")
  );

  sensorReady = initialiseMPU();

  if (!sensorReady) {

    Serial.println(
        F("ERROR: MPU6050 not detected.")
    );

    Serial.println(
        F("Check power, SDA, SCL and libraries.")
    );

    stopMotors();

    while (true) {
      delay(500);
    }
  }

  // Obtain an initial angle estimate.
  sensors_event_t accel;
  sensors_event_t gyro;
  sensors_event_t temp;

  mpu.getEvent(
      &accel,
      &gyro,
      &temp
  );

  angleDeg = readAccelPitchDeg(
      accel.acceleration.x,
      accel.acceleration.y,
      accel.acceleration.z
  );

  previousMicros = micros();

  Serial.println(
      F("MPU6050 initialized.")
  );

  Serial.println(
      F("Verify sensor axes and motor direction.")
  );
}

// --------------------------------------------------
// 14. MAIN CONTROL LOOP
// --------------------------------------------------

void loop() {

  // Check control-loop timing.
  unsigned long nowUs = micros();

  unsigned long elapsedUs =
      nowUs - previousMicros;

  if (elapsedUs < LOOP_US) {
    return;
  }

  previousMicros = nowUs;

  float dt =
      elapsedUs / 1000000.0f;

  // Reject abnormal timing intervals.
  if (dt <= 0.0f || dt > 0.05f) {

    integralTerm = 0.0f;
    previousError = 0.0f;

    stopMotors();

    return;
  }

  // ------------------------------------------------
  // Read sensor measurements
  // ------------------------------------------------

  sensors_event_t accel;
  sensors_event_t gyro;
  sensors_event_t temp;

  mpu.getEvent(
      &accel,
      &gyro,
      &temp
  );

  // ------------------------------------------------
  // Calculate accelerometer angle
  // ------------------------------------------------

  float accelPitch = readAccelPitchDeg(
      accel.acceleration.x,
      accel.acceleration.y,
      accel.acceleration.z
  );

  // ------------------------------------------------
  // Calculate gyroscope angular velocity
  // ------------------------------------------------

  /*
    The Adafruit library reports gyro values in rad/s.

    This example uses gyro X to match the example
    accelerometer axis convention.

    Change the gyro axis if your sensor is mounted
    differently.
  */

  float gyroRateDegS =
      gyro.gyro.x * 180.0f / PI;

  // ------------------------------------------------
  // Complementary filter
  // ------------------------------------------------

  float gyroAngle =
      angleDeg + gyroRateDegS * dt;

  angleDeg =
      ALPHA * gyroAngle
      + (1.0f - ALPHA) * accelPitch;

  // ------------------------------------------------
  // Calculate angle error
  // ------------------------------------------------

  float error =
      targetAngle - angleDeg;

  // ------------------------------------------------
  // Fallen-robot safety stop
  // ------------------------------------------------

  if (fabs(angleDeg) > FALL_ANGLE_DEG) {

    stopMotors();

    integralTerm = 0.0f;

    previousError = error;

    if (millis() - lastPrintMs > 250) {

      Serial.print(
          F("SAFE STOP, angle = ")
      );

      Serial.println(angleDeg, 2);

      lastPrintMs = millis();
    }

    return;
  }

  // ------------------------------------------------
  // PID PROPORTIONAL TERM
  // ------------------------------------------------

  float P = Kp * error;

  // ------------------------------------------------
  // PID INTEGRAL TERM
  // ------------------------------------------------

  integralTerm += error * dt;

  integralTerm = constrain(
      integralTerm,
      -MAX_INTEGRAL,
      MAX_INTEGRAL
  );

  float I = Ki * integralTerm;

  // ------------------------------------------------
  // PID DERIVATIVE TERM
  // ------------------------------------------------

  float derivative =
      (error - previousError) / dt;

  float D = Kd * derivative;

  previousError = error;

  // ------------------------------------------------
  // Combine PID terms
  // ------------------------------------------------

  float output = P + I + D;

  // Convert to signed motor command.
  int motorCommand = (int)constrain(
      output,
      -MAX_PWM,
      MAX_PWM
  );

  // ------------------------------------------------
  // Apply motor command
  // ------------------------------------------------

  driveMotors(motorCommand);

  // ------------------------------------------------
  // Print diagnostic data every 100 ms
  // ------------------------------------------------

  if (millis() - lastPrintMs >= 100) {

    Serial.print(F("Angle: "));
    Serial.print(angleDeg, 2);

    Serial.print(F(" | Error: "));
    Serial.print(error, 2);

    Serial.print(F(" | P: "));
    Serial.print(P, 2);

    Serial.print(F(" | I: "));
    Serial.print(I, 2);

    Serial.print(F(" | D: "));
    Serial.print(D, 2);

    Serial.print(F(" | PID: "));
    Serial.print(output, 2);

    Serial.print(F(" | PWM: "));
    Serial.println(motorCommand);

    lastPrintMs = millis();
  }
}
