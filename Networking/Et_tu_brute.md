# Et tu, Brute?


Suspicious traffic has been seen on our company web server. Can you figure out the type of attack and find the flag?

The flag in this one is not in the usual leveleffect{FLAG} format. You'll know it when you find it. When you do, submit it in the format leveleffect{INSERT_FLAG_HERE}

Beginner 
150 points

Looking at the packet capture in wireshark, we see a lot of post requests to the /login page. This is a bruteforce attack, lets look for a login attempt thats successful.
we found it! There might be a easier way to filter the packets but I just went throught them manually.
the password seems to be flag.

![flag](/Images/et_tu_brute.png)

`flag: leveleffect{y0u-kn0w-h77p-r3qu3575}`
