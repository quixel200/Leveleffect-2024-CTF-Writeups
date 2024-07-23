# RPMs to the max 

This is an actual malware sample seen in the wild. It's been defanged but it retains a lot if its original indicators. Amidst those indicators, you guessed it, is the flag!

Advanced 
350 points 

I ran floss(a tool for extracting strings in flareVM) and it identified that its a dot net binary. Now you could use something like PEStudio or just look through the strings to find identify this.

Now .NET uses an intermediate language called CIL(Common Intermediate Language), and CIL is really easy to reverse engineer similar to java bytecode. So you almost get the source code when reversing it.
Ill be using the tool dnspy, this is what I am familiar with, however it has been archived since 2020 so you might want to look at alternatives like ILspy and dotPeek.

What we're looking for is an indicator, and seeing to how its a flag, it might be hidden as a string, or being transferred through some network once the binary runs.

Simply running the binary prints out 'hello there' and it exits,no network traffic, no files created...interesting.
![the message printed when the binary is run](/Images/hello_there.png)


lets look at the code in dnSpy and see whats happening, if we go to the main function, we can see this segment.
![the dnspy code](/Images/hello_dnspy.png)

lets try to make sense of this code, it first runs what seems to be an environment check, now this can't be what failed, because if it did, then the binary would just exit and we would not see the message. so the check is not the issue here.

next, we have:
`if (!string.IsNullOrWhiteSpace(Arguments.Message))`

from my understanding, it checks if the 'Message' in arguments is empty, and if it is not empty, then it shows us 'hello there' and exits.
lets look at what the message is, looking at the arguments class

![the arguments class](/Images/arguments_class.png)

We see some more interesting info, like a IP string, and a key.
Looking further into main, we can see that it calls a 'StringDecrypt' function with arguments IP, and key.
lets look into the function, heres the interesting line:
`text = StringDecrypt.FromBase64(StringDecrypt.Xor(StringDecrypt.FromBase64(b64), stringKey));`

so it decodes the text from base64, performs an Xor with the key we found in Arguments, and then decodes from base64 again.

Now if you're really good at programming(unlike me), you could try to write your own code and just decrypt the IP and message strings.But I am going to have the program work for me.
In order for the program to run, it needs to decode the strings at some point, so what if we just set a breakpoint there and see what the value is?
first lets make the message string empty and store it somewhere else so that the rest of the program can run, and lets set a breakpoint after the call to decrypt to see what the IP is

![the decrypted ip](/Images/ip_decrypted.png)

well its 1.2.3.4:6789, not that useful, but wait we still haven't decrypted the message yet. Lets replace the text in the ip field with the message and repeat the same process.
and we get the flag!

![rpms flag](/Images/rpms_flag.png)

`flag: leveleffect{stealing_from_the_stealer}`


