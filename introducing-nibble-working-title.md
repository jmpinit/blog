---
comments: true
date: 2012-07-08 19:03:27
layout: post
slug: introducing-nibble-working-title
title: Introducing Nibble (working title)
wordpress_id: 1208
categories:
- Concept
---

[![](http://www.hackniac.com/blog/wp-content/uploads/2012/07/mockup_edit-1024x531.jpg)](http://www.hackniac.com/blog/wp-content/uploads/2012/07/mockup_edit.jpg)

Above is a mock-up of a new project that I am working on to take to Toorcamp in a month. The mock-up was made at StudentRND in MDF using their laser cutter.

<!--more-->

The specifics of the idea are still heavily in flux right now, but the physical format is pretty solidly set at this point. From the picture you can see that Nibble is a cube with 3 openings. The square one is for a graphical LCD (84x48 monochrome Nokia 3310 probably) and the two holes on the sides are for speakers. Those parts will get hooked up to a microprocessor with a LiPo battery for power giving me a small, dead-simple computer system.

It's not going to just be another retro computer build though! It has a twist. The twist is that some kind of bytecode interpreter go on the machine and will be intimately tied to a Javascript environment (Rhino for Java probably) running on a host machine, with communication happening via a Bluetooth SPP. The combination will allow such things as:

**Code execution on the device!**

	device.reset();
	device.load(ide.compile("
	SET A, 0x1fff
	NOP
	"));
	device.run();

**High-level remote control!**

	device.notify("A toast message on a tiny computer cube!");
	device.beep(4000, 1000); //beep at 4 Khz for 1000 milleseconds

**Easy low-level debugging!**

	alert("Nibble program counter = "+device.PC);


Purpose
-------

The idea is to make a system that is cute and extremely approachable, bridging the gap between high-level and low-level to create a programming toy that combines love of structural simplicity and technical challenge. I believe that making such a connection between a flexible scripting language like Javascript, that is well used and well-known, and a small 8 bit reprogrammable cube will open up many possibilities for fun. Programming is about creating beautiful, logical systems AND fighting for what you want within the limitations of a system that exists in real-world hardware. I want Nibble to be a playground offering a mix of both the great technical challenge that I love in low-level programming and the power-laden freedom that I feel using modern high-level languages.


A note on the bytecode interpreter
----------------------------------

I am writing the system with distinct modules, separating the communications system from the screen and sound interfaces for example. The bytecode interpreter will be mostly independent of the rest of the system. This means that I can write a couple and swap them in and out as I please. This is important because I don't have a concrete plan for the interpreter.

I considered doing a Forth machine to start, but that impulse was quickly killed when I remembered how much writing Forth code sucks (even it's proponents must admit that it's not great in the area of readability). Instead I am going to implement the **DCPU16** from Notch's new game 0x10c. I've been following its development for some time and am continually amazed by its strong community, which has already developed numerous tools and applications for this made-up platform. The DCPU16 specification makes it fairly approachable, and it is widely available on the net with numerous open-source emulators available as examples. I love the idea of 0x10c and feel like it will go a long way towards nurturing a new generation of technological wizards. The ability for someone who loves that game to readily start playing with my own device is very exciting.

So! I will implement a DCPU16 emulator on Nibble to feed off of the hype, community, tools, and code currently flying out of 0x10c. And the theoretical children who will be playing 0x10c will have something familiar to play with, but that can cross the gap out into the real world.
