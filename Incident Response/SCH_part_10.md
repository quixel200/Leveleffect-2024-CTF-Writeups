# SCH Part 10 - Slippery slug

I'm the parasite. What is my hash? (SHA-256)

Advanced 
350 points 


Looking at process explorer, we can see olgreg attached to explorer.exe. I tried submitting the hash of olgreg but that is not the answer.
If we look at the dlls of explorer.exe, we see one that does not have a company name and is located in the Users directory.

![the dll](/Images/sch_part10.png)

this is a dll injection. more info can be found [here](https://www.youtube.com/watch?v=7fOa2IWZIck)

the answer is the hash of the dll, we can get the hash with the command:
`Get-FileHash .\IECleanCache.dll`

`flag: FC6C275FDE21FE347CA700D514F490B89AB521A15CCFCBDE9E46B79F1BC5E6C0 or leveleffect{FC6C275FDE21FE347CA700D514F490B89AB521A15CCFCBDE9E46B79F1BC5E6C0}`
