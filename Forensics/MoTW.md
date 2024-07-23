# MoTW 



NOTE - The resources needed for this challenge are on the Cyber Defense CTF Triage Workstation VM on our hosted platform.

Find out where the file forest_stream.jpg was downloaded from on the Triage Workstation and you'll have your flag!

Advanced 
300 points


For this one I used autopsy and opened a new case with all the recent files. Going to the downloads, we can see the zone identifier and the url of the image.
![the autospy window](/Images/MoTW_flag.png)

If you don't want to go overkill the way I did, I learnt that there is another easier way to do it(thank you tsuto for teaching me). We can get the alternate data stream and getting the content of the Zone.identifier gives us the url.

![the intended way I suppose](/Images/MoTW_intended.png)

`flag: leveleffect{gently_down_the_stream}`

