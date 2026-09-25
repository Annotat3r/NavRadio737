MobiFlight Custom Device for the Boeing 737NG Multi-Mode Radio (MMR)

developed by Ryan Goff from the MF Community Device Template. It is

based on the Gables Engineering G7501-01 Boeing 737 Nav GLS Panel.



This project was developed for use with X-Plane 12 and the Zibo 

mod Boeing 737. The custom device code is written for the way 

X-Plane 12 outputs data for displaying on the LCD screen. I don't 

believe this code would work for MSFS without modifying.



CAD FILES

The CAD files include .stp (step) for all of the parts but it is important

to understand that I designed the parts with specific manufacturing

equipment in mind. The Acrylic and Plexiglass parts were cut using

a desktop cnc machine, spray painted, and then the text laser-engraved

using a blue-light diode laser.

The buttons were 3D printed using white filament, spray painted black,

and then laser engraved.

Because of the laser-engraving being a step that occurs later, the

CAD files for the faceplate and buttons do not include any text. The

text was added in the laser engraving software.

I have included 737NavRadio\_PCBA.step, which is a step file export of

the custom printed circuit board assembly.



PCBA

The PCBA features an on-board Raspberry Pi Pico (RP2040), making this

a fully self-contained device that requires no additional connections

to external microcontroller devices.

The backlighting is designed to operate off of an external 12V DC power

supply and does not work if only connected to 5V USB. If you are building

this panel and don't have, and don't want to acquire an external 12V

power supply, you will need to make edits to the schematic and board

files. Powering the backlighting from an external 12V source was done

to reduce the overall current requirements of the PCBA vs. powering

them from 5V. The backlighting is fully dimmable via connection to one

GPIO PWM pin through an N-Channel MOSFET.

Nearly all surface-mount devices on the PCB were ordered as part of the

PCB Assembly via jlcpcb.com. Through-hole components such as the 12V

power connection, the USB-Micro connector, 2-pin header for bootsel,

and 4-pin header for connecting the OLED display are user-soldered. All

push-buttons and LEDs on the PCB are user-soldered, though these are

SMT components.

The OLED display purchased must be a 2.42" 128x64 OLED LCD with I2C and

SSD1309 driver. The specific device I used in my build was from AliExpress

TZT 123 Official Store:

https://www.aliexpress.us/item/3256802580414312.html



Download the NavRadio737 custom device and move it to your MF Community

folder directory. Use the RP2040 pin connections shown in the schematic

to set up your mobiflight input/output devices.

