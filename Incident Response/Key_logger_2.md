# Key Logger #2 

This is for the Zig.exe binary!

I was a bit trickier to find! What was my file name?

Advanced 
350 points 

Once I realised that rundlll32.exe does most of the work, I decided to run it and see what happends using procmon. Obviously the actual process was not that simple, I first analysed zig and realised that it does very little other than downloading rundlll32.exe, and the file only gets downloaded in the VM, I tried to disassemble it in the VM but couldn't find much, running it with procmon finally gave me the answer.

We see that other than the base.out file, it also creates a 'misdirection.out' in 'C:\Program Files\WindowsPowerShell'

![the second key logger](/Images/key_logger_outputs.png)

`flag: leveleffect{misdirection.out}`


