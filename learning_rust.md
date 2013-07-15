command line arguments
----------------------

	let args : ~[~str] = args();
	println(fmt!("the program name is %s", args[0]));

convert a string to a number (and back)
----------------------------

	let val = from_str("57");
	println(to_str(val.get()));
