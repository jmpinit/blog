Text
====

1) write raw blog post in markdown in my dropbox.
2) commit it to the git repo
3) revise as necessary
4) run a rakefile/makefile that:
	1) moves it to my blog's source directory
	2) renames it with the date
	3) adds the YAML header
5) tweak as necessary
6) run deploy script

Images
======

1) create directory for the post/project in images/posts
2) upload the image
3) place the image in its post

_tools_
Generate source code for images in a post with a command like "imggen simulacrum", which finds the images in the directory at hackniac.com/images/posts/simulacrum/ and creates this source:

	{% assign img = 'http://hackniac.com/images/posts/simulacrum' %}

	![front face]({{ img }}/front.jpg)
	![parts]({{ img }}/front.jpg)
	![vm_run]({{ img }}/front.jpg)
	![watch_hello]({{ img }}/front.jpg)
	![watch_side]({{ img }}/front.jpg)

* connect a post to an image directory
