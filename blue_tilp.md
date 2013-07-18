---
comments: true
date: 2012-04-09 17:10:24
layout: post
slug: blue-tilp
title: Blue TILP
wordpress_id: 1139
categories:
- Modification
- Utility
tags:
- attiny
- avr
- bluetooth
- calculator
- hack
- mod
- texas instruments
- ti link protocol
- tilp
---

[![](http://www.hackniac.com/blog/wp-content/uploads/2012/03/calc_front.jpg)](http://www.hackniac.com/blog/wp-content/uploads/2012/03/calc_front.jpg)

I've made my TI-84+ bluetooth-capable using an [RN-42 module](http://www.sparkfun.com/products/10253) and an Attiny85. It now shows up as an bluetooth SPP to any nearby bluetooth-capable devices, but looks completely normal (at least on the outside). The system allows the calculator to be communicated with over bluetooth as if there was a normal direct wired connection to it. The calculator just sees data coming in as if it were being sent from another calculator or a PC. It still allows the calculator's link port to be used normally.

<!--more-->

I plan on using my calculator's new wireless linking ability to give it super-powers. So far I've only used it in a simple chat program, but eventually it will give my calculator the ability to explore complicated 3D graphs and have integrated WolframAlpha access, among many other useful things. It's great advantage lies in its ability to turn my calculator, which by now is almost an extension of my own body, into an interface to any other bluetooth-capable device I want to use it with.


The Hardware
------------

[![](http://www.hackniac.com/blog/wp-content/uploads/2012/03/blue_tilp_guts1.jpg)](http://www.hackniac.com/blog/wp-content/uploads/2012/03/blue_tilp_guts1.jpg)

The Attiny85 that serves as the brain of the project has been put into a rather odd configuration. I bent half of its pins across its bottom so that it could be soldered to a 2x4 male header. Doing this makes it into a plug that can be disconnected for programming and then easily plugged back into the female header inside the calculator. Through that header the Attiny85 is connected to the ring and tip lines heading to the TI link port on my calculator, to the reset and serial lines of the bluetooth module, to 3.3v and to ground.

Power is a trick in this design, for two reasons. The first is that the Attiny85 is a 5v device, but I'm connecting it to a 3.3v bluetooth module directly. That's workable because I'm running the Attiny85 at 3.3v instead of 5v. Reducing the voltage like this does not seem to cause problems, even though it is at the edge of the spec for the chip.

The second problem is that the power supply never shuts off. The calculator is always 'running', but it goes to sleep when the user presses the off button. Right now I don't have any method to deal with that implemented, so my added hardware will suck the calculator dry of power much faster than the time it would have taken the calculator to run dry on its own. However, there is a relatively easy solution. The Attiny85 just needs to figure out when the calc is asleep and then go into a sleep mode itself. This should reduce power consumption very substantially, but I haven't yet figured out a good way for the microcontroller to know when the calculator is asleep.

[![](http://www.hackniac.com/blog/wp-content/uploads/2012/03/blue_tilp_brain.jpg)](http://www.hackniac.com/blog/wp-content/uploads/2012/03/blue_tilp_brain.jpg)


Implementing the TI Link Protocol
---------------------------------

I've made many attempts at reverse-engineering the TI Link protocol over the past few years, and none have been totally successful until now. Communication was so bothersome with the built-in protocol when I made those other attempts that I went as far as to implement UART to use instead (see [this](http://www.hackniac.com/posts/ti-83-uart.html) project for that code).

However, as I've been encountering a lot lately, things I've failed at before are now easily accomplished because of all the knowledge I've gained in the interim. I can't pin down exactly what I didn't understand before about the TILP, but this time I had no trouble implementing it. The Attiny85 can talk easily with the calculator's operating system directly, without needing software modification on the calculator.


Creating a Transparent Link
---------------------------

Once I had the Attiny85 talking to the calculator and talking to the bluetooth module separately, I tried to combine them so that the Attiny85 would be the invisible translator in-between the two. It turned out to be fairly easy to pull off, although it required one bothersome trade-off.

With nothing happening the Attiny85 is actively listening for communication from the calculator. If it receives data from the calculator it passes it straight onto the bluetooth module at 115200 baud serial (implemented in software since the Attiny85 does not have UART hardware). I set up an interrupt for incoming serial communications from the bluetooth module. UART is a timing-critical protocol so I couldn't really get around this. The interrupt writes whatever the incoming data is to a FIFO buffer as quickly as possible for later processing. As long as the Attiny85 sees nothing from the calculator it empties the FIFO buffer over to the calculator.

This allows two-way asynchronous communication to occur. It works fairly well because the TI link protocol is not a timing-critical protocol (to an extent), so it isn't usually bothered when the UART interrupt slows down receiving or transmitting. However, I have noticed that it fails if delayed more than a certain amount. This is a problem if a long continuous message comes in over bluetooth. It causes only the first part of the message to get through.

The only way I see to resolve this problem is by creating packets with a length field for the incoming data so that the microcontroller knows when there is a contiguous transmission and how long it will be, so it won't start talking to the calculator until all of the data is received. This should prevent communications with the calculator from being interrupted as badly.


Next Steps
----------

I've got to make the communications more reliable and fix the power issue. Then I can move onto developing software that makes good use of the wireless connection. The principal device that I will be using my bluetooth calculator with is my tablet computer (running Android). I carry it with me everywhere. including school, so it would be the best device to use to wirelessly extend the capabilities of my calculator. I'm most interested in getting my tablet to perform intensive 3D graphing and to allow my calculator access to WolframAlpha. It should turn in a very useful tool for college.


Update: Code and Schematic!
---------------------------

Two people requested the code and schematics, so here you go:

Code is at github [here](https://github.com/jmptable/bluetilp).

Schematic is here:

[![](http://www.hackniac.com/blog/wp-content/uploads/2012/04/bluetilp_schematic-1024x302.jpg)](http://www.hackniac.com/blog/wp-content/uploads/2012/04/bluetilp_schematic.jpg)
