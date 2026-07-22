# wro2026_MicroBS
# WRO Future Engineers 2026

## Team Information

**Team Name:** MicroBS  
**Country:** Palestine 
**Organization:** BZU  
**Competition Category:** WRO Future Engineers 2026

---

## Project Overview

This repository contains the complete documentation, source code, and engineering development process of our autonomous vehicle designed for the World Robot Olympiad (WRO) Future Engineers 2026 competition.

Our objective is to design and build a reliable autonomous vehicle capable of navigating the competition field, avoiding obstacles, and completing all required challenges while following the official WRO rules.

---

## Vehicle Architecture

The vehicle consists of the following subsystems:

### Mobility System
#### Chassis Structure
  the robot is built on an aluminum body kit, which was selected for its combination of strength, durability, and low weight. The rigid aluminum frame provides a stable platform for mounting all electronic and mechanical components while withstanding the vibrations and impacts encountered during testing and competition. In addition, the chassis offers sufficient space for efficient component placement and weight distribution, contributing to the overall stability of the vehicle.

Most of the mechanical structure was assembled using the aluminum kit, reducing the need for extensive custom manufacturing. However, several parts were designed and produced using 3D printing to better meet our performance requirements. The most significant modification was the creation of larger drive gears. These gears increased the gear ratio between the motor and the wheels, allowing the system to generate higher torque. As a result, the robot achieved smoother acceleration, improved traction, and more reliable performance when navigating turns and obstacles. Testing confirmed that the larger custom gears provided better driving characteristics than the original configuration.

The protective foam bumper holds our sensors in an optimal position while absorbing crash impacts to protect both the track and the fragile front steering mechanism. Additionally, it dampens chassis vibrations to ensure cleaner sensor readings and acts as a physical safety buffer during autonomous runs.
-Chassis Photos

![Front View](images/chassis_front.jpg)


### 🤖 Robot Components Overview
This section provides a detailed overview of the key hardware components used in the ShahroodRC robot for the WRO 2025 Future Engineers category. Each component was carefully selected to ensure compatibility, reliability, and optimal performance for tasks like line following, obstacle avoidance, and precise parking. The components are seamlessly integrated with the LEGO EV3 platform, leveraging our team’s prior experience to streamline development and focus on competition performance.
#### 📐 Dimensions
| Dimension | Measurement |
|--------|--------|
|Length | ............. |
| Width | ...............|
| Height| ..................|
#### 🔧 Components Overview
#### Raspberry Pi 5
![Raspberry Pi 5](images/ras%20pi%205.jpg)

The Raspberry Pi 5 is the main controller of our robot. It is responsible for processing sensor data, running the autonomous navigation algorithms, and sending control commands to the motor driver.

##### Why We Chose Raspberry Pi 5

- High processing power for real-time decision making.
- Supports Python and computer vision libraries.
- Easy integration with sensors and external modules.
- Reliable performance during testing and competition runs.

##### Role in the Robot

The Raspberry Pi 5 performs the following tasks:

- Reads data from the robot's sensors.
- Processes information about the robot's environment.
- Executes navigation and control algorithms.
- Controls the movement of the robot through the motor driver.
- Manages communication between the different electronic components.

##### Integration

The Raspberry Pi 5 is connected to:

- Logitech C270 HD Webcam
- Servo Motor
Connected via control wires to send PWM signals that turn the front wheels left and right.
- L298N Motor Driver
- Power Supply
This cable receives regulated voltage directly from the blue step-down buck converter module mounted on the side, converting raw battery voltage down to a stable 5 v needed to power the Pi without frying it.
- Rear IR Sensor Module:
Connected via a data pin to send  signals back to the Pi when an obstacle is detected behind the chassis.
-Active Cooling Fan
to keep the processor cool inside the enclosure.

  #### Logitech C270 HD Webcam
  ![Logitech C270 HD Webcam](images/cam.jpg)

The primary vision system consists of a front-mounted USB webcam serving as the core perception sensor for track boundary detection, color identification (e.g., distinguishing obstacle markers), and dynamic steering corrections.Sensor Model: Logitech C270 HD WebcamNative Optical Resolution: 720p HD (1280 *720 pixels) at 30 FPS Field of View (FOV):60 diagonal
Interface: Standard USB 2.0 (Bus-powered via compute board)
Operating Voltage : 5.0 V DC (MORE OR LESS BY .05 via USB bus) 
via USB busPeak Current Draw: 500 mA (2.50 W peak power draw)

##### Why We Chose the Logitech C270

- Provides reliable image quality for computer vision applications.
- Supports HD video resolution (1280 × 720).
- Compatible with the Raspberry Pi 5 and OpenCV libraries.
- Lightweight and easy to mount on the robot.
- Affordable and widely available.

##### Role in the Robot

The Logitech C270 is responsible for:

- Capturing live video of the competition field.
- Detecting obstacles and track boundaries.
- Providing visual data for image-processing algorithms.
- Supporting navigation and decision-making during autonomous operation.

##### Technical Specifications

- Resolution: Up to 1280 × 720 (HD)
- Frame Rate: Up to 30 FPS
- Connection: USB 2.0
- Fixed-focus lens
- Plug-and-play compatibility with Raspberry Pi OS

##### Integration

The Logitech C270 is connected to the Raspberry Pi 5 and provides real-time images for the robot's vision system.

#### Motor Driver (L298N Dual H-Bridge Module)

#### DC-DC Buck Converter

The DC-DC Buck Converter is used in our robot's power management system. Its purpose is to reduce the battery voltage to the voltage levels required by different electronic components.

##### Why We Chose a Buck Converter

- Provides a stable output voltage.
- Efficiently converts power with minimal energy loss.
- Protects sensitive electronic components from overvoltage.
- Supports reliable operation of the robot during competition.

###### Role in the Robot

The buck converter receives power from the main battery and reduces the voltage to the required level for the robot's electronic systems. This ensures that all components receive a safe and stable power supply.

###### Integration

The buck converter is connected between the battery and the electronic components that require a lower operating voltage. It supplies regulated power to the control and sensing systems, improving the overall reliability of the robot.

###### Benefits

- Stable power delivery.
- Improved energy efficiency.
- Increased protection for electronic components.
- Reliable operation throughout the competition.

#### DC motor
#### Servo motor
#### IR Sensor
The rear infrared sensor module acts as an optical proximity detector for short-range obstacle sensing behind the chassis base. It operates on the principle of active light reflection to detect walls, track boundaries, or collision risks during reverse maneuvers.
Module Type: Active Infrared Optical Reflection Sensor (Dual Diode Pair).Operating Voltage (3.3 V - 5.0V ).Current Draw= approx 20mA (Low-power peripheral).Detection Distance Range= approx 2cm - 30 cm (Adjustable via onboard potentiometer).Signal Output: Digital Output (DO - HIGH/LOW logic level) and Analog Output (AO).Onboard Signal Conditioning: Integrated LM393 voltage comparator IC with status LED indicators.



### Drive mechanism
The robot uses a rear-wheel-drive mechanism powered by a single DC motor. Motion is transmitted from the motor to the rear axle through a two-gear transmission system. The two rear wheels are mechanically linked by a metal axle, ensuring that both wheels rotate together and provide consistent propulsion.

To enhance the performance of the drive system, custom gears were designed and manufactured using 3D printing. The larger gears increased the transmission ratio, allowing the robot to generate greater torque at the wheels. This improvement resulted in smoother acceleration, better traction, and more stable movement while navigating the track. Multiple tests were conducted to evaluate different gear configurations, and the final design was selected for its balance between driving power, reliability, and control.
- Steering mechanism
- Mechanical components

### Power System
- Power Flow Architecture 
![Power distribution](images/batteryDist.png)
 
                                                   
- Battery
- Master Power Control:Switch Type: Panel-mounted I/O rocker switch integrated along the chassis side frame.Function: Provides physical circuit isolation and emergency system shut-off.DC-DC Step-Down Buck Converter:Monitoring: Integrated 3-digit, 7-segment red LED display for real-time voltage monitoring.
- Regulation Hardware: Features a toroidal core inductor, input/output electrolytic filter capacitors, an aluminum heat sink, and multi-turn precision potentiometers.
- Primary Battery Interface:Configuration: Integrated chassis battery tray fitted with high-tension spring terminal contacts.


### steering System
### sensor system
-[camera](#logitech-c270-hd-webcam)
Placement: Positioned at the extreme front deck, mounted forward over the front axle bumper.

Geometry Rationale: Mounting the camera at the front edge eliminates chassis obstruction from the field of view. The forward-angled orientation creates an optimal trapezoidal perspective on the track floor, capturing both immediate track boundary lines and oncoming obstacle pillars several meters ahead.


-[IR Sensor](#ir-sensor)
Rear IR Sensor Placement:

Placement: Center-aligned on the rear lower chassis deck, pointing directly outward.

Geometry Rationale: Eliminates blind spots directly behind the vehicle during reverse alignment maneuvers or back-up routines without interfering with the rear spur gear mechanism.

Location: Center-mounted at the lower rear chassis frame.

Orientation: Pointed horizontally backwards, aligned with the central longitudinal axis of the vehicle.

Geometry Rationale:

Eliminates rear optical blind spots during reverse parking/alignment routines.

Positioned on the lower deck to detect low-profile obstacles without obstructing the rear spur gear mechanism or axle clearance.

To establish a reliable trigger threshold under varying ambient light conditions:Physical Setup: Place an obstacle (e.g., track wall/pillar) at the desired trigger threshold distance = 10 cm directly behind the rear chassis.Potentiometer Tuning: Rotate the onboard blue multi-turn trimmer potentiometer clockwise/counterclockwise using a small screwdriver.Threshold Lock: Adjust until the onboard status indicator LED turns ON precisely when the object is at 10 cm and turns OFF when the object moves beyond10 cm

Sensor Tradeoffs & Failure Mitigation:Short-range sensing 10 cm compared to Ultrasonic or LiDAR sensors.  

### Software System
- Lane following
- Obstacle avoidance
- Steering control
- Autonomous decision making

---


---

## Team Members

| Name | Role |
|--------|--------|
| Beesan| ............. |
| Sarah | ...............|
| Majeed | ..................|

---

## Robot Photos

### Front View
![Front View](images/front%20view.jpg)

### Rear View
![Rear View](images/back%20view.jpg)

### Left Side View
![Left Side View](images/left%20side.jpg)

### Right Side View
![Right Side View](images/right%20side.jpg)

### Top View
![Top View](images/top%20view.jpg)

### Bottom View
![Bottom View](images/bottom%20view.jpg)
---

## Videos

Links to autonomous driving demonstrations will be provided before the competition.

---

