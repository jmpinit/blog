---
comments: true
date: 2011-02-14 02:10:31
layout: post
slug: note-taking-keyboard
title: Note-taking Keyboard
wordpress_id: 198
categories:
- Concept
- Device
tags:
- keyboard
- note
- organizer
- pda
---

For some reason I am most inspired after cleaning up junk piles around my house. Today the inspiration that resulted from my cleaning adventures revolves around a few different ideas that I have been toying with recently. One of them, simple short-range infrared communications, I've only been thinking about for a week or so. The other idea, a keyboard that I can whip out at any time and type descriptions of ideas as I come up with them I have had for a few years. Combining them I came up with this little project for a weekend in the future when I have time to work on something miscellaneous.

[![I know the laptop is crazy. Shh.](http://www.hackniac.com/blog/wp-content/uploads/2011/02/idea0002-1024x700.jpg)](http://www.hackniac.com/blog/wp-content/uploads/2011/02/idea0002.jpg)

<!--more-->

The Concept
-----------

When you think of something interesting that you want to remember later you grab your little keyboard and type it out. Your keyboard is always with you and its long battery life and sturdy construction allows you to treat it almost like you would a pencil, an object that requires no special care or attention to get to work. The things that you write on it are by no means full and filled-out thoughts. It is almost like a personal collection of tweets, I'll call them 'strands' I think, because they are incomplete thoughts that by their nature require further development to be valuable. Your keyboard communicates with a little gadget that plugs into your computer. It does so silently and without any intervention from you, you merely need to bring the two within sight of each other and they exchange information. When this exchange occurs your thought-strands are dumped to the computer and the computer immediately stores and catalogs and organizes them so you can come back and find the best ones later.


Motivation
----------

Motivation for building this project comes from the way that I work with ideas in my head. I am always coming up with little snippets of thought that I think might be valuable, but these fragments often need further development. Without a way of recording these snippets and organizing them so that I can come back and add to them later I am not a productive creator. The current system that I use, which I have been refining for a long time, still has a lot of room for improvement. Usually I simply carry a series of folded papers in my pocket upon which I write down ideas when I come up with them. After a time the wad becomes too thick for my pocket and I dump the oldest papers into an "idea" box under my bed. The problem with this system is that it is very difficult to organize my ideas, and they often get spaced out over several papers if I come back and add to them later. I want something computerized so that I can more easily organize my snippets of thought. The benefit of computerized organization is so great that I would value a gadget upon which I could _rapidly _(key point) record my ideas even if it was only in text.


Parts of Inspiration
--------------------

The parts are the dictator of the design in this case. The main difficult part (at least for my level of knowledge in this area) is the infrared communications hardware. I found a nice demodulator a few days ago online for working with the communications scheme that television remotes use. I am planning on buying some of them to play around with, but in the meantime I need to be a little creative to scratch my infrared communications itch. A pile of old VCRs, DVD players, and stereo systems I found under one of my junk piles should serve as a good source for the hardware that I need for that subsystem. Finding them was what gave my brain the kick it needed to spend the time putting a rough design of this project together.

Another major component that inspired the design is my ancient dell-zombie laptop. Over the years it has been taken apart and put back together so many times that it now is a slab of components without its original screen, keyboard, speakers, or anything else along those lines. It has served me well as an isolated playground for dangerous hacking software hacking projects, but for a while now I've wanted to use it to do something that would require constant processing that is light for a PC but way too much for a lowly MCU. Because it is a laptop the power consumption is quite low so I am fairly comfortable with having it on for most of the day. Using a computer with a full operating system for storing and displaying the notes gives me a lot of flexibility, because I can distribute and process the notes using all of the resources that a PC has to offer, like the internet.

For the actual note-taker device that is to be held in the hand I have a tiny PS2 keyboard that I acquired along with a Parallax Propeller Demo Board about a year ago. It is just about the right size to carry around with me all the time and not be bothered by its weight or dimensions. Right now it is just sitting in one of my junk bins, so I think that I will repurpose it for this project.


User Interface
--------------

My concept for how I will use this device is rather odd I think compared to the usual techniques that other devices use. Most gadgets where a person is able to enter text have a screen so that the person can see what they are typing. I don't want to sacrifice the space, weight, or battery power needed for a screen so I got a little creative with the method for inputting text. A row of LED's and a small piezo-electric microphone are the sole providers of user feedback for the device. When you type there is a distinct pattern for every key displayed on the row of LED's and also a unique sound tied to every key. My hope is that with practice I will connect the sounds and patterns to the keys so that I can forgo the requirement of seeing what I am typing, I will hear it and read it in the patterns. 'Viewing' the text that I have written will simply require the pattern of sounds and lit LED's that correspond to each letter being played back to me for the text. It will likely be annoying at first but I believe the benefit is worth the cost, and it's not like anyone else is going to use this thing so it is O.K. if the interface is rather esoteric.
