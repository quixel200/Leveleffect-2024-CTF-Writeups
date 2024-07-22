#  Catch the bandit 

Can you catch the bandit and recover the flag?

Intermediate 
250 points 


I will be using process monitor from the sysinternal suite to monitor the proccess and see what its doing while its running.
lets set a filter for the bandit.exe process and run it.

We see that it creates a file flag.txt in C:\Users\quixel\Appdata\Roaming and deletes it over and over again.
![procmon log](/Images/bandit.png)

lets try to open the file before it gets deleted.
I cannot catch it.

So I decided to use a debugger and try to set a breakpoint right after it writes to the file.
I used x32dbg and it took a bit of trial and error but I was able to get the flag.

`flag: leveleffect{b4nd17_c4ugh7}`


