# FoxTemp 2024

## Intro

The goal of the FoxTemp2024 project is to develop a wireless,
battery powered temperature- and humidity sensor. Wireless in
this case does NOT mean WiFi, but using the 868 MHz ISM band.

This is just the next iteration in a series of very similiar devices, the
previous ones being FoxTemp2022 and FoxTemp2016. The main change
from FoxTemp2022 is that this new iteration does not use
ready made building blocks and just sticks them together,
instead it uses a custom made PCB, designed so that the
design can be sent to a cheap manufacturer that produces
the PCB _and_ already solders most parts on for you.

This project started, because less than a year after constructing
FoxTemp2022 because the parts for FoxTemp2016 were becoming very
painful to source, the main part for FoxTemp2022 (which was a
"Moteino" clone) became unavailable as well.
I then (of course) also wanted a better sensor-chip, namely a
SHT45, but I was unable to find a source for a breakout board
with the 'protective membrane included' variant of
it (SHT45-AD1F). Breakout boards with the other variant
(SHT45-AD1B) were available, but seemed prohibitively expensive
for what they delivered. At the same time, others told me about
chinese PCB prototype assembly manufacturers, that would create
prototypes with the components already soldered on, at
very reasonable prices. I also wanted to finally learn KiCAD.

## Status

As of June 2024, a "Rev. 0" has been designed, targetting
JLCPCB as the manufacturer (meaning it uses parts that that
company had in stock in June 2024), and successfully
produced there. And it actually worked well.

The following picture shows how the boards looked like when
they arrived from JLCPCB. As you can see, most components
are on the front of the board (left in the picture), and
already soldered on. What's missing is the 3x2 ISP pin header,
the battery holder, the wire antenna, and the RFM69HW on the
back. You can also see why you really would not want to
hand-solder the SHT45 - it's the one marked "U2": size
1.5x1.5mm...

<img src="pics/foxtemp2024r0-0.jpg" alt="two half finished foxtemp2024 devices as they arrived from the factory (showing front and back)" width="500">

## Hardware

The hardware design is very similiar to FoxTemp2022.
At the core is an ATmega328P microcontroller, and the
module used for the 868 MHz wireless link is an
RFM69HW - just like in FoxTemp2022.

Most parts should already be soldered on, except:
* the RFM69HW needs to be soldered to the back of the board
* pin headers need to be soldered in
* a battery holder needs to be connected (by soldering on the wires coming from it)

## Firmware

The way this was designed, the FoxTemp2022 firmware
simply works without modifications after you set the AVRs
fuses correctly. You can also instead compile the firmware
in Foxtemp2024, that enables some (minor) additional power
savings for FoxTemp2024, but would not work on the FoxTemp2022
hardware.

All development happens in the FoxTemp2022 repository, and
not here. Just get the firmware from there.

