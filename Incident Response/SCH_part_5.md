# SCH Part 5 - Pásale 

I spawn 3 different processes. What are they?

The flag will be all three process names in alphabetical order, separated by colon without space, and SHA-256 hashed. Example:

alpha.exe:bravo.exe:charlie.exe -> b9a6deb6189e70a01f92cd62fcb74ace7d2bbfb060205a18b2e936ae3cecd3c5

Intermediate 
250 points 


![the process tree](/Images/olgreg.exe)

So looking at the process tree in procmon, we see that olgreg spawns three processes:
- net.exe
- ipconfig.exe
- systeminfo.exe

arranging them in alphabetical order according to the format:
`ipconfig.exe:net.exe:systeminfo.exe`

lets hash this string.

`flag: 59801deedaf4391aa2bb22564b17e47c32899edcd9b67d51dc4a0f786e2c3cc9 or leveleffect{59801deedaf4391aa2bb22564b17e47c32899edcd9b67d51dc4a0f786e2c3cc9}`
