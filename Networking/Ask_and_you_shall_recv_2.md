# Ask and you shall recv 2 


Your goal is to SSH to 0.cloud.chals.io over port 21986 using the private key provided for download. The passphrase is cda-od.

The username to connect with is the name of the operation led by law enforcement agencies in January 2021 that dealt a considerable blow to Emotet infrastructure.

Note - sharing private keys is always a bad idea - this is only for the purposes of the challenge.

Beginner 
150 points 

to connect using a private key, we can use the -i argument
-p argument can be used to specify the port
for anyone who hasn't used ssh, the general sytax is:
`ssh [username]@[hostname]` 

to find the username, I first searched for emotet,got info on the operation but the name of the operation wasnt provided.
refining my google search a little, "name of operation that took down emotet" provided the answer, which is 'ladybird'

so the command to connect is:

`ssh -i p2.private.key ladybird@0.cloud.chals.io -p 21986`

note: ensure that your private key has the correct perms, it can be changed using:
`chmod 600 p2.private.key`


we get the flag after connecting:

`Nice job! Here's your flag: leveleffect{private_keys_are_private_for_a_reason}`
