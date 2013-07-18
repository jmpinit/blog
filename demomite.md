---
comments: true
date: 2012-01-30 23:00:48
layout: post
slug: demomite
title: Demomite
wordpress_id: 927
categories:
- Demo
- Device
- Favorites
tags:
- arduino
- assembly
- attiny
- attiny2313
- avr
- binary
- bit
- challenge
- chip
- chiptune
- code
- cut
- demo
- demoscene
- device
- dip
- diy
- dremel
- electronics
- gadget
- hack
- hacking
- hackniac
- hardware
- Integrated Circuit
- isp
- lcd
- machine
- make
- maker
- mcu
- micro
- microcomputer
- microcontroller
- music
- nokia3310
- plastic
- programming
- protoboard
- prototype
- pwm
- small
- software
- solder
- speaker
- timelapse
- tiny
- transistor
- veroboard
- wire
---

[![](http://www.hackniac.com/blog/wp-content/uploads/2012/01/demomite_lores_full.jpg)](http://www.hackniac.com/blog/wp-content/uploads/2012/01/demomite_lores_full.jpg)

Now mid-way through my senior year of high school, it has been a while since I finished applying to colleges. In fact, it's almost time to start receiving their possibly life-altering decisions. However, before that happens there is one last hurdle to cross: the mid-year report, a list of my current grades and midterm exam results sent to the academic institutions I've applied to so that they can be assured that I really am the high-achieving student that I tried to present myself as in my application. Besides the obvious gift of stress, this report also presents an opportunity. Some schools allow "additional materials" to be submitted along with the report. This project is my additional material, designed to demonstrate the extent of my abilities - and more importantly, show that I am serious about taking advantage of my potential when I get to college.

<!--more-->

A Tiny (2313) Demo (Dyna)Mite
-----------------------------

I had planned to do a project to send with my mid-year report, but I didn't know what form it would take. Last weekend I finally had the first chance to take a shot at actually creating something for it, because that weekend marked the end of midterms at my school, and with them the end of intense studying and stress. Unfortunately that Friday and Saturday my inspiration failed me. I piddled around with various experiments I've been working on hoping that one would spark a brilliant idea for a project, but none managed any success towards that goal. As a result, late Saturday night I was pretty fed-up with myself and frankly a little depressed.  "How dare my brain choose this time to quit creating", I was thinking to myself. Fortunately my frustration led me to muse about attempting ideas I had previously thrown out for perceived lack of genius/complexity, and Demomite was born.


Ignore the snazzy portmanteau (it's really quite simple)
--------------------------------------------------------

The idea for this project was incepted by my previous [TinyAsmCopter project](http://www.hackniac.com/posts/tiny-asm-copter.html). Demomite is a tiny handheld game device designed to provide a platform for software demos. In the computing world a demo is a demonstration of programming/artistic/musical ability. It's specs are severely limited on purpose to make programming for it more challenging**:**


### Computing power:

* **attiny2313 microcontroller**
* **8 MHz CPU w/ ~8 MIPS**
* **2 kilobytes of program memory**
* **128 bytes of RAM**
* **128 bytes of EEPROM**


### Graphics:

* **Nokia 3310 LCD**
* **84x48 pixels**
* **black and white**
* **serial interface (slow)**


### Sound:

* **built-in speaker**
* **simple 1-transistor amplifier**
* **PWM (1 bit) signal**


### Controls:
	
* **N.E.S. controller**
* **shift interface w/ min. ~110 microsecond read time**
* **8 buttons**


### Misc:
	
* **removable 400 mAh LiPo rechargeable battery**
* **DC-DC boost converter (increased power efficiency) -** LiPower from Sparkfun


Building It
-----------

I had the idea Saturday night, and finished building it Sunday night. I worked with parts that I already had on-hand, so the process was fairly straightforward. To start I prototyped the electronics on a breadboard, connecting the LCD then N.E.S. controller then amplifier/speaker. After writing a bit of assembly code to show that each of those parts worked properly I started putting it all into a handheld form.

I did not know what I would do for the case, so I just grabbed the box that I fill with junk pieces of plastic for this very purpose and dumped it on my desk. After half of an hour of holding together pieces of plastic and the electronics I finally settled on a design using the lids of two project boxes from RadioShack. It's just the right size, but an odd design because there is an open slit around the edge. The detriments of not having a sealed enclosure were outweighed by the benefits of the size and look though, so I went ahead with it. I cut a squarish hole for the LCD, some small holes for the speaker, and everything fit nicely.

Transferring the circuit to breadboard went along with no hiccups, even though I did it by eye without ever writing down a design (don't try that at home folks). A few tacks of hot glue secured the mainboard in place and reinforced the wired connections. Painters tape insulated the bare connections and held down the wires. I chose a switch that would fit perfectly into the slit around the edge and made a stand-off for it by ripping apart a CD drive front. The battery compartment is a bent piece of metal from an ancient camcorder, which is simply hot-glued to the top part of the case.

Connecting the N.E.S. controller to the main enclosure proved to be a challenge. I didn't want to mess with the outside by placing a reinforcing strip of plastic or something else, and I didn't want to just hot glue the two together because that would interfere with disassembly. In the end I just took more of the plastic strip that I used to offset the switch and attached it to the N.E.S. controller so that it can be slotted into the slit around the edge of the enclosure. It is slick because I can un-slot the controller and fold the thing in half to fit in my pocket, but when it is slotted it can easily separate again and there's  a lot of wobble. It will be a temporary solution until I come up with something better.

[![](http://www.hackniac.com/blog/wp-content/uploads/2012/01/demomite_guts_lores.jpg)](http://www.hackniac.com/blog/wp-content/uploads/2012/01/demomite_guts_lores.jpg)

The Demomite is one of my favorites out of the things I've ever built. It was extremely satisfying to make and hopefully will serve its purpose of showing what I can do well. I will use it like a boxer training with weights, when I step out of its restrictive walls the punches I throw will be all the more powerful.


Schematic
---------

[![](http://www.hackniac.com/blog/wp-content/uploads/2012/01/schematic-300x221.jpg)](http://www.hackniac.com/blog/wp-content/uploads/2012/01/schematic.jpg)


Software
--------

[Tiny Miasmata](http://www.hackniac.com/blog/2012/02/01/tiny-miasmata/)
