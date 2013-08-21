---
wip: true
desc: cmd => sms => shell
---
SMS Shell
=========

Enter shell commands to be trickled out of your phone when possible. Sort of like twitter, except your followers are machines.

On phone:
---------

for each message in the queue
	1) Compress
	2) Encrypt
	3) Send sms
	
Optimizations:
--------------

* show colorful feedback of size of the command out of 140 chars (incremental compression/encrypt?)
* special trickle-fed utilities
* make the machine-generated SMS easier to filter out

Parts
-----

* https://github.com/rapidsms/rapidsms
