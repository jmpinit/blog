---
date: 2013-07-19 22:33:33
wip: true
---
<style>
img {
	margin: 0px;
	border: 2px solid #021a40;
}
</style>

<!--
TODO
* sort the programs by coolness
* split groups of programs onto separate pages
-->

Calculator Childhood
====================

_"2nd, +, 7, 1, 2"_ will always be ingrained in my memory.

Archival process
----------------

1. Extract programs from group files into folders
2. General notes on each program
3. Images/gifs of program operation
4. Explanation of how they work
5. Annotated source code using [sourcecoder](http://www.cemetech.net/projects/basicelite/sourcecoder2.php)
6. Modify to fix bugs

The programs
------------

Programs are divided into groups according to the TIG files (group archives) that they were saved in. I tended to develop some programs along a theme and then archive them into a group and start off on a new theme.

italisized = boring math program

Group ALL
---------

#### ALIAS

Draws pixels in a line given a direction.

#### CAST

Draws the output of RAYCAST by placing 2 pixels mirrored vertically, one for each column.

![CAST](../images/calculator_childhood/CAST.gif)

#### CIRCLE

Draws lines out from the center over 360 deg.

![CIRCLE](../images/calculator_childhood/CIRCLE.gif)

#### DATABOMB

Asm program of unknown purpose.

#### FLASH

Flips between pic0 and pic1 for animation.

#### MAPPER

Editor for game map stored in matrix A. Places X's for walls and pi symbols for the player starting position.

![MAPPER](../images/calculator_childhood/MAPPER.gif)

#### PRINTLNK

Asm program

#### RAYCAST

Does 2 dimensional raycasting. Bug: renders only one quadrant.
#### _YIELD_

Group ALL2
----------

#### EXNAVNET

Nonworking program aimed at exploring/hacking the TI Navigator network in my calculus class.

#### GENPOP

Randomly initializes genomes for a new population of JUMPER creatures. Stores 99 genomes consisting of 8 numbers each into matrix A.

#### GENTERR

Generates a random terrain for usage by the JUMPER.

![GENTERR](../images/calculator_childhood/GENTERR.gif)

#### GONAVNET

Nonworking program aimed at exploring/hacking the TI Navigator network in my calculus class.

#### JUMPER

Genetic algorithm aimed at optimizing creatures who try to jump as far as possible across a randomly generated terrain in the shortest number of moves possible. Each jumper has energy that is depleted at differing rates by different actions. The jumper dies when it runs out of energy.

__Fixes__

* Score for a jumper was originally the number of actions it could take before running out of energy. Changed the score to be the x distance covered, to encourage jumpers crossing the terrain.
* No bound check on the x position, so the program would crash if a jumper made it all the way across the landscape.
* Score bonus if the end of the terrain is reached.

#### MUTATE

Operates on the genomes of the best performing JUMPER creatures, mutating them to generate the next population.

Group ALL3
----------

#### APPEND

__pseudo code__

	for each number in L1
		switch number
			case 1: append '+' to Str3
			case 2: append '-' to Str3
			case 3: append '*' to Str3
			case 4: append '/' to Str3

#### APPEND2

TODO - what does it do?

Used by SHUNT.

__pseudo code__

	for each number in L1
		run POP
		switch number
			case 1: append '+' to Str3
			case 2: append '-' to Str3
			case 3: append '*' to Str3
			case 4: append '/' to Str3

#### CALC

Executes calculation instructions stored in L1 and displays the result.

#### CONVERT

Takes a human-readable calculation stored in Str3 and turns it into an instruction stream in L1 for CALC to execute.

#### _DIST_

Calculates a distance between 2 (x, y) points.

#### POP

__pseudo code__

	function pop
		B = L1[stack_pointer]
		stack_pointer--
		return

#### PREPEND

TODO - what does it do?

Used by SHUNT2.

#### PUSH

__pseudo code__

	function push
		stack_pointer++
		L1[stack_pointer] = B
		return

#### SHUNT

Implementation of the Shunting Yard Algorithm. Takes an equation as input and outputs the equation in Reverse Polish Notation.

![SHUNT](../images/calculator_childhood/SHUNT.gif)

#### SHUNT2

TODO - how is it different than SHUNT?

Implementation of the Shunting Yard Algorithm. Takes an equation as input and outputs the equation in Reverse Polish Notation.

#### SOLVE

TODO - what's the purpose?

Unknown purpose. Follows instructions in L1 of length 4 and zeros or ones in matrix A (dimension 5x5).

Group ALL5
----------

#### ANIM

Animation program. Draw a frame pixel-by-pixel, and then save it to one of the pic variables. Repeat for up to 10 frames. REPLAY played the animation.

#### CITY

Draw a procedurally-generated cityscape.

![CITY](../images/calculator_childhood/CITY.gif)

#### EARTH

Simulates the pull of gravity on a little satellite. Has proper Newtonian gravity. Made while in physics class.

![EARTH](../images/calculator_childhood/EARTH.gif)

__controls__

* arrow keys - fire thrusters in the 4 cardinal directions

#### EXPLODE

Removed a circle on the graph.

#### FLUID

Simulation of a liquid. A cellular automata. Each pixel on the graph screen was considered a particle of liquid. The program would iterate over the graph, updating each pixel, and save to a pic variable at the completion of each pass. The resulting animation could be played back using REPLAY. Making it generate an animation was necessary because TIBASIC executed far too slowly for it to be interesting to watch in real-time.

![FLUID](../images/calculator_childhood/FLUID.gif)
![FLUID output](../images/calculator_childhood/FLUID_out.gif)

#### INVADERS

Filled the screen with randomly generated space invaders. Each 8x8 sprite had one half randomly filled, and the other half was made a mirror of the first.

![INVADERS](../images/calculator_childhood/INVADERS.gif)

#### MAZE

Generated a maze using a simple binary randomized algorithm.

![MAZE](../images/calculator_childhood/MAZE.gif)

__pseudo code__
TODO

#### RAND

Generated a tub of randomly placed particles on the graph to be run through either LIQUID or SAND.

#### REPLAY

By drawing each pic variable in series (a quick operation done by the OS) and clearing in-between an animation could be played back.

#### SAND

Simulation of falling sand. A cellular automata. Each pixel on the graph screen was considered a particle of sand. The program would iterate over the top couple of rows, updating each pixel, and save to a pic variable at the completion of each pass. The resulting animation could be played back using REPLAY. Making it generate an animation was necessary because TIBASIC executed far too slowly for it to be interesting to watch in real-time.

![SAND](../images/calculator_childhood/SAND.gif)

![SAND output](../images/calculator_childhood/SAND_out.gif)

Group ALL6
----------

#### BCUBE

Draw matrix B at a particular location.

#### ISODRW

Given a heightmap in matrix A this program would render it on the screen in a 3D isometric perspective, made of boxes. Used BCUBE, NCUBE, and TCUBE for drawing different cube parts.

![ISODRW](../images/calculator_childhood/ISODRW.gif)

__pseudo code__
TODO

#### MKCUBE

Utility for loading cube graphics into matrix variables for use with ISODRW.

#### NCUBE

Draw matrix D at a particular location.

#### SFT

Assembled version of SHIFT.

#### SHIFT

Assembly program that shifts everything on the graph screen

#### SOUND

Make-believe music visualizer.

![SOUND](../images/calculator_childhood/SOUND.gif)

#### STORE

Saves a 9x9 square at the upper left corner of the graph to matrix A.

#### TCUBE

Draw matrix C at a particular location.

Group ALL7
----------

#### DRW

Copies graph buffer to the LCD.

#### SFT2

Shifts the entire graph buffer 1 px to the left.

#### SOUND v2

Make-believe music visualizer. Improved by continuously generating a waveform, rather than just one screenful.

![SOUND v2](../images/calculator_childhood/SOUNDv2.gif)

Group ALL8
----------

#### PIXED

Very simple platformer where you play as a single pixel.

![PIXED](../images/calculator_childhood/PIXED.gif)

#### ALL9

#### BMAZER

![BMAZER](../images/calculator_childhood/BMAZER.gif)

TODO - AXE PROGRAMS

A
-

#### ANIM

#### ASCII

#### BINTODEC

#### CIRCFILL

#### COOR

#### DRWTET

#### ENCODE

#### EXIT

#### INVADERS

#### KEY

#### NUMALPHA

#### PICHAN

#### PICSAVE

#### PIXIO

#### PRAND

#### RAND

#### REPLAY

#### SAND

#### SNAKB

#### TEST

#### TMAZE

B
-

#### RACER

![RACER](../images/calculator_childhood/RACER.gif)

C
-

#### ALLASCII

![ALLASCII](../images/calculator_childhood/ALLASCII.gif)

Uses [ENPRO](http://www.ticalc.org/archives/files/fileinfo/426/42648.html) to print every character available in the calculator.

#### BATTERY

Uses [ENPRO](http://www.ticalc.org/archives/files/fileinfo/426/42648.html) to get the charge of the calculator's batteries, and then displays it graphically.

![BATTERY](../images/calculator_childhood/BATTERY.gif)

E
-

#### CONTRAST

Uses [ENPRO](http://www.ticalc.org/archives/files/fileinfo/426/42648.html) to screw up the calculator's contrast setting. 

![CONTRAST](../images/calculator_childhood/CONTRAST.gif)

#### FASTROAM

The start of some sort of game. Uses [ENPRO](http://www.ticalc.org/archives/files/fileinfo/426/42648.html).

![FASTROAM](../images/calculator_childhood/FASTROAM.gif)

#### GRID

Utility that makes a grid of 8x8 pixel cells for drawing sprites.

![GRID](../images/calculator_childhood/GRID.gif)

#### VOMIT

Vomit rain.

![VOMIT](../images/calculator_childhood/VOMIT.gif)

BASCLASH
--------

A game where players use TIBASIC programs to control robots that try to navigate a maze and destroy each other.

![BASCLASH](../images/calculator_childhood/BASCLASH.gif)

BOMIO
-----

Platformer game. Play as a T trying to kill the A with bombs. Features tombstones on death, destructable maps, and an unpredictable enemy AI. Map saved in pic0 in a row of 16x8 chunks. Map drawn as characters at start of game using OUTPUT(ROW, COL, CHAR).

![BOMIO map](../images/calculator_childhood/BOMIO_in.gif)
![BOMIO](../images/calculator_childhood/BOMIO.gif)
![BOMIO death](../images/calculator_childhood/BOMIO_died.gif)

__Controls__

* left/right arrow keys - movement
* 2nd - jump
* mode - lay bomb

EVO
---

GENERATE
--------

GPUTE
-----

GRAVITY
-------

HEXUTIL
-------

IVDEMOS
-------

SOLVER
------

Some sort of maze solver.

TODO: look at source

VERIFY
------

Symbolic equation solver?

TODO: look at source

CONTROL
-------

Robot club robot controller.

TOUCH
-----

TI calculator touch screen.

Tools to make this
------------------

* TilEm
* TiLP
* Cemetek's [Sourcecoder](http://www.cemetech.net/projects/
* basicelite/sourcecoder2.php)
