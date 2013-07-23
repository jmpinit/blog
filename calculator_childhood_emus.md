---
wip: true
---
CHIPSIM2
--------

In this project I wrote a virtual machine in TIBASIC that uses the graph screen as memory, storing bytes as rows of pixels. Any change in memory is immediately seen, so the execution of a program could be tracked. A small 3 pixel indicator followed the program pointer.

Here it is calculating the Fibonacci sequence:

![CHIPSIM2: fibonacci](../images/calculator_childhood/CHIPSIM2_fib.gif)

#### EMU

Consumes the instruction stream and executes the corresponding instructions. Also moves the indicator showing the currently executing instruction.

__instructions__

Each instruction is implemented as a separate TIBASIC program. [x] = the value pointed to by x.

* 0 - NOP: P = P+1
* 1 - JMP: P = [P+1]
* 2 - LD: [[P+1]] = [P+2]
* 3 - ADD: [[P+3]] = [[P+1]] + [[P+2]]
* 4 - SUB: [[P+3]] = [[P+1]] - [[P+2]]
* 5 - LSL: [[P+1]] = [[P+1]]<<1
* 6 - LSR: [[P+1]] = [[P+1]]>>1
* 7 - MOV: [P+2] = [[P+1]]
* 8 - DISP: print [[P+1]] on the screen

__test program: fibonacci sequence__

L1 = { 7, 16, 17, 3, 15, 16, 16, 7, 17, 15, 8, 15, 1, 1, 0, 1 }

	loop:
		MOV		C, B
		ADD		B, A
		MOV		A, C
		DISP	A
		JMP		loop
	
	A: .db 0
	B: .db 1
	C: .db 0

#### FLASH

Takes an instruction stream from L1 and writes it to the screen using the WR instruction.

![FLASH](../images/calculator_childhood/FLASH.gif)

#### INDICOFF

Erase the 3 pixel arrow showing where the program counter is.

#### INDICON

Draw the 3 pixel arrow showing where the program counter is.

FOURBIT (STATEMCN)
-------

GRPHPUTE (GPUTE)
----------------
Written in Axe
TODO

EMUASM
------
