# SCH Part 6 - Check out 

I am sending my precious enumeration data somewhere.

Provide the full domain and port, such as domain.tld:4444

Intermediate 
250 points 


lets set a filter in procmon for olgreg.exe and look at the network traffic in procmon
![the domain of the exiltrated data](/Images/olgreg_network.png)

we can see that it sends our data to `leveleffectexfilsyourdata.com:9001`

`flag: leveleffect{leveleffectexfilsyourdata.com:9001}`


