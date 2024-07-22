# Pardon the intrusion 



In 2023, Cisco disclosed information about the active exploitation of a critical vulnerability in its software that allowed a remote, unauthenticated attacker to gain access to internet-facing network devices and create a local user account. This initial access paved the way for a privilege escalation vulnerability disclosed around the same time that would eventually lead to a full compromise of the system.

The first vulnerability received a CVSS score of 10.0 CRITICAL. The flag is the CVE identifier for that vulnerability.

Intermediate 
200 points 

reading through the description, a few things stood out to me:
- it happened in 2023
- it has a CVSS score of 10.0

so I googled "cisco 2023 cves"

and one of the results was this page:
https://nvd.nist.gov/vuln/detail/CVE-2023-20198

the description reads:
```
The attacker first exploited CVE-2023-20198 to gain initial access and issued a privilege 15 command to create a local user and password combination. This allowed the user to log in with normal user access. The attacker then exploited another component of the web UI feature, leveraging the new local user to elevate privilege to root and write the implant to the file system
```

we have our answer!

`flag: leveleffect{CVE-2023-20198}`


