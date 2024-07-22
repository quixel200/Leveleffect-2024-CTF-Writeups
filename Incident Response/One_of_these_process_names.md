#  One Of These Process Names Is Not Like The Other 

This is for the Zig.exe binary!

I am the logger.

Intermediate 
200 points 

We saw that the movezig.ps1 script uploads the contents of base.out to a remote address, but we still don't know how content gets written to the base.out file. Lets investigate.

While looking through the disassmbly in ida, I saw that a file called 'rundlll32.exe' gets downloaded at the very beginning of the main function
![main funcion ida](Images/rundlll32.exe)

Now if you're running the binary locally, the file will fail to download. So I had to use the provided vm to further investigate.
Now rundlll32.exe was pretty hard to decipher completely, I was running out of time on the VM provided and ida wasn't installed on the system so I just used procmon. 
But heres what I found:

![the keyloggers](/Images/key_logger_outputs.png)
it creates the base.out file, and also another file, which is the second key logger output, thats the flag for a different challenge.

so the key logger is 'rundlll32.exe'

`flag: leveleffect{rundlll32.exe}`


