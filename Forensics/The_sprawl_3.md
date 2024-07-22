# The Sprawl - 3 

These IOCs were discovered on a compromised endpoint. Figure out the third flag by interacting with the binary.

Intermediate 
200 points 

After we know that we are Armitage and that the program is wintermute, the program says
"I'll see you next time you log in, unless you beat me to it first."

Since this is a forensic challenge, I am guessing the flag was hidden somewhere on the system. I quit the binary and then ran it again but this time with procmon.
We see that it creates a file called theWay.bat in the startup folder.

![the procmon capture](/Images/the_way.png)

looking at the file, we get our flag.
Another indicator would be that since its in the startup folder, you would see a browser popup once you login again, which is kinda a giveaway.

![the flag](/Images/sprawl4_flag.png)

`flag: leveleffect{gettingclosertoneuro}`


