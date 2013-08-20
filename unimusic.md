---
wip: true
date: Tue Aug 20 13:53:20 EDT 2013
desc: chrome extension for downloading music
---

My monstrous, hacky way of getting music that is available on Youtube and Soundcloud.

Usage
-----
1. Bookmark pages with desireable music in "Music" folder in Chrome.
2. Press the Unimusic extension's button.
3. Copy resulting script into a file in Linux.
4. chmod +x the script.
5. Run the script.
6. Music that can be downloaded is downloaded.
7. Optionally hit button in extension to delete bookmarks to music already downloaded.
8. Enjoy music.

Yes I know that's too many steps. And generating a bash script from JS to be copied to a file (usually by pasting into Vim across an SSH connection to my media server) is a ridiculous Rube-Goldberg-esque process. It's "good-enough" for me, and I'm working on making it more streamlined.

Music Sources
-------------
It's only possible to download from site's that CLI utilities have been written for. These are the ones I've found so far:

* Soundcloud: [soundcloud_curl.sh](https://github.com/lukapusic/soundcloud-dl)
* Youtube: [youtube-dl](http://rg3.github.io/youtube-dl/)

TODO:
* publishable code
* polish
* easy installation
