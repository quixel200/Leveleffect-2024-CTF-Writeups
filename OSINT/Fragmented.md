# Fragmented 

It's a good habit to be suspicious of shortened links, but this one might be worth looking at a little more closely...
Beginner 
100 points 

visiting the link takes us to a...recipe page? looking at the source just gave me a headache. but I noticed that the url had what looked to be a base64 encoded string so I tried decoding it

https://www.howsweeteats.com/2020/05/baked-beans/#bGV2ZWxlZmZlY3QlN0I2NjcyMzQ2NzZkMzM2ZTc0MzUlN0Q=

`echo "bGV2ZWxlZmZlY3QlN0I2NjcyMzQ2NzZkMzM2ZTc0MzUlN0Q=" | base64 -d` 

which gives us 

`leveleffect%7B667234676d336e7435%7D`

which is the flag...kinda, its url encoded, when encoding the { gets converted to a %7B and the } becomes %7D

so the actual flag is 

`flag: leveleffect{667234676d336e7435}`
