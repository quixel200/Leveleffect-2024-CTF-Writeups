# SCH Part 4 - Check in 

I am executing enumeration commands every minute. What's my name?

Intermediate 
200 points 

Since its triggered every minute, I checked the task scheduler again but there was nothing in there. So I decided to open procmon and wait for the process to run its commands so that I can see it in the process tree.

![the process](/Images/olgreg.png)

the olgreg.exe seems to be running the net and the ipconfig command every minute.

`flag: leveleffect{olgreg.exe}`


