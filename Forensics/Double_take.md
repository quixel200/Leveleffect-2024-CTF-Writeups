# Double take 

I'm sure this image is hiding something, but nothing stands out no matter how I look at it. Maybe it's just stringing me along...

Intermediate 
200 points

the phrase 'stringing me along' seems to be a suggestion to try strings.
lets do that.
But I couldnt find anything of interest.

Now I went down a completely different rabbit hole and wasted a bunch of time.
I then decided to use a binary visualisation tool like https://binvis.io/   
looking at the visualisation, I noticed this weird little part at the bottom
![binary visualisation](/Images/doubletake_vis.png)

right at the end of the file, we have this:
```
0001efb0: da00 0801 0301 013f 0034 9f62 0047 0056  .......?.4.b.G.V
0001efc0: 0032 005a 0057 0078 006c 005a 006d 005a  .2.Z.W.x.l.Z.m.Z
0001efd0: 006c 0059 0033 0052 0037 0063 0032 0035  .l.Y.3.R.7.c.2.5
0001efe0: 006c 0059 0057 0074 0035 0058 0033 0056  .l.Y.W.t.5.X.3.V
0001eff0: 0030 005a 0069 0030 0078 004e 006d 0078  .0.Z.i.0.x.N.m.x
0001f000: 006c 0066 0051 003d 003d 00ff d9         .l.f.Q.=.=...
```

seems to be a base64 encoded string!
`bGV2ZWxlZmZlY3R7c25lYWt5X3V0Zi0xNmxlfQ==`

decoding this using cyberchef gives us the flag.

`flag: leveleffect{sneaky_utf-16le}`

