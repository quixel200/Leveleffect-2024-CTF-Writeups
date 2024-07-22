# Whose App Was It Anyway? 

This is for the Zig.exe binary!

I ran the logger after I mislead you from the first console screen.

Intermediate 
200 points

We know that the logger is rundlll32.exe from [here](One_of_these_process_names.md)
We need to find out how the logger gets run.

Looking at the process tree in procmon, We see that zig.exe will run a command that sets the Run key for rundlll32.exe and its name is 'MyApp'.
![the process tree](/Images/zig_create.png)

`flag: leveleffect{MyApp}`


