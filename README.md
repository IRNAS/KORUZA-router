# KORUZA-router

KORUZA router is an open hardware open software development of a routing platform to be used in wireless optical system KORUZA as the control and routing platform as well as secondarily as management for wireless outdoor routers typically used in mesh networks. This repository currently serves as the ongoing requirements base for developing such a device.

# KORUZA - Primary use-case
This router is the heart of KORUZA system and runs all applicaiton specific code, alignment algorithms and user interface. It is connected with the followin:

Internally:
 * SFP module for wireless link (1G/10G data + i2c)
 * webcam (usb)
 * stepper controller+io (uart,i2c,usb)
 
Externally:
 * WiFi backup (1Gbps ethernet + PoE)
 * Secondary KORUZA unit (1Gbps ethernet + PoE)
 * User router (1Gbps ethernet + PoE)
 
# WISP/Community backbone node switch/management - Secondary use-case
Used to connect different outdoor wireless routers together and power them with added management, much like existing Ubiquiti and Mikrotik devices with such support, however being completely open, versatile and running open software with external peripherals well supported

* DC/AC input for power supply
* Fiber input for isolation
* Several network ports (1Gbps ethernet + PoE)
* Sensor input and device protection
 
## Base
The "reference" design used for this specification is MqMaker WiTi board https://mqmaker.com/ which is open hardware developed for home router application. We aim to change it for mesh routing and such type of development.

Requirements are a separate file and entries there are based on closing issues.

## Wish list
Hereby we list all the different ideas that could be included, later defined in specification if accepted. Please open an issue for every feature and we will discuss if it should be implemented or not.

* DC/AC power input
* PoE input, passive 24V or 48V
* PoE output on all ports
* PoE switch and consumption measurement per port
* Microcontroller based system watchdog, router reset circuit
* Two USB ports
* UART, I2C port
* 2 SFP ports
* 10Gbps pass-trhough between ports with retiming
* WiFi 2.4Ghz for local access
* WiFi 5GHz expansions socket
* GPIO ports
* Relay expansion



