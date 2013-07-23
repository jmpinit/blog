---
date: 2013-07-21 23:01:14 
description: ruby script controls ti-83/84+ calc
wip: true
---

PC connected to Arduino. Arduino connected to TI-83+. The Arduino runs code that knows the TI link protocol, allowing it to send remote control commands to the calculator. A ruby script on the PC takes an input picture and draws it on the calculator with the pen tool. Flood-fill algorithm is used to speed up drawing time by drawing adjacent pixels one after another.

<iframe width="640" height="360" src="//www.youtube.com/embed/nRY8sncwFLM?rel=0" frameborder="0" allowfullscreen></iframe>

[SOURCE ON GITHUB](https://github.com/jmptable/calc_control)

Source Overview
---------------

* calc.rb -> calc constants and utility functions.
* drawimage.rb -> "ruby drawimage.rb <name of pic>"
* paste.rb -> "ruby paste.rb <data>". Attempts to type out the text of the given argument on the calculator.
* sendimage.rb -> sends raw B&W picture data.
* writetext.rb -> writes the text of a webpage on the calculator.
