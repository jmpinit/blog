---
date: 2013-03-01 17:21
desc: little tool for vector field visualization
---

![y/x]({{site.url}}/images/posts/vfield/vfield-ripples.png)

Quick tool for diff. calc HW
----------------------------
I made this little tool using Processing and the new Java scripting library. It draws slope field for a given differential equation as a field of vectors.

JS in Java?!
------------
This is the meat of the code:

~~~ java
//give the script the current grid location
engine.put("x", ZOOM*((float)x/width-0.5));
engine.put("y", ZOOM*(-((float)y/height-0.5)));

//get the slope at this pt according to the script
float slope = ((Double)engine.eval(in.equation)).floatValue();
float angle = atan(slope);

//draw the slope here
stroke(255, 0, 0);
line(x-LEN*cos(angle), y+LEN*sin(angle), x+LEN*cos(angle), y-LEN*sin(angle));
~~~

It is inside of a double loop over every point in the entire field. Each point gets fed into the engine using the variables "x" and "y". The script/equation supplied by the user is then executed and the result is interpretted as the slope of the solution curve at that location. Then a little bit of trig is used to draw that on the screen.

It's extremely inefficient, but took ten minutes to write and gives me what I am interested in. Here are some results for various interesting differential equations:

![y/x]({{site.url}}/images/posts/vfield/vfield-y_div_x.png)
![lungs]({{site.url}}/images/posts/vfield/vfield-lungs.png)

Source
------
[Here: vfield.pde]({{site.url}}/uploads/code/vfield.pde)
