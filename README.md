# MortarShield
MortarShield is basically a dual stepper motor driver with integrated power supply and GPS module.
![alt text](https://github.com/twizzter/MortarShield/blob/main/ms11.png?raw=true)


# Background
Designed as a part of bigger hobby project https://github.com/kwahoo2/Mortar

The goal was to "electrify" a dobsonian-mounted telescope and connect it with Stellarium.


# Details
Shield is meant to be powered from 12V supply, but should work within 8-15V range.
<br/>Onboard DC/DC converter provides power for Rpi and accesories (3A total)
<br/>Board uses 2x DRV8814 as motor drivers.
<br/>Motor maximum current is limited to 2A for each winding and can be additionally lowered by software.
<br/>I suggest to start with lower currents, as drivers may become hot. 1A is usually enough.
<br/>Stellarium gets position and time from embedded GPS module. Any NMEA-compatible GPS module will work as well, just connect UART to R1/R2.
<br/>Since RPi GPIOs are prone to damage, board is equipped with protection components (220R/double schottky)
<br/>You don't have to populate them if you're not planning to do experiments with board.
# PCB
Uploaded zip contains gerber and drill data - all you need to make your own board from any PCB manufacturer. I recommend 1.55mm thickness, green soldermask and HASL finish, as those are usually the cheapest options.
