# SCH Part 9 - Parasite 

I swear I'm not the one doing that, I'm legitimate! It's this thing, it's attached to me and I can't shake it!

What is my name?

Advanced 
350 points 

In the process tree of procmon, we saw that the olgreg.exe was actually spawned by explorer.exe, so the parent process is explorer.exe and olgreg is attached to it.
Or at least that was my thought process when solving the challenge.

![the process tree](/Images/olgreg.png)

However, there is a dll injection on the explorer.exe file as we'll see in [SCH part 10](SCH_part_10.md).

`flag: leveleffect{explorer.exe}`


