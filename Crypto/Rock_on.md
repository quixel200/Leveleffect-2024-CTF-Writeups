# Rock on 



Getting it out is the easy part, but good luck getting in.

Intermediate 
250 points 

we're provided with a capture file...
looking throught it we see a GET flag.zip
lets export the zip file from wireshark
file-> export objects-> http

lets try to unzip the file...its password protected. great.

now the challenge name seems to be hinting at the 'rockyou.txt' file that contains a list of commonly used passwords. You can find it on git here:
https://github.com/praetorian-inc/Hob0Rules/blob/master/wordlists/rockyou.txt.gz

if you're on kali linux, the file can be found at /usr/share/wordlists/rockyou.txt

we can bruteforce zip files using johntheripper.

lets convert it into a format that john can understand using zip2john

`zip2john flag.zip > zip.hash`

we can run john using the command,
`john --wordlist=/usr/share/wordlists/rockyou.txt zip.hash`

`john --show zip.hash` will show you the password
its `Cena.John.Rulz`

extracting the zip file, we get a flag.pdf file...which is also password protected.

searching for a tool to crack pdf passwords led me to:
https://www.kali.org/tools/pdfcrack/

the usage is pretty simple, lets use the rockyou wordlist.

`pdfcrack -f flag.pdf -w /usr/share/wordlists/rockyou.txt`

and it found the password for us!
`found user-password: 'Fcrunner1337'`

opening the pdf document gives us the flag

`flag: leveleffect{l375_g37_cr4ck1n}`
