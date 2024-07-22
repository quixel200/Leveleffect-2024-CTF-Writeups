# Autoruns 3

Attackers compromised this Windows host and riddled it with persistence mechanisms in a see-what-sticks effort to maintain a foothold on the system. Can you find the third persistence mechanism?

Intermediate 
200 points 

One of the places to check for persistence is the task scheduler, We see a task named 'Disk Cleanup' that looks pretty suspicious to me, as far as I know no such task exists in windows and it certainly will not run at 11:11am even if it did exist. We see that it runs a powershell command with a base64 encoded string. lets decode it.


`/c start /min "" powershell.exe -Command IEX([System.Text.Encoding]::ASCII.GetString([System.Convert]::FromBase64String((Get-ItemProperty -Path HKCU:\\SOFTWARE\\DiskCleaner).bGV2ZWxlZmZlY3R7aXRzX2JlY29taW5nX3NlbGZfYXdhcmV9)))`

decoding this gives us our flag.

`flag: leveleffect{its_becoming_self_aware}`


