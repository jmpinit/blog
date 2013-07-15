https://gist.github.com/jmptable/5980297

Source Code
===========

silly.c
-------

	#include <stdio.h>

	void silly_run(int num) {
		    printf("the silly number is %d\n", num);
	}

test.c
------

	void silly_run(int);

	int main() {
		silly_run(5);
		return 0;
	}
	
test-rust.rs
------------

	use std::libc::c_int;

	#[link_args = "-lsilly"]
	extern {
		fn silly_run(num: c_int) -> ();
	}

	fn main() {
		unsafe { silly_run(5); }
		println("Ran the unsafe code.");
	}
	
makefile
--------

	all:
		gcc -Wall -fPIC -c *.c
		gcc -shared -Wl,-soname,libsilly.so -o libsilly.so *.o
		export LD_LIBRARY_PATH=./:$LD_LIBRARY_PATH
		gcc -Wall -L./ test.c -lsilly -o test
		rustc -L./ test-rust.rs
