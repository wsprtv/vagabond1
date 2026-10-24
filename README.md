# Vagabond1 WSPR Transmitter

<img src="images/intro.png" height=300>

Vagabond1 is a tiny WSPR transmitter that piggybacks on the popular
[ESP32 C3 Super Mini board](https://www.espboards.dev/esp32/esp32-c3-super-mini).
It contains only 11 components (including 7 passives).
Vagabond1 is fully supported by
[Nomad](https://github.com/wsprtv/nomad) firmware.

## Links

- [Schematic](https://wsprtv.com/vagabond1/docs/vagabond1.pdf)
- [Interactive BOM](https://wsprtv.com/vagabond1/docs/ibom.html)
- [KiCad Files](https://github.com/wsprtv/vagabond1/tree/main/kicad)
- [JLCPCB Fabrication Files](https://github.com/wsprtv/vagabond1/tree/main/fabrication)
- [Nomad Firmware](https://github.com/wsprtv/nomad)
- [ESP32 C3 Super Mini Documentation](https://www.espboards.dev/esp32/esp32-c3-super-mini/)

## Assembly

Vagabond1 boards can be assembled at JLCPCB using
[these fabrication files](https://https://github.com/wsprtv/vagabond1/tree/main/fabrication).
Select 0.8mm board thickness.

When soldering Vagabond1 and ESP32 C3 Super Mini boards together, orient them
so that the GPS module is away from the USB-C port.

## ESP32 C3 Super Mini Modifications

The ESP32 board needs two modifications when powered with solar cells.

1. The RESET line on the ESP32 needs to be routed to pin 2 to enable voltage
monitoring. Connect the two pads with a wire as shown below:

<img src="images/mod1a.png" height=400>

2. [Optional] Replace the reverse polarity protection diode on VSYS with a 0-ohm
resistor or a short wire to eliminate an unnecessary 0.2V drop. Also,
consider removing the always-on power LED or the associated current-limiting
resistor (or both) to save ~0.8 mA. The image below shows the location
of the diode (top highlighted component), followed by the resistor
and the LED.

<img src="images/mod2.png" height=400>

## Power / Antenna Connections

<img src="images/connections1.png" height=500>

## I2C Sensor Connections

<img src="images/connections2.png" height=450>
