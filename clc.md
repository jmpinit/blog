---
wip: true
desc: cli graphing calculator
---

[CLC ON GITHUB](https://github.com/jmptable/clc)

What
====

See what math looks like; super quick - on the command line.

    ./bin/clc 0 6.28 0 2 "1+math.sin(x)"

                         ▄▄▄▄▄▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▀▚▄▄▄▄▖              

                 ▗▄▄▄▀▀▀▀                                 ▝▀▀▀▚▄▄▄       

           ▄▄▄▀▀▀▘                                                ▀▀▀▚▄▄▖

     ▗▄▄▀▀▀                                                             ▝▀▀▚▄▄
    ▀▀▀▄▄▄                                                             ▗▄▄▞▀▀▘                                                                   
          ▀▀▀▄▄▄▖                                                ▄▄▄▞▀▀▘                                                                         
                ▝▀▀▀▄▄▄▄                                 ▗▄▄▄▞▀▀▀                                                                                
                        ▀▀▀▀▀▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▄▞▀▀▀▀▘                                                                                      

Code Snippets
=============
(mostly for moi)

Working snippets
----------------

	system("echo █");
	system("echo \u2580");
	printf("test: \u2580\n");
	printf("test: %c%c%c\n", -30, -106, -128);
	
Finding the bytes
-----------------

	const char* input = "test=\u2581";
	char* c;
	while((c = *input++)) {
		printf("%c=%d\n", c, c);
	}
	
Printing all block elements
---------------------------

	// all
	for(int i=-128; i < -128 + 0x259F - 0x2580; i++)
		printf("test: %c%c%c\n", -30, -106, i);

	// just 4 point blocks
	for(int32_t i=0xE29696; i < 0xE29696 + 8; i++) {
		int32_t b1 = (i>>16) | 0xFFFFFF00;
		int32_t b2 = (i>>8) | 0xFFFFFF00;
		int32_t b3 = i | 0xFFFFFF00;

		printf("%c%c%c", b1, b2, b3);
	}
	
Printing all braile elements
----------------------------

	// 6 point
	for(int32_t i=0xE2A080; i < 0xE2A080 + 64; i++) {
		int32_t b1 = (i>>16) | 0xFFFFFF00;
		int32_t b2 = (i>>8) | 0xFFFFFF00;
		int32_t b3 = i | 0xFFFFFF00;

		printf("%c%c%c", b1, b2, b3);
	}

	// 8 point
	for(int32_t i=0xE2A180; i < 0xE2A180 + 64; i++) {
		int32_t b1 = (i>>16) | 0xFFFFFF00;
		int32_t b2 = (i>>8) | 0xFFFFFF00;
		int32_t b3 = i | 0xFFFFFF00;

		printf("test: %c%c%c\n", b1, b2, b3);
		printf("test: %X, %X, %X\n", b1, b2, b3);
	}

Random Notes
============

Used wchar but failed
---------------------

	#include <wchar.h>
	#include <wctype.h>

