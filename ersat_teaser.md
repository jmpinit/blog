---
date: 2012-01-07 17:24:58
title: Ersat Teaser
---

I take on an especially challenging project every year, with the goal of testing the limits of my existing knowledge and pushing it further. This is my big project for this year. I have set it up as an official independent study with my high school, so I will be giving a presentation on it to a group of students and teachers in the Spring and will receive credit towards graduation for it. I haven't divulged much about it here on my blog up to this point except for small references to it in posts about proofs of concepts I've made for it (see [IR receiver project](http://www.hackniac.com/posts/a-tiny-tv-remote-receiver.html)). Now that I have finished applying to college I have a window of opportunity to sink a lot of effort into it, so I have decided that it is time to spill the beans on the project. What follows is the project proposal that I submitted to my school to allow it to count as an independent study, and a sampling of the sketches that I've done to flesh out the project over the last few months.

<!--more-->

Background
----------

I have been carrying around the concept of an “ersat” in my head for a few months. I dreamed it up after I did some very interesting research on the Strategic Defense Initiative, which was set up in the United States during the Cold War. The program was often called “Star Wars”, because its aim was to create a space-based defense system to protect the U.S. from Soviet nuclear attack. Although the entire program was filled to the brim with amazing engineering projects, the ones that most captivated me were the satellite-based systems for missile defense. Their plans called for everything from x-ray lasers powered by nuclear bombs to suicidal falling robots. It all sounded like science fiction, and it was. They did not have the technology to get any of it into space.


Idea
----

I too have no means to get my creations into space, but I still want a chance to work under design constraints similar to those of a machine built to reside in orbit. This is where ersats come in. The word "ersatz" means artificial, fake, or imitation. An ersat is a wannabe satellite. It hangs from a ceiling or sits on a table rather than orbit in space. However, it operates within the confines of many of the same engineering restraints that real satellites are subject to.

An ersat does not have a power cord or finite batteries. It must operate indefinitely by drawing power from its surroundings. Like a satellite in space any given ersat also has a specific purpose; recording measurements of its environment, for example. It must also be able to communicate, whether that be to some kind of "ground station" (a personal computer or other foreign device) or to another ersat. Key to all of this is the ability for the fake satellite to manage its resources. Power is not plentiful, and anything that it could be made to do requires power, so an ersat must include an advanced power management system to stay 'alive'.

If you are having difficulty picturing an ersat, then imagine a rough ball of electronics about the size of a grapefruit. Possibly it has shiny rectangular solar panels to collect power, which would make it would look convincingly like a miniature satellite model. It hangs on its wire or sits on a desk quietly. Maybe it has some obvious external means of expressing that it is still alive and doing its job, like a tiny light that turns on and off or a small screen that scrolls a message, but otherwise it just sits there doing its thing. When I imagine the possibilities that ersats represent I see them hanging in trees or placed haphazardly around a city. Small terrestrial satellites operating completely on their own fulfilling some simple but interesting purpose. An ersat is much more art than practical system, but the applications of the technologies that go into its creation are very straightforward and relevant.


Areas of Study
--------------

An ersat is defined by conditions that represent a significant engineering challenge, and in fact its challenge is representative of what engineers who deal with embedded systems (portable electronic systems being the most directly applicable example) have to solve constantly in the course of their work. Specifically, the areas that an ersat addresses are:

1. _Power gathering and management_ - The ability to find and use any sources of power available, and use them in the most efficient way possible. Important to everything from electric cars to iPods.
2. _Networking_ - Communication without wires is not trivial. The problems encountered by an ersat trying to phone home are the same fundamental problems that must be solved to allow wireless communications for any device, from a cell phone to a laptop.
3. _Distributed computation_ - An ersat on its own may not be powerful enough to solve a given problem in the given time. Distributing the computation allows the combined computational power of an entire network to bear down on a problem as one system. Currently an extremely hot topic because of the growth in demand for supercomputing systems for simulation work in many different industries.
4. _Design resiliency_ - There is no easy way to repair a real satellite in space, so it needs to be engineered well enough that as many eventualities as possible are accounted for. Similarly, an ersat must operate on its own without intervention or help. Doing this well represents an ability to engineer a system for long-term strength and stability, which is highly prized in the engineering world.


Prototypes
----------

Engineers do not tackle constructing their final product right from the start. Instead, they build a series of simpler constructions to prove the various systems that underlie the main project will work before putting them together into one coherent structure. These are the major prototypes that I think I will need to build before creating the final project:

* Wireless communications
* Trickle charging - store up energy from a weak source, like a solar panel, to do more than what could be done by continuously using the weak source
* Power measuring - How much is left? How much has been used?
* Power management system - How can we schedule power-hungry tasks so that they get done by the time they need to be done but not suck the power system dry?
* Distributed computing - How can tasks be shared most efficiently? Extremely broad area. The scope of this prototype will be narrowed as the other ones are finished.
* Remote repair - Enable the software systems to be reset and recalibrated from the 'ground' (an external device some distance away).
* Combined prototype - Put together the progress from the preceding prototype systems into one system: the first full ersat.

They are subject to change as I work through the project, and more might be added to the list. All will be as thoroughly documented as the final resulting creation.
