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
company had in stock in June 2024), and sent off to them for
manufacturing.
The result has not been received yet, thus it is unknown
if "Rev. 0" works at all, or needs fixes.

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

The way this was designed, the FoxTemp2022 firmware should
simply work without modifications after you set the AVRs fuses
correctly. It is planned to make changes to the firmware
that enable additional power savings for FoxTemp2024. That
development will happen in the FoxTemp2022 repository, and
not here.

