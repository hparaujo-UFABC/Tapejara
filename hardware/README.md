
![tapejaraProject02.png](https://image.easyeda.com/oshwhub/pullImage/bb901b24ff3f4992817f9b3c5bbfd46f.png)

# Video link：
First [flight](https://youtu.be/oPYGQzMy-3I) of Tapejara

&gt; Errata: The pinout of the OV2640 camera connector is mirrored: 1 &lt;-&gt; 24 | 24 &lt;-&gt; 1. Do not try to connect the camera or it will cause a short-circuit in the PCB.
&gt; A corrected version will be provided in a future update (coming soon).
&gt; All other functionalities remain unchanged. The prototype has been flight-tested via line-of-sight.

# Project introduction
The Tapejara tpj-01 is a quadcopter-style micro-drone equipped with an OV2640 camera and IMU, barometer, and magnetometer sensors. It utilizes an ESP32 microprocessor to collect sensor data, calculate control actions, and provide telemetry.
The drone can be controlled remotely via a mobile app (currently under development).
The tpj-01 was designed to serve as an educational research platform for experimenting with flight firmware, control systems, and data collection. For this reason, the printed circuit board (PCB) allows for expansion via a daughterboard (shield) where additional sensors can be installed.
By the way,  "Tapejara" is a genus of pterosaur that lived in Brazil during the Cretaceous period.

# Project Parameters
* MCU: ESP32-S3 WROOM-1-N16R8
* OV2640 camera
* IMU: MPU-6050
* Barometer: BMP280
* Magnetometer: QMC5883P
* Rotors: coreless 8520 (2x CW + 2x CCW)
* Propellers Diameter: 55 / 65 mm (2x CW + 2x CCW)
* Battery: 1S (3.7V) | 500 mAh
* PCB (X-Frame):
    * Material: FR-4
    * Color: Green
    * Thickness: 1.2 mm
* Remote control via Mobile App and Wi-Fi

# Hardware description
This project consists of the following parts:
* The MCU for flight control (PID + PWM), data sensor collection and telemetry;
* Power management: the primary energy source for the system is an 1S battery that supply the rotors directly. A Buck-Boost regulator generates a stable 3.3V for the MCU and the sensors. The camera also needs LDO regulators for 1.3V and 2.8V, both derived from the 3.3V regulator. The battery is protected against polarity inversion.
* USB/OTG: a type-C micro USB port is used for firmware upload and power supply (during the drone programming). It is protected against ESD (ElectroStatic Discharge).
* PWM: the 4 rotors are controlled via PWM signals generated at the MCU that switch 4 power NMOS FETs.
* Sinalization: 4 LEDs can be used to provide visual feedback to the user. During flight, they are kept on for direction indication (2 red LEDs are positioned at the left-side of the frame and 2 green LEDs at the right-side).
* Shield expansion: it is possible to design a daughterboard for sensor/processing expansion. The main board provides the battery voltage, 3.3V, ground (GND) connection, and 4 ESP32 I/O pins (2 from the I²C sensors connection and 2 additional pins).

The printed circuit board (PCB) itself was designed with an "X" configuration to support the rotors directly, thereby eliminating the need for additional 3D-printed mounts. The design is self-contained.
The battery and camera must be secured to the board using any available means. For the camera, there are two holes on the front of the drone that may be useful.

# Assembling processes
The printed circuit board (PCB) is self-contained. Simply press-fit the four rotors into place (following the markings printed on the board) and mount the camera and battery.
The firmware can be uploaded via the USB port using the Arduino IDE. The serial baud rate is 115200.
To use the Arduino IDE for programming, select this board: ESP32-S3-USB-OTG.
After uploading the firmware, the drone must be configured using the remote control (RC) app.

# Finished product display
3D view of the PCB (top and bottom).

![3D_Tapejara_brd_v1_Top.png](https://image.easyeda.com/oshwhub/pullImage/84055942a0d44c3785745380b575fa5f.png)

![3D_Tapejara_brd_v1_Bott.png](https://image.easyeda.com/oshwhub/pullImage/bb00693431cf4b5ea2bb941bae3684c6.png)

PCB weight of only 12g.


![dronePeso.jpg](https://image.easyeda.com/oshwhub/pullImage/f70d11cf850c429787053734a16b63e1.jpg)

Assembled Drone weight of only 32.36g.


![weightAssembl.jpg](https://image.easyeda.com/oshwhub/pullImage/e069e166afaf4b939e28e9a06cdd0070.jpg)

Final image.


![tapejaraAssembled.jpg](https://image.easyeda.com/oshwhub/pullImage/8ac1b6b6c46a4e6fad9aa9e8dc1dbaad.jpg)
