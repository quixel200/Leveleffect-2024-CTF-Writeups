#  Back to basics 1

What is one IPv4 address resolved from the leveleffect.com domain?

beginner 
100 points 

googling how to find the resolved ip, we are told to use the `nslookup` command 

```
nslookup www.leveleffect.com 

Server:         218.248.112.65
Address:        218.248.112.65#53

Non-authoritative answer:
www.leveleffect.com     canonical name = 21954108.group8.sites.hubspot.net.
21954108.group8.sites.hubspot.net       canonical name = group8.sites.hscoscdn00.net.
Name:   group8.sites.hscoscdn00.net
Address: 199.60.103.226
Name:   group8.sites.hscoscdn00.net
Address: 199.60.103.30
Name:   group8.sites.hscoscdn00.net
Address: 2606:2c40::c73c:67e2
Name:   group8.sites.hscoscdn00.net
Address: 2606:2c40::c73c:671e
```
it resolves to 218.248.112.65#53, which is our flag.

`flag: leveleffect{218.248.112.65#53}`

