# Keylogger Out #1 



This is for the Zig.exe binary!

What was the file name for the first key logger output?

Intermediate 
200 points 

The keylogger can be found by looking at the disassemly in ida.
You can also find it by looking at the movezig.ps1.
or you can wait for movezig.ps1 to execute and look at it in procmon.

Personally I like to go through the disassembly of a binary before running it.

During the systemchecks, the main function calls 'createUploadScheduleTask' and within that function we see a string `$filePath = "C:\Windows\base.out` . The rest of the function writes to movezig and adds movezig.ps1 to the Run key
![keylogger file](/Images/ida_keylog.png)


looking at the contents of movezig.ps1, we see the exact same string.
![movezig.ps1 file](/Images/movezig_keylog.png)

Basically, the movezig connects to a url, calls a 'put' method which im assuming is uploading the file, and the file that gets uploaded is 'base.out'
so the first keylogger is 'base.out'

`flag: leveleffect{base.out}`
