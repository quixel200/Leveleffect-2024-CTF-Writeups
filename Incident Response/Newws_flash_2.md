# Newws flash 2 



Our detections hit on the file hash b1f2068201c29f3b00aeedc0911498043d7c204a860ca16b3fef47fc19fc2b22. The sample is observed to create a registry Run key under HKCU. Can you find the name of the file that key is set to execute?

Intermediate 
200 points 

I can think of two ways to do this, one is to disassemle the binary and go through the code and try to find the key, or just run the file and use procmon to see changes to registry key.
I first tried googling the file hash and looking at the results from any.run, I couldnt find the answer, so I went to malwarebazaar and downloaded the binary to run in my vm.

So I filtered using procmon to show just the registry keys and found that the binary sets a Run key with 'Steam'

![registry key](/Imagess/news_flash_2.png)

the answer is steam.

`flag: leveleffect{steam}`


