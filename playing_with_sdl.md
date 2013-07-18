---
comments: true
date: 2012-09-27 20:19:25
layout: post
slug: playing-with-sdl
title: Playing with SDL
wordpress_id: 1369
categories:
- Demo
- Exploration
- Software
---

[![](http://www.hackniac.com/blog/wp-content/uploads/2012/09/3dconway-1024x576.png)](http://www.hackniac.com/blog/wp-content/uploads/2012/09/3dconway.png)

I am learning how to use SDL. This afternoon I wrote the code that generated the image above. It is a mirrored wireframe height map. On the surface is a simulation of Conway's Game of Life. A bump indicates life and flatness indicates death.

The renderer is my own. I am not using OpenGL, just [SDL_Draw](http://sdl-draw.sourceforge.net/) to draw the lines. I am writing code for a demo based on this. Its code will show up on [my Github](https://github.com/jmptable) sometime soon.

[![](http://www.hackniac.com/blog/wp-content/uploads/2012/09/3dconway2-1024x576.png)](http://www.hackniac.com/blog/wp-content/uploads/2012/09/3dconway2.png)
