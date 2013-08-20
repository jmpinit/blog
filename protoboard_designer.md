---
wip: true
---
A webapp for designing protoboard hardware projects.

Features
--------

* Easily switch between front and back of board
* Solder bridges or jumpers for connections
* Guesstimate wire length in units of protoboard holes
* Source parts from an existing library (EaglePCB?)
* Very easily add custom parts (built-in editor)
* Keyboard shortcuts / sleek design for fast editing
* Simple scheme for verifying connections

Verifying Connections
---------------------

A simple text-based language for defining device connections. Easily implemented as a JS subset run using eval().

Connect one to many:
	Device1.connectionA = Device2.connectionA 
	Device1.connectionA = Device2.connectionB
	
* Code lines are highlighted as the corresponding connections are placed in the design
* Connections not written out in the code are allowed, but highlighted as a warning

Tech
----

* [Raphael](http://raphaeljs.com/) for rendering graphics
* [Bootstrap](http://getbootstrap.com/) for UI
* [Persist JS](http://pablotron.org/?cid=1557)([github](https://github.com/jeremydurham/persist-js)) for saving designs
