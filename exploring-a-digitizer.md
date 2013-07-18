---
comments: true
date: 2010-09-03 22:50:22
layout: post
slug: exploring-a-digitizer
title: Exploring a Digitizer
wordpress_id: 9
categories:
- Demo
- Favorites
- Modification
tags:
- arduino
- draw
- pen
- serial
- touch
---

[![](http://www.hackniac.com/blog/wp-content/uploads/2010/09/project_digitizer_inprogress.jpg)](http://www.hackniac.com/blog/wp-content/uploads/2010/09/project_digitizer_inprogress.jpg)

Just about a week ago I was in charge of resolving an IT crisis at my dad's business. While I was there I picked up this unused but extremely neat old digitizer. Its original purpose was to make digital measurements of architectural plans. I decided that I wanted to hack it to serve as a generic digital drawing pad for my computer.

<!--more-->

External
--------

[![](http://www.hackniac.com/blog/wp-content/uploads/2010/09/project_digitizer_surface.jpg)](http://www.hackniac.com/blog/wp-content/uploads/2010/09/project_digitizer_surface.jpg)

The most obvious part of the hardware for the digitizer is the drawing surface itself. The message in the corners boasts "Redundant Grid Technology". I know that devices like these often use a system with a grid of wires embedded in the surface that interact with the pen to read its location, so it seems likely that the "Grid Technology" is exactly this.

[![](http://www.hackniac.com/blog/wp-content/uploads/2010/09/project_digitizer_pen.jpg)](http://www.hackniac.com/blog/wp-content/uploads/2010/09/project_digitizer_pen.jpg)

To use the digitizer you must use the special pen. It is not wireless so the cord must be constantly shifted as you use it but the pen feels rather nice, even with its odd hexagonal shape. On the very tip of the pen there is a rounded metal pin that serves as the cursor point so you know where you are clicking/drawing. It is attached internally to a button so when you press down on it there is a click in the pen and the digitizer beeps to let you know it registered a click. A bit farther up the pen there are two buttons, one colored black and the other white. The buttons are easily pressed while using the pen to access additional features.

[![](http://www.hackniac.com/blog/wp-content/uploads/2010/09/project_digitizer_card.jpg)](http://www.hackniac.com/blog/wp-content/uploads/2010/09/project_digitizer_card.jpg)

A very handy feature of the digitizer revolves around the use of this little card. It is called "Custom Configuration Quick Reference". To use it you put it anywhere on the drawing surface, click on the P in the corner of the surface, click on the two labeled points on the card, and then click the buttons on the card as if they were part of a computer GUI. Hovering the pen over a previously selected option results in a beep from the digitizer. Options that you can change include the baud rate, the number of data and stop bits, the mode, and basically anything else related to the serial output of the surface. The myriad of communication options on this card makes hacking the digitizer a piece of cake.

[![](http://www.hackniac.com/blog/wp-content/uploads/2010/09/project_digitizer_ports.jpg)](http://www.hackniac.com/blog/wp-content/uploads/2010/09/project_digitizer_ports.jpg)

The side of the digitizer has three ports. On the left is the power connection, which is rated at 9 volts D.C. In the middle is the serial connection used to interface with the digitizer. On the right side is the pen cable connector. The serial cable that was included has a DB9 connector on the other end, but my computer does not have any I/O ports using that connector. I've got some motherboards sitting around that have DB9 connections but I didn't feel like spending the time to put together a computer, get it working, and then write an driver just to use the digitizer.

Internal
--------

[![](http://www.hackniac.com/blog/wp-content/uploads/2010/09/project_digitizer_board.jpg)](http://www.hackniac.com/blog/wp-content/uploads/2010/09/project_digitizer_board.jpg)

When I finally opened the case I was greeted by a delightful sticker. "DO NOT SLIDE BEYOND THIS POINT SERIOUS DAMAGE WILL RESULT", it said, but I paid it no heed and instead went ahead with the thought, "there must be electronic goodies they don't want me to see!", and I was right. The board is very well designed. At the end of the board is a flex-ribbon connector that attaches to the wire matrix embedded in the surface of the digitizer. Next to the connector is a huge array of passive components, resistors and caps, that format the signals coming from the grid and pass it to two massive shift registers. The registers are wired to an MC68 microcontroller socketed further down the board. I was delighted when I found the socketed MC68, because in theory I could reprogram it for my own uses without having to desolder it from the board. The rest of the board is taken up by opamps and passive circuitry that formats data going to and from the pen and data going over the serial bus. In the upper right of the board is a piezo speaker used to emit beeps for feedback to the user.

Getting the data
----------------

My original idea was to write a Windows driver for the digitizer so that I could use it as a mouse for my computer. The fact that my computer does not have a DB9 connector threw a wrench in that idea, so I decided to go exploring in the hardware to hopefully find a 5v serial interface that could be directly used with a microcontroller of my choice. Within about half an hour I had sniffed out the predicted 5 volt serial line on the board. It could have taken much less time but I was having trouble following some convoluted traces on the board. I soldered a wire to the line just before it gets to the opamp that raises the voltage to RS232 levels and then put everything back into the case. I used an Arduino for its FTDI serial-to-USB converter, and with a few jumper wires I was able to utilize the data in applications on the computer. I wrote a simple Processing sketch to allow the digitizer to draw pictures, and lo and behold it all worked:

[![](http://www.hackniac.com/blog/wp-content/uploads/2010/09/project_digitizer_proto.jpg)](http://www.hackniac.com/blog/wp-content/uploads/2010/09/project_digitizer_proto.jpg)

Further plans
-------------

The most obvious thing to do is convert the digitizer to serve as a mouse for my computer. It should be easily accomplished using the V-USB library for atmega chips and a small board inside the case of the digitizer with a USB port. Having it show up as a mouse in Windows would let me use it to draw nice pictures and do stuff that requires a lot of control.

Using the board as a playing field for some kind of physical game is an idea that I like. Maybe having the game field be invisible and only revealed by the pen would be fun. The feeling that I got when navigating the menus using only sound as feedback was interesting, something that could be the basis of a fun game.

[edit: I used the Java Robot API to control my mouse with the plotter. It was fun to play with but ultimately not very useful.]
