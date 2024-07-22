# Bits abound 



I have a key with a curious code etched into it but not a clue where it goes. Here, take a look and let me know if you discover anything even the least bit significant about it.

the image:
![key](/Images/key.png)

now the description seemed to be hinting at something with the phrase 'discover anything even the least bit significant about it'
so I decided to perform a LSB analysis on the file.
This just means taking only the least significant bit of each byte and seeing if theres anything hidden. Ill use the following script I found on github for this:
https://github.com/Pulho/sigBits

seems I was right... in the output we see this weird little string:
`TW9Xb01vR2xEaVVxVmtYVVVlfnpUfn5+VmV+a09ufn5WZX5+Tm1EfklvU3c=`

decoding this base64 string we get:
`MoWoMoGlDiUqVkXUUe~zT~~~Ve~kOn~~Ve~~NmD~IoSw`

which seems pretty random, but wasnt there a key on the image?
the key was '21a', lets try to xor with that key... and we get our flag!

`flag: leveleffect{way_to_put_two_and_two_together}`
