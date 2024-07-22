# SCH Part 8 - Beacon 

There's a flag being transmitted somewhere...

Advanced 
300 points


if the flag is being transmitted, then it must be captured by wireshark, I first tried looking throught the packets in the eth adapter but there was way too much traffic there so I tried the loopback adapter, now generally I have never seen traffic on the loopback adapter before and so I checked it out.

We see the http post request that is sending our data.
following the tcp stream, we can see our flag

![the flag](/Images/sch_part8.png)

`flag: leveleffect{et_phone_home}`
