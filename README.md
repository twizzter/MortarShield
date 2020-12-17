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
# Board development
<br/>"Deadbug" prototype consisted of brick 5v adapter powering Rpi and a lab supply to feed motors. It turned out that those old L298 drivers aren't top notch ;)
<br/>I went with some FET-based bridges. Equipped with PWM current limit, thermal protection and small size, 8814 appeared as decent chip to play with.
<br/>Just open drawer, pull out some old GPS module, add GPIOs to handle buttons/photo shutter, try to fit whole stuff into Rpi's shield space. Sounds like fun!

![alt text](https://github.com/twizzter/MortarShield/blob/main/MortarShieldV1.png?raw=true)
# Prototype testing
<br/>Onboard 5V DC/DC working properly and stable under heavy load, GPS sensivity (with quater-pole-poor-man antenna) was surprisingly good.
<br/>Motor drivers turned out to be way more efficent than L298.
# V1.1
<br/>-Current sense resistors - changed to 2512
<br/>-DRV external reset and fault handling
<br/>-DRV AENBL/BENBL are separated now - microstepping
<br/>-DRV control inputs pulldowns to avoid weird behave during RPI startup
# PCB
Uploaded zip contains gerber and drill data - all you need to make your own board from any PCB manufacturer. I recommend 1.55mm thickness, green soldermask and HASL finish, as those are usually the cheapest options.
