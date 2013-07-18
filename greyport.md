---
date: 2011-09-09 22:26:13
title: Greyport
---

[![](http://www.hackniac.com/blog/wp-content/uploads/2011/07/Boarded-1024x768.jpg)](http://www.hackniac.com/blog/wp-content/uploads/2011/07/Boarded.jpg)

Greyport is designed to turn the world into an open hardware hacking playground. Loosely based on the user interface of the highly popular line of TI calculators, the goal of the project is to build a device that can be used as a portable electronics hacking tool. A target device can be easily connected to Greyport and a script to communicate with and control the target can be rapidly written on Greyport itself. Because the user-created scripts can be written quickly and stored for later use they turn Greyport into a hugely multipurpose digital electronics tool. An online collection of scripts created by other users could further extend the usefulness of the device.

<!--more-->

System
------

At the heart of Greyport is an Atmega1280, which is part of the popular AVR line of RISC microprocessors. The core system is comprised of the 1280, a TFT color LCD, a keyboard module, an SD card, and a large bank of I/O connections that can be connected to any system using standard test cables.

On the software side of things there is an operating system written in C with assembly optimization sitting in the ROM of the 1280. Part of the core of the OS is a bytecode interpreter, because a limitation of the AVR line is that the instruction pointer cannot point to addresses in RAM, so machine code cannot just be dumped into RAM to be executed when an application needs to be run. Greyport's flexibility requires that it be possible for user code to be run from RAM. Many general-purpose functions are included in the default kernel so that they do not have to be implemented in the slower bytecode. Since the code is all open source the user is free to modify the OS to fit their needs.

The first programming language the system will support (besides pure bytecode of course) is a perversion of BASIC named greyBASIC. A compiler written in bytecode takes a greyBASIC language source file from memory and turns it into bytecode that can be executed. Using the compiler and a text editor it is possible for the user to develop applications on the device without ever touching a PC.


Progress So Far
---------------

The project website is [here](http://www.greyportal.com), although it is no longer updated and is not in a great state. I worked on greyport for a year before bringing a friend onto the project. We completed the first working prototype for an independent study at our high school and presented it to the gifted student support staff at the end of that school year. You can see a copy of that presentation below:
