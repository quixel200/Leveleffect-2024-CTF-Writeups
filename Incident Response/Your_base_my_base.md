#  Your Base, My Base

This is for the Zig.exe binary!

I took your keys to this domain.

Intermediate 
250 points 


So we know that the keylogger is rundlll32.exe, and we know that the file it writes to is base.out. read more [here for keylogger](One_of_these_process_names.md) and [here for file](Keylogger_out_1.md) 
Now on movezig.ps1, we see that the script connects to a url with a put request, so its safe to assume that this is the domain we are looking for.
![the movezig.ps1 code](/Images/movezig_keylog.png)

`flag: leveleffect{http://leveleffectgotallyourbase.com:1337/base.out}`



