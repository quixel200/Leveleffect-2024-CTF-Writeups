# I Could Have Called for Help 

This is for the Zig.exe binary!

What secret set of keys could have been initiated for help?

I already looked through the zig binary and I was certain that there was no call for help thing in there. 
So I looked at the file it downloads and runs: rundlll32.exe

looking throught the ghidra decompiled output, I saw this:

![call for help](/Images/call_for_help.png)

unforunately I don't know the exact location of where I found this since I ran out of time on the VM(or maybe im just too lazy wink wink), but you should be able to find it with some time or just run strings on the binary.
surely this is the one its talking about, thats not something that you see in a binary everyday.

`flag: leveleffect{helpmeobiwan}`
