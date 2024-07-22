#  APT jeopardy 3



Aerocorp, a subsidiary of Goodcorp, recently suffered a massive data breach by a sophisticated actor. Can you identify the group responsible?

    We believe employee credentials were initially compromised via spearphishing campaign.
    A handful of employees were social engineered into clicking on malicious attachments.
    The use of Cobalt Strike was observed in post-compromise network traffic.
    Operations found post-compromise PowerShell activity consistent with the PowerSploit framework.
    The attackers scheduled remote AT jobs via commandline.
    Forensics recovered a binary created around the time of compromise with the hash 40528e368d323db0ac5c3f5e1efe4889 .
    Logged network traffic reveals that images with unusually large file sizes were uploaded to various GitHub accounts.

Name the APT!

Advanced 
300 points 


We are given a file hash. lets look it up on virustotal.
Looking at the community tab, we see that its a apt group from china.
with this info, we can ask claude and it provides the answer for us.

`flag: leveleffect{Leviathan}`

