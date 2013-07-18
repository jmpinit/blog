---
date: 2012-11-11 13:32:11
title: Current/Recent Projects - (October->November) 2012
post_format:
---

Need more lifetimes to burn.

<!--more-->

Software
--------
	
* [Many Little Pieces](https://github.com/jmptable/many-little-pieces) - A game about programming, where you write code for robots. You have to mine from the world the symbols that you will write your code with. Started over the summer during a 22 hour hackathon ([Codeday](http://codeday.org/) put on by [StudentRND](http://studentrnd.org/)) with a few people I met there. We won "most innovative", but nothing else, at the very least because we didn't have a working game. What we had worked, but we spent  too much time on the backend and not enough time on the front-end that would actually be seen. The other people who worked on it with me didn't stick to the project, so it's all mine now.
* [Mitigator](https://github.com/jmptable/mitigator) - I've been interested in personal efficiency for a long time, and have planned many systems for helping me to manage the work that I do. This is the first system that I've made real progress on, driven by my huge workload here at MIT (I want to mitigate my MIT workload). It's a todo list that can be accessed from the web, mobile app, or directly using a command-line on the server it runs on. I currently use Astrid on Android, Outlook, and Google Calendar to manage things, but this system will replace the todo list portion of those applications. The main benefit is putting control of the data in my hands, and making it possible for me to do deep analysis of my work habits so I can make myself more productive in the future.
* [Badger](https://github.com/jmptable/badger) - On the theme of personal productivity, this is a webapp that's designed to automatically create a work schedule if given some basic information about tasks that need to get done and the time that is available to do them. The web-page does most of the work, but it can communicate back to my room's server for logging, and to trigger physical things in my room for motivation such as the fan art and misc. robotics. It also yells at me using text-to-speech so I know when to change tasks and etc.
* Bool Box - A system for programming microcontrollers. The developer uses a program on a PC to "paint" a Boolean state machine linking outputs to inputs. Simulation is continuous and drawn over the design as it is worked on, so there is immediate feedback. Once the design is finished it is sent to a microcontroller flashed with a VM that simulates the design. The chip will then have the behavior laid out in the design. It's not practical, but I think it will be fun to use.
* Remake of [Miasmata](http://www.hackniac.com/posts/miasmata.html) in C++ using SDL
* Several small SDL learning experiments
* Software 3D renderer (no OpenGL, etc.) based on the math I was learning in class that day. Only supports points and lines. Maybe I will do a voxel thing with it in the future.
* [Full screen Conway's Game of Life](http://www.hackniac.com/blog/wp-content/uploads/2012/11/conway-11-11-12.zip).
* [3D-drawn (but 2D simulated) Conway's Game of Life implementation](http://www.hackniac.com/blog/wp-content/uploads/2012/11/3dconway-11-11-12.zip) using renderer mentioned above. The cells in the cellular automaton are represented as bumps in a mesh.
* [Glitch](http://www.hackniac.com/blog/wp-content/uploads/2012/11/glitch-11-11-12.zip) - Based on the Conway's Game of Life implementation from above. Adds mapping of life intensity (measure of change over area) and procedural of generation of sound from the automaton. Makes a nice ambience that I am pleased with.
* [CLIFuck](http://www.hackniac.com/blog/wp-content/uploads/2012/11/bf_interpreter-11-11-12.zip) - Basic command-line [Brainfuck](http://en.wikipedia.org/wiki/Brainfuck) interpreter.
* [Brainfuckers](http://www.hackniac.com/blog/wp-content/uploads/2012/11/brainfuckers-11-11-12.zip) - I put the brainfuck interpreter from CLIFuck in little bugs that can roam the screen. Eventually I want to implement live-coding and multiplayer. The bugs will fight for resources inside of a mini-environment. Should make a fun little toy.
* Several helpful scripts / webpages utilizing my room's linux server
* ideas.php - Shows small thoughts that I've had throughout the day/week so that I remember them. I log them into the system using a command called idea that is a simple bash script.
* randproj.php - Tells me to work on a random project or homework. Helps when I don't know what to do.
* map.php - Displays a connected graph of my current projects and the different ideas I have about each one. Ideas that are connected have edges (discrete-math-speak for lines) between them in the graph.


Hardware
--------
* Desktop Turing Machine - I'm planning out this little desktop widget. It is a Turing Machine whose tape is tiny ball bearings. The bearings are moved around with electromagnets. It uses a BEAM robotics circuit to store up power from a solar panel in supercapacitors until there is enough to do one computational step (controlled by an MCU). I envision it just as a pretty thing to watch.
* Fan art - I've got a few dozen computer fans that I am mounting on my wall. Their speed will correspond to the rate of my commits to Github, and the rate at which I work through my todo list. I am hoping that it will create a positive feedback loop, making me get more things done by making me aware of the progress I am making.
* Z80 microcomputer from Tranz 330 POS terminal
* Reclaimed server blade
* Tiny wrist-worn display linked over Bluetooth to my phone. It's just an SMD [Attiny84](https://www.sparkfun.com/products/11232), an [RN-42 Bluetooth module](https://www.sparkfun.com/products/10253), [Nokia 3310 LCD](https://www.sparkfun.com/products/10168), a piezo electric element for tap input, and a [tiny polymer lithium ion battery](https://www.sparkfun.com/products/11316). Will display the time like a regular watch, and also notifications from my phone as well as any other information I care to add. Currently in the drawn-all-over-my-arms-in-pen design stage. Need to find some money to buy the parts.
