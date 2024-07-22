#  Back to basics 2

Which nameserver is the SOA (Start of Authority) for the leveleffect.com domain?

Beginner 
100 points 

I googled how to find the SOA and got this website:
https://www.nslookup.io/soa-lookup/

searching for levelefffect.com we get the following info

![SOA record](/images/back_to_basics_2.png)

it even provides us a command we can use to establish the linux cli supremacy:
`dig @ns-134.awsdns-16.com. leveleffect.com. SOA`

`flag: leveleffect{ns-1327.awsdns-37.org}`


