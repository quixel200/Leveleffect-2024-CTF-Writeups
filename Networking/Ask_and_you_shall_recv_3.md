# Ask and you shall recv 3 



This time, the flag is hosted on a webserver running internally at 0.cloud.chals.io on port 8888. SSH is exposed on port 27141. The private key for user tunneler is provided for download and the passphrase is cda-od.

Can you figure out how to get to the flag?

Note - sharing private keys is always a bad idea - this is only for the purposes of the challenge.


Intermediate
250 points 

now we have access to ssh on a different port but how do we access the server on 8888?

lets try connecting to the ssh server first.
we get the following message:
`You're on the right track but the path above is closed. Try digging under, but do it fast!`

we cannot run any commands and the connection closes after a few seconds.
One way to access the internal network is through a technique called port forwarding.

The way port forwarding works is it allows you to forward the traffic from a port on the internal network to your local network. 

heres a great resource where you can read more about this:
https://iximiuz.com/en/posts/ssh-tunnels/

we can create a remote port forward in ssh using:
`ssh -i p3.private.key -L 8888:localhost:8888 tunneler@0.cloud.chals.io -p 27141`

accessing the webserver, we get the flag.

![reverse port forwarding](/Images/remote_port.png)

`flag: leveleffect{attack_from_within}`
