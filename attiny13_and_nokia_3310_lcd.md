---
date: 2011-06-23 19:06:38
title: Attiny13 and Nokia 3310 LCD
---

(I wrote the beginning of this article in the middle of the school year and just finished it today. If you want to see where this project led me, check out [this post](http://www.hackniac.com/blog/2012/02/01/tiny-miasmata/))

![](http://www.hackniac.com/blog/wp-content/uploads/2011/06/proto_char-e1308855217781.jpg)

One day I wanted to do an exercise in seeing how far I could go with scraps that I had lying around. I dug through my parts bin and found a couple of Nokia 3310 LCD displays that I bought a long time ago because they were cheap and looked fairly easy to use. I also found about a dozen Attiny13 micros that I had bought for basically the same reasons. Knowing I need 5 I/O lines to drive the displays and the Attiny13 has exactly 5 regular I/O lines (excluding the use of the reset pin), they seemed like a good match. I decided to combine them and make a fun little widget for my desk, or maybe a keychain if I ever get the chance to use SMD parts and mill a PCB for it.

<!--more-->

Concept
-------

[![](http://www.hackniac.com/blog/wp-content/uploads/2011/01/concept.png)](http://www.hackniac.com/blog/wp-content/uploads/2011/01/concept.png)

The idea is to have a little gadget, not much larger than the Nokia LCD that I'm using, that displays little graphics in sequence. The memory on the Attiny13 is very small at 2K, so only one full screen image can be fit in program memory without some kind of compression (84x48 at 1 bit per pixel). This is especially limiting because all of the I/O lines will be used to drive the screen with none left over to communicate with an external memory chip (without some more complicated circuitry or coding). To get around this I am making the graphics procedurally-generated. Ideas I have for some graphics include a tetris simulation, a self-playing side-scroller, 3d cubes, and maybe grayscale patterns (if I can drive the display that quickly). I'm sure as I have time to play around with it I'll think of others.

Update April 23:

I dug out the old code that I wrote for the project and remade the breadboard circuit that I created earlier this year when  I wrote the beginning of this post. After cleaning up the code a little bit I took a bunch of pictures of the demos that I had created then.


Image Display Demo
------------------

This was the original goal of the project. I completed it without much trouble. The demo is written in AVR assembly code. It was actually harder to write the program in Processing that converts an image to 1 bit in a format that the code can display than it was to actually write the code needed to display them.

[![](http://www.hackniac.com/blog/wp-content/uploads/2011/06/proto_image1-e1308854783705-1024x714.jpg)](http://www.hackniac.com/blog/wp-content/uploads/2011/06/proto_image1-e1308854783705.jpg)

The image it is displaying is the boot screen of the Nokia 3310. I found it on the net and ran it through my converter program and then flashed it to the chip. I also converted a bunch of other images like batman and a Volkswagen and the radiation symbol but this one was by far my favorite. Just look at that dithering!


Character Library Demo
----------------------

Since images turned out to be not much of a challenge I wrote a little character-display library for the Attiny13, also in AVR assembly. I made a font for it by hand (based on the TI-83 plus system font because my calculator was in reach when I realized I needed a font). The font is stored in PROGMEM (not really going to be able to fit an ASCII character set in 64 bytes of RAM heheh). The put_char function takes an ASCII code input and draws it to the screen while taking into consideration line-wrapping.

[![](http://www.hackniac.com/blog/wp-content/uploads/2011/06/proto_char-e1308855217781.jpg)](http://www.hackniac.com/blog/wp-content/uploads/2011/06/proto_char.jpg)


Tilemap Library Demo
--------------------

I was still hungry after the success with displaying images and characters, so I wrote tilemap code too. The tilemap is currently stored in PROGMEM, which is kind of silly because I'm sure you would want to have it in RAM to do anything useful for it (like space invaders as I originally intended), but hey, that's what you get on a school-night with an icky A.P. history test to study for the next day. With a little bit of modification the tilemap could be stored in RAM. There is _juuusstt _enough RAM to let that work, because the tilemap can be up to 10x6 tiles in size with 8x8 tiles, meaning you'll have just 4 bytes of RAM left after storing the 60 byte tilemap. The library could be rewritten to use maybe 2 bits per tile in the tilemap (allowing 4 different tiles) but that would require packing and unpacking code and blah blah. Maybe when I need another challenge...

[![](http://www.hackniac.com/blog/wp-content/uploads/2011/06/proto_tilemap1-e1308855931545.jpg)](http://www.hackniac.com/blog/wp-content/uploads/2011/06/proto_tilemap1.jpg)
