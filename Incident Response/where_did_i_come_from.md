# Where Did I Come From? 

This is for the Zig.exe binary!

I must have come from somewhere originally. (provide the full URL please) ("I" is not Zig.exe but rather what it calls)

Advanced 
300 points 

I found the answer while looking at the disassembly in ida, I also realised that this is the reason that the message 'possible error...' appears when running the binary locally. So it turns out zig does not do much other than setting up the system to run rundlll32.exe which performs the main exfiltration.

![the disassembly](/Images/where_did_I_come_from_dis.png)

heres the full url:
`https://cda-lab-data.s3.amazonaws.com/FAQingFriday/rundlll32.exe`

`flag: leveleffect{https://cda-lab-data.s3.amazonaws.com/FAQingFriday/rundlll32.exe}`


