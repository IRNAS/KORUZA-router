# MqMaker WiTi board modification

For prototyping of KORUZA v2 https://mqmaker.com/doc/WiTi/ WiTi board is used, but requires a number of modifications as follows:

Remove components:

* RP-SMA antenna connectors
* Power connectors for SATA
* SATA connectors
* Diode D1 (Disables RTC and clears I2C address 0x50)
* Diode D2 (Disables RTC and clears I2C address 0x50)

## PoE modification (802.3af Mode B)
Passive gigabit PoE can be added to WiTi board by modifying the board and adding an external step-down regulator. Ethernet poinout for Ubiquiti gigabit PoE injectors 2-Pair Powering (model POE-24-24W) is +(4,5)pins, (7,8) pins and gigabit 4-Pair Powering (model POE-24-24W-G) is +(1,2)(4,5)pins, -(3,6)(7,8) pins. Note that if you use PoE without removing reistors, you will burn them, but nothing else bad should happen.

### PoE modification 2-pair
Remove resistors on the port(s) for 2-pair PoE for gigabit operation, TAP on magnetics needs to be used. Then add a wire to the pad of the resistor that is oriented towards the ethernet connector.

* LAN0 (SW0), remove R303 (DC-), R302 (DC+)
* LAN1 (SW1), remove R313 (DC-), R312 (DC+)
* LAN2 (SW2), remove R323 (DC-), R322 (DC+)
* LAN3 (SW3), remove R333 (DC-), R332 (DC+)
* WAN0 (SW4), remove R343 (DC-), R342 (DC+) (KORUZA default)
* WAN1 (SW5), remove R798 (DC-), R797 (DC+)

### PoE modification 4-pair
Remove resistors on the port(s) for 4-pair PoE for gigabit operation, TAP on magnetics needs to be used. Then add a wire to the pad of the resistor that is oriented towards the ethernet connector.

* LAN0 (SW0), remove R303 (DC-), R302 (DC+)
* LAN1 (SW1), remove R313 (DC-), R312 (DC+)
* LAN2 (SW2), remove R323 (DC-), R322 (DC+)
* LAN3 (SW3), remove R333 (DC-), R332 (DC+)
* WAN0 (SW4), remove R343 (DC-), R342 (DC+) (KORUZA default)
* WAN1 (SW5), remove R798 (DC-), R797 (DC+)
