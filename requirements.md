# Requirements for KORUZA routing platform

 * Configuration: 6 port Gigabit router (4x RJ45 + 2x SFP) and KORUZA specific features
 * Design license: Open source hardware
 * Firmware: Openwrt trunk
 * Bootloader: U-Boot
 * Main chip: 
  * CPU: MediaTek MT7621A (integrated switch)
  * 2x GE PHY: (SerDes functionality for SFP)
 * RF: None
 * Flash: 32 MB
 * RAM: 256 (512 if possible) MB DDR2/DDR3
 * Hardware Watchdog: required (discuss with manufacturer)
 
 * Physical interfaces
  * 4x Gigabit ethernet RJ-45 with LED (Passive PoE pins extracted to connector)
  * 1x external SFP+ port with cage with LED
  * 1x internal SFP port without cage with LED
  * Power board connector (2.54mm, dual row)
  * 1x USB 3.0 connector external
  * 1x MicroSD card connector
  * GPIO expansion connector
    * 1x USB 2.0
    * 1x I2C
    * 2x UART
    * 5V power
    * GPIO pins
  * Console UART (4 pin 2.54mm)
  * Push button reset
  * 2x status LED, software controllable (can be switched off in software), all LEDs must be visible from the connector edge of the router
  * Connector layout guide see image for guidance (discuss with manufacturer)
 
 * Power
  * Input: Gigabit Ethernet connector power pins connected to Power board connector
  * Input: Internal 2-pin header on board for 5V input
  * Standalone Power board
   * Passive PoE in/out for every RJ-45 port
   * Voltage regulator for 5V output to power router
   * I2C current/voltage measurement
   * Single cell LiPo battery backup option
   * Voltage measurement via I2C
  * Consumption: TDB (estimated 7-10W with 1 SFP module active)
  
 * Environmental & Mechanical
  * Temperature range:
   * Operating: -20 to +80 °C
   * Storage: -20 to +80 °C
  * Humidity: 5%-90% typical
  * Dimensions: 65mm x 160mm (with 3mm mounting hole in each corner)
  * Enclosure: none
  * Weight: TBD
   
 * Reliability
  * ESD: Conductive 4 kV, Air 8 kV
  * Surge protection: gas discharge arrestors on all RJ-45 ports (subject to cost)
  * MTBF: Over 50000h
   
 * Compliance standard:
  * CE Mark
  * FCC
  * RoHS
   
# Detailed features and implementations - Main router board
Describes specifics for hardware implementation and design requirements on a technical level. The overall KORUZA system consists of 3 standalone boards: Main router board, power supply board and KORUZA control board. Hereby we are specifying router board only.

## SFP interface
There are two SFP port, one is with cage facing the connector edge of the board, and one is internal. The internal SFP port is without the cage, but he will be also facing the connector edge of the board and have space for the cage to be soldered if needed.

 * SFP ports
  * external SFP+ (marked A) (1Gbps) with cage, connected to multiplexer that switches it to SerDes PHY and then to CPU via RGMII port
  * internal SFP (marked B) (1Gbps only), connected to SerDes PHY and then CPU directly to switch

The implementation of SFP ports must comply with SFP MSA standard and power supply must be filtered according to specification.

## I2C Mux
Because the main CPU has only one I2C bus, there is a need for some kind of multiplexing because of two SFP ports. The additional requirement is to have I2C of internal SFP port also on the expander connector like shown in the diagram below.

## Power supply
The main router board operates at 5V power and has a respective input for 5V. PoE functionality is implemented as separate Power supply board that connect though a Power board connector. 

![alt tag](https://github.com/IRNAS/KORUZA-router/blob/1G-router-requirements/KoruzaDiagram1G.png)




