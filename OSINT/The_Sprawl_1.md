# The Sprawl - 1

These IOCs were discovered on a compromised endpoint. Figure out the first flag by interacting with the binary.
Beginner 
100 points 

We are provided with a binary.
Lets try running it... in a lab environment ofc (flareVM ftw)

once the binary starts, we are greeted with a message

```
Welcome! Let's get started.                                                                                             
Are you ready to begin?
```
uhh yes?
yes seems to be correct answer. 

next it asks us
`Are you who you say you are? Enter 'I give up' at any time to exit.`

it then opens a browser tab showing the wiki page for Armitage
https://williamgibson.fandom.com/wiki/Armitage

I Just assumed we were armitage and it worked.
and we get out first flag

`Well done Jake, your first flag is: leveleffect{jakearmitage}`



