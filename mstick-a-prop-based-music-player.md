---
comments: true
date: 2010-09-21 23:01:06
layout: post
slug: mstick-a-prop-based-music-player
title: 'MStick: A Prop-Based Music Player'
wordpress_id: 49
categories:
- Device
- Favorites
tags:
- music
- parallax
- player
- prop
- propeller
- sd card
- wav
---

Initial Design
--------------

My iPod finally bit the dust and I started to think about alternatives. For this project the goal was to create a usable digital music player to replace my dead iPod. To make it more interesting I placed bounds on the construction: build it in a day and with only parts that I have on hand. I hashed out the entire plan for my new music player one day in school.


[![](http://www.hackniac.com/blog/wp-content/uploads/2010/09/project_mstick_plans.jpg)](http://www.hackniac.com/blog/wp-content/uploads/2010/09/project_mstick_plans.jpg)

Everything is kept very simple. A Parallax Propeller microcontroller serves as the brain with support circuitry consisting of power regulation, audio amplification, button input, accelerometer input, and LED output. Songs are loaded off of the SD card that is located on the back and plugged into the board using a ribbon cable. For programming there is a header at the top that can be directly plugged into a PropPlug, Parallax's serial-over-USB programmer for the Propeller MCU. The board is designed to be directly plugged into a 9v battery, forming a "column" that can be more easily fit into a pocket. I never planned on having a case, it would be too difficult to do in one day and I felt that it would hold out pretty well on its own in my pocket because of the simple and robust design of the board.


A Day of Building
-----------------

I wasted the first day of my break playing video games. On the second day of my break I actually got down to the business of my hacking marathon. The to-do list for the day looked something like this:
	
1. Dig every single part needed for the project out of my parts bins and piles of misc. electronics junk.
2. Design the circuit board on graph paper, including all electrical connections and placement of parts.
3. Solder the board together.
4. Test electrical connections.
5. Test functionality of MCU (hello world program).
6. Write a simple firmware for the device to allow music to be played from the SD card.

I quickly finished #1, but with a catch. While perusing the drawers that contain my microcontrollers I found a board that I built a while ago for a hack that I am still trying to carry out on an ancient microprocessor-based word processor. It has a Parallax Propeller in a socket with its pins broken out to headers. It also has a simple power regulation circuit and an EEPROM wired to the Prop.

[![](http://www.hackniac.com/blog/wp-content/uploads/2010/09/project_mstick_base_module.jpg)](http://www.hackniac.com/blog/wp-content/uploads/2010/09/project_mstick_base_module.jpg)

I figured that it would be much faster to just utilize this board for the project, so I modified the design a little bit to better suit the header interface. The new design called for only building a "shield" for the MCU board that would contain everything specific to music playing. That way I could design different shields for different devices that serve different purposes and just swap them when I want to change the purpose. With the system board already done I quickly moved on to building the music-playing shield.

[![](http://www.hackniac.com/blog/wp-content/uploads/2010/09/project_mstick_shield.jpg)](http://www.hackniac.com/blog/wp-content/uploads/2010/09/project_mstick_shield.jpg)

The shield is very very simple. It has an LM386 wired up for low gain amplification and connection to a stereo audio jack. The sound is mono at the moment but the Propeller can output stereo and it is a simple matter of adding another LM386 to make it work. The accelerometer/buttons are conspicuously missing, because I figured that I did not need them to complete my goal for the day, and that they could be added in later. Simply having it play through every song on the SD card as soon as power is switched on seemed adequate for one day's work. The SD card is wired directly to interface pins. I should have used pull-ups on the connections but it seems to be working fine without them. I was limited on time and found that I had no suitable resistors, so I may burn out a couple SD cards and/or a Propeller or two, but at least I finished it in the time I gave myself. The whole thing looks sloppy when all the parts are put together, but it works:

[![](http://www.hackniac.com/blog/wp-content/uploads/2010/09/project_mstick_full_assembled.jpg)](http://www.hackniac.com/blog/wp-content/uploads/2010/09/project_mstick_full_assembled.jpg)

A Night of Programming
----------------------

By the time I had finished building the circuit and working out all the electrical bugs it was getting late in the afternoon. Although my test programs worked well to output simple tones I had no code to read music files off of the SD card and play them over the audio jack. A quick trip over the net to the Parallax OBEX (object exchange) fixed that. I picked up a beautifully-written WAV player object that made it trivial to get music off of the SD card and send it over the audio jack. A main program composed of a few dozen lines of code was all that it took to get the device that I had painstakingly built to play through each song on my SD card. I converted a bunch of my songs from MP3 to WAV, copied them to the SD card, put the SD card in the MStick, and then carefully tucked the whole thing into my backpack so I could utilize it the morning that I returned to school. Incredibly glad to have an alternative to my iPod.


Future Improvements
-------------------

All sorts of things can be done to improve this early version of the MStick music player, especially because it is a rough project by design. Here is a list of the top improvements that I think could be easily made:

1. Add the accelerometer of course. I need a way to control it other than toggling the power.
2. Write a gesture-control object to utilize the accelerometer fully.
3. Etch a PCB so that the overall size is much smaller and it is much more physically resilient.
4. Switch to a surface-mount Propeller, power regulator, and audio amplifier to reduce the size of the player even further.
5. Use a rechargeable battery for power; 9v's get very expensive very fast.
6. Create a docking station for nightly recharging and file syncing.
7. Mill a case for it out of acrylic or some other resilient material. Might be a good excuse to try a custom manufacturing service for the first time, which is something that I have wanted to do for a while.
