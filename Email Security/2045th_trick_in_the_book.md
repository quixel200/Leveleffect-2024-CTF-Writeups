# 2045th trick in the book 



This is a common encoding system that phishers abuse in their endless quest to bypass email scanners. Can you figure out what it is?

=C6=96=D0=B5=CE=BD=D0=B5=C6=96=D0=B5=C6=92=C6=92=D0=B5=D1=81=C5=A5{=D4=81=
=CE=BF=D5=B8=C5=A5=5F=D1=98=CA=8B=D1=95=C5=A5=5F=D1=81=CE=BF=D1=80=D1=83=5F=
=D1=80=D0=B0=D1=95=C5=A5=D0=B5=5F=C5=A5=C4=A7=D1=96=D1=95=5F=D1=96=D5=B8=
=C5=A5=CE=BF=5F=C5=A5=C4=A7=D0=B5=5F=D0=AC=CE=BF=D1=85}


Intermediate 
200 points 

I had to ask claude for this one, Its response was:
```
This appears to be text that has been encoded using Quoted-Printable encoding, which is commonly used for email transmission. Quoted-Printable encoding represents non-ASCII characters and some ASCII characters using an equals sign (=) followed by two hexadecimal digits.
To decode this, we would need to:

Replace all occurrences of "=\n" (equals sign at the end of a line) with nothing, as these are just line breaks in the encoded format.
Replace each "=XX" sequence with the corresponding character represented by the hexadecimal value XX
```

interesting, I checked cyberchef and it had a quoted printable option which gave me the flag.
its in some weird font and we have to type out the flag manually.

`flag: leveleffect{dont_just_copy_paste_this_into_tbe_box}`


