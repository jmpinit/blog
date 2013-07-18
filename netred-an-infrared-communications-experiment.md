---
comments: true
date: 2011-02-18 17:26:48
layout: post
slug: netred-an-infrared-communications-experiment
title: Netred - An Infrared Communications Experiment
wordpress_id: 214
categories:
- Concept
- Favorites
tags:
- calc
- communication
- infrared
- ir
- network
---

[![](http://www.hackniac.com/blog/wp-content/uploads/2011/02/kibnet-e1298050576855.jpg)](http://www.hackniac.com/blog/wp-content/uploads/2011/02/kibnet-e1298050576855.jpg)

Two years ago my friend and I were thinking of projects to do. We had an overly-ambitious mentality. We wanted a project that would require solving complex challenges and result in us being rich or making a huge impact in society. One of the ideas that we had was dubbed "KIBNet", an uninspired name derived from the phrase "Kids In Basements", alluding to what we considered to be the natural habitat of hardware hackers.

<!--more-->

KIBNet was rooted in our love of the state of the early internet, especially the bulletin board systems that started to show how useful the World Wide Web could be. We wanted to bring some of that kind of home-grown and hacked-together networking fun back in a form that we could use our hardware and software skills to build.


Target Community
----------------

We knew that BBS's were still around, and we could access them on our own easily without building anything at all, but that wouldn't have been much fun. Instead we decided we were going to create our very own kind of network with our very own custom hardware to try to extract and encapsulate the essence of what we loved about those old systems. We just needed to find a community to use our system when it was finished, and would get the same amount of fun out of it as we would. There are enough people in our high school who are like-minded to create a small community like this, it's just a few people but that's plenty for our rather silly idea.


Exploiting the Environment
--------------------------

We decided to mold our system to the environment of the community that we were targeting it for, namely our high school. This is where we got the idea to make KIBNet into a kind of local message system, a little digital playground for people in the know. Students in high school crave communication, but the use of technology during school hours to scratch that itch for interaction is heavily frowned upon. However, there is a small slice of technology that is perfectly well accepted in school, and extremely widely used. Nearly everyone has a graphing calculator, and they have plenty of power to serve as the basic platform for interacting with our network, so we decided to take advantage of them.


The Structure of the Network
----------------------------

With the graphing calculators as our chosen platform we needed to figure out how the network would be built around them to reach the final state of affairs that we had in mind. The goal would be to have isolated servers in various high-traffic areas around the school, with the calculators serving as terminals to interact with them at these access points. The vision we had was for, as an example, someone to be sitting at lunch in the cafeteria and be able to log into the cafeteria KIBNet server to drop a message on the public chatboard or to play a multiplayer game with other people in the room who were logged in. The structure of the network was crafted to be flexible for use in our school. We needed to be rather sneaky, meaning that the hardware had to be small, robust, and preferably not result in the evacuation of the school and the calling of a bomb squad if it was at some point discovered. For this reason we decided to keep the hardware simple, and make it wireless so that it could be placed out of the way. Having groups of kids with calculators in hand and wires streaming to a hefty box sitting on the floor in a hallway would seem mightily suspicious, and would be disruptive besides. It was an important aspect of the project all along for it to not disrupt the operations of the school, and by extension not bother the teachers or administrators enough to warrant its removal by force.

Texas Instruments graphing calculators, the type recommended by and used in our school, have a link port that allows communication between calculators using a special link cable, but they are in no way wireless devices. One major challenge of the project would be to make them able to communicate without wires. We looked at several different possibilities, all utilizing radio technologies. Making the hardware small enough to be connected to the calculator and carried around without being suspicious was also a difficult challenge. Eventually the time required to solve those two challenges in combination was what prevented us from carrying out the construction of the project. We abandoned it altogether for a lengthy period of time.


New Approach
------------

[![](http://www.hackniac.com/blog/wp-content/uploads/2011/02/calc_concept.bmp)](http://www.hackniac.com/blog/wp-content/uploads/2011/02/calc_concept.bmp)

Recently I started thinking about KIBNet again. I'm still very motivated by the vision of the project that I had at the start (although my friend has moved on to other projects of his own), but now I have experience that tells me the scale of the original project was too large, and some compromises need to be made to make it feasible. I have little time at the moment to actually work on the project and bring it to a conclusion, but returning to solve some of the original design challenges is something that I can do to an extent.

In my new concept for the hardware of the network I believe that I have solved the calculator wireless communication problem with a technology that I am surprised my friend and I did not think of when we tried to solve the problem the first time around. Infrared communication has been a recent interest of mine, and I think that it could be nicely applied for this project. The short-range and line-of-sight transfer of information that it allows is perfect for the local-server aspect of the project. Even though it is highly susceptible to noise, the traffic in the areas around the access points would be so low that I don't believe this would be much of a problem, it could largely be eliminated with some robust software. Also, infrared communication fairly easy to implement, and very easy to implement compared to the radio communications ideas we had originally. It is also possible at power levels low enough to allow the calculator itself to power the hardware entirely, reducing the size substantially. The size should be so small, in fact, that all the hardware can be fit into the recessed opening that contains the calculator's link port, making it very sneaky. The cost is also very low, which could be important if I wanted to manufacture a large number of the devices.

I spent some time the other day thinking about how the hardware would come together, and here are the concept drawings that I came up with from that effort:

[![](http://www.hackniac.com/blog/wp-content/uploads/2011/02/plug_design.jpg)](http://www.hackniac.com/blog/wp-content/uploads/2011/02/plug_design.jpg)

[![](http://www.hackniac.com/blog/wp-content/uploads/2011/02/server_design.bmp)](http://www.hackniac.com/blog/wp-content/uploads/2011/02/server_design.bmp)

Chance of Completion
--------------------

I will continue to think about the project and refine these designs. Hopefully in the future I will have the time to do something with it. It might be a good candidate for a legacy I can leave behind at my school. I would love to leave a couple of the servers in hidden spots around the school and place some instructions somewhere for other kids to get access to it. The opportunity for a homebrew and underground network playground for young hackers is a cool idea that I would love not to let pass.
