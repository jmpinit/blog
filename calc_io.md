---
wip: true
date: Tue Aug 20 13:33:49 EDT 2013
desc: ti calc + avr mcu
---
I dead-bug soldered an Atmega328p into empty space inside of a TI-83+ calculator and connected it internally to the calculator's power and link port. I then stuck a DB9 port and RGB LED into the back of the case. Then I wrote a software synth in assembly for the AVR. It takes commands from TI-BASIC programs running on the calculator. To make music. Or to do general hacking, because 4 ADC pins, 6 GPIOs, a serial port, one DAC, 3.3v, and ground are exposed on the port.

Here it is generating a sine wave:
![http://hackniac.com/images/calc_out/sine_out.jpg]()

Hardware
--------

* Atmega328p
* DAC - just an RC filter on an AVR PWM pin. Designed for audio output.

TODO: the rest

Todo
----

* AVR TILP bootloader (load code into AVR from calculator)
* AVR firmware to allow the calculator full control (ADC, DAC, IO, serial, sound output)
* TI-BASIC hooks for AVR functionality to make hacking around easier
* Calculator GUI for very basic control of the ports
	* GPIO select input/output
	* read GPIO state
	* read ADC values
	* set DAC output frequency
* [Bus-pirate](http://dangerousprototypes.com/docs/Bus_Pirate)-like functionality
