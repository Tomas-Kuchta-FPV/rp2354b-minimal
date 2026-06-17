# RP2354B Minimal for KiCad 10

This is a realization of the Raspberry Pi RP2350 "Minimal" design.

My main objectives were to try the RP2354 for the internal flash and use the
"B" part for the extra GPIOs.

Going through [Hardware design with RP2350]
(https://pip-assets.raspberrypi.com/categories/1214-rp2350/documents/RP-008280-DS-1-hardware-design-with-rp2350.pdf)
is required to do this stuff and expect good results. It has a link to the
original Kicad 7.0 version.

Changes from the original example:

* Kicad 10.0.3 (was Kicad 7.0). This just means opening the project with
  10.0.3 and immediately saving it.

* RP2354 (was RP2350). This means changing some of the components from
  do-not-populate to populate, and vice versa.

* Added JLCPCB part numbers. There are lots of options for most parts, and I
  just picked ones in stock.

Then I created the manufacturing output for JLCPCB, uploaded the files, and a
week later got apparently-working boards. "Apparently" in that the board I've
tried shows up as a usb drive (Windows) if I hold BOOTSEL, the debugger
(Raspberry Pi debugger under VS Code) connects and can load code, the board
tells me it's running at 150 MHz, and I can blink LEDs after soldering on
headers. I have not tried using the secondary flash, just the internal flash.
The boards look nicely done, including getting the inductors turned the right
way on all five boards I got.

One objective was to change as little as possible, partly because I have not
done any boards with JLCPCB using 0402 and such tiny traces, and would be
unlikely to be able debug it if something didn't work, i.e. the oscillator or
power supply. But they must be fine.

I told VS Code it's a pico-2 to connect to it, so some stuff is probably wrong
(like flash size).

