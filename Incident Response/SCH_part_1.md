# SCH Part 1 - A new challenger arrives 



There is a suspicious user on the host with a password set to never expire. What is the username?

[i] README - The resources needed for this challenge are on the Super Compromised Host (SCH) VM on our hosted platform. Use the VM on the Phase 2 CTF module if you've run out of hours on the original module.


Beginner 
150 points 


We can check all the users on the by running the command `net users`.

immediately I notice 'themightyboosh'.
you can get more info about the user with the command `net users themightyboosh`
we can see that the password is set to never expire.

`flag: leveleffect{themightyboosh}`


