# APT jeopardy 2 



Goodcorp recently suffered a data breach. The nature of the breach and the sophisticated tactics observed suggest the threat actor is likely an APT. The Incident Response team collected the following from its investigation:

    The initial point of compromise was a spearphishing email.
    The email was designed to mimic an MFA alert and contained a malicious QR code.
    The link in the QR code led to the site thepiratecinemaclub[.]org NOTE: Do not attempt to visit this site.
    Once on the system, a persistence mechanism in the form of a modified version of CpuTrace was dropped.
    We found artifacts of a C2 proxy known as XTunnel on compromised systems.

There are more pressing matters than attribution here, but for the purposes of the challenge, name the APT!

Intermediate 
250 points

More googling.We have a domain given so we can use that to find the apt.
this is the website I found:
https://otx.alienvault.com/indicator/domain/thepiratecinemaclub.org

We can see under tags that its APT28 also known as fancy bear

`flag: leveleffect{fancy bear}`


