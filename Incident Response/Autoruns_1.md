# Autoruns 1 

Attackers compromised this Windows host and riddled it with persistence mechanisms in a see-what-sticks effort to maintain a foothold on the system. Can you find the first persistence mechanism?

intermediate 
200 points 

A great place to start when looking for persistence mechanisms is the start menu programs. these programs are automatically run when you turn on the pc. I will be using autoruns which is a program that comes with sysinternalsuite and helps identify persistence mechanisms.

We have a run key set to run 'cscript.exe'. huh...looks suspicious.
![cscript.exe](Images/cscript.png)

we can see that it runs a vbs file located at Appdata\local\temp\init.vbs


init.vbs has this code in it:
```
CreateObject("Shell.Application").ShellExecute "config.bat", "> " & CreateObject("WScript.Shell").ExpandEnvironmentStrings("%LOCALAPPDATA%") & "\Temp\out.txt", CreateObject("WScript.Shell").ExpandEnvironmentStrings("%LOCALAPPDATA%") & "\Temp", "open", 0
```
It seems to execute config.bat and writes the output to \temp\out.txt scrolling through the contents of out.txt, I found the first flag.

![the flag](/Images/autorun_1.png)


`flag: leveleffect{first_one_down}`


