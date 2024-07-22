# The Sprawl - 4 

These IOCs were discovered on a compromised endpoint. Figure out the final flag by interacting with the binary.

hint used: You're going to need to use that DLL for this challenge...

Advanced 
350 points 


Now the way I first solved it was by running strings on the dll file which gave me all the flags...
![thesprawl flags](/Images/the_sprawl_strings.png)

The other way to do this is to disassemble the file using dnspy.
we see that if we provide a command line argument of "turing", it will print out the final flag for us.

![final flag](/Images/sprawl_final_flag.png)

`flag: leveleffect{neuromancerdisabled}`
