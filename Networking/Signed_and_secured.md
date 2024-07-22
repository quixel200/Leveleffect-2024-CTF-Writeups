# Signed and secured

We have intercepted some network traffic after an alert hit from our SOC. Something seems off about some of the traffic here, but we haven't found anything concrete yet...

Beginner 
150 points 

I first used wireshark to analyse the packets, I couldn't find anything so I decided to use a online pcap analyser.This is what I used:
https://apackets.com/

looking through the actual packets yielded no results, and I couldn't find any suspicious looking IP's either. Next I looked through the tls/ssl certificates, one of them was self-signed... with the flag!


