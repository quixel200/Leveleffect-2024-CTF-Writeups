# Save zig move zig 

This is for the Zig.exe binary!

I am the name that called the zig mover.

Beginner 
150 points 

Now when running zig, make sure you have process monitor, or procmon open, it allows you to monitor whats happening to the system.
Lets look at the process tree in procmon.

![the commands it runs](/Images/zig_create.png)

now we see 3 entries, the one we're inserted in the one that 'called the zig mover'. I assume its the movezig.ps1 file, and we can see that zig spawns an instance of schtasks.exe and sets a scheduled task named 'ScreenSaver' which calls movezig.ps1.
so the answer is ScreenSaver.

`flag: leveleffect{ScreenSaver}`


