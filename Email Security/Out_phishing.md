# Out phishing 

A Goodcorp employee recently reported a phishing attempt to his company email address. We've provided the email headers for you to analyze. What country is the original sending server hosted in?

Looking at the text I found an IP address presumably of the sender:
`Received: from goodcorp.com (unknown [193.217.1.27]) by ip-172-26-30-121.us-west-1.compute.internal (Postfix) with ESMTP id AEC1530C94 for <bob.guppy@goodcorp.com>; Fri, 15 Mar 2024 05:04:09 -0700 (PDT)`
 
I googled the ip which led me to ipinfo.io and I got the Country. Its Lithuania

`flag: leveleffect{Lithuania}`


