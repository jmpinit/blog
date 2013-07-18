---
comments: true
date: 2012-03-11 17:27:21
layout: post
slug: gameboy-camera-successfully-hacked
title: Gameboy Camera Successfully Hacked
wordpress_id: 1122
categories:
- Demo
- Modification
- Software
tags:
- avr
- camera
- gameboy
- hack
- nintendo
- satellite
---

[![](http://www.hackniac.com/blog/wp-content/uploads/2012/03/gameboy_cam.png)](http://www.hackniac.com/blog/wp-content/uploads/2012/03/gameboy_cam.png)

I've been working very hard on my [ersat project](http://www.hackniac.com/posts/ersat-teaser.html) this past week. In particular I am trying to finish the sensor module for Ersat 1 (the first working prototype for my demonstration). It has an entire suite of sensors, but the central one is a Gameboy Camera. I want the module to be able to take low-res pictures to send over the ersat network, mostly to give it the feel of a Cold-War era spy satellite, and after some research I decided that the odd Gameboy Camera peripheral would work perfectly. It is cheap and easy to buy online, and it has a fairly simple interface. As an awesome bonus, the very odd "Artificial Retina" sensor chip used in the Gameboy Camera can do some simple image processing on its own, reducing the computational load for the guts of Ersat 1.

<!--more-->

I thought that getting pictures of of it would be a snap and take at most a few days. As usual, that was an optimistic guess. It has taken a little over a week of days working maybe 1-2 hours each to get it up and running. I took 2 other stabs at it during that time before settling on what I have now.

Surprisingly, the challenging aspect wasn't software or hardware. The solution I came up with is simple on both counts. The challenge was overcoming laziness. There is a straightforward datasheet freely available for the artificial retina chip in the Gameboy Camera, but I didn't want to delve into that if I didn't have to, so at first I scoured the web for projects that other people have  already done with it. That search turned up a lot of results, so I thought I was set. Unfortunately it led to a crazy looping path of madness as I tried to get code written by other people to work with my hardware (and a really pitiful spiral of depression as I fought to not spend time completely reformatting/rewriting some horrifically ugly code that one of them wrote).

I attempted to make sense of two projects done by other people before I gave up and made my own solution from scratch using just the information in the datasheet. It has taken 3 days and been a straightforward process. I wish I had started from scratch to begin with. For newbies (like me) out there who want to take some of the pain out of this kind of thing, here's an outline of the process to get something like this up and running:

1. Read the datasheet. It's some of the most boring reading material in the world (just a bit more exciting than EULAs I think), but reading it will give you a sense of what needs to be made and forewarning of gotchas that might lead to days of frustration if missed. Skimming works well for me. I make a list of the basic requirements that must be fulfilled to talk to whatever device it is while I read.
2. Implement the communication and test it! Sometimes writing custom code is not required here and a library will suffice, but if that's the case make sure to test it before continuing. I used my logic analyzer to verify without doubt that the signals were being shuffled around correctly, but often requesting a specific response from the target works just as well.
3. Incrementally build up the functionality. Don't shoot for the full prize right away. In the past I had a lot of trouble with this. I often spent a long time writing ambitious code and then found out that it was fundamentally wrong and had to be rewritten. Even if it takes a significant amount of time, come up with incremental goals to complete before attempting the big end one.

The Solution
------------

[![](http://www.hackniac.com/blog/wp-content/uploads/2012/03/GB_cam_test_lores.jpg)](http://www.hackniac.com/blog/wp-content/uploads/2012/03/GB_cam_test_lores.jpg)

I wrote some simple code in C for an Atmega328p to communicate with the Gameboy Camera. In my demonstration application (the source code can be downloaded below) it uses this code to ask the Gameboy Camera for a picture when prompted over serial by a Java (Processing environment) application running on a PC. The cam then takes a picture and sends it pixel by pixel to the Atmega328p, which in turn sends the pixels over serial to the Java application to be drawn. Within the Java application a mouse click will take a picture, the o, v, and g keys switch modes, and the x position of the mouse sets a camera value denoted by the mode (offset, vref, and gain). The serial communication is very slow, so even though the picture is only 128x128 pixels in 256 level grayscale it takes a few seconds for it to get scanned onto the computer.


Source code
-----------

I put this code out there to help others like me who want to use this cool device, and anyone else who is interested.

[AVR GB Camera Interface](http://www.hackniac.com/blog/wp-content/uploads/2012/03/AVR-GB-Camera-Interface.zip)
