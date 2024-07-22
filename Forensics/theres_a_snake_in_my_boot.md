# There's a snake in my boot!

A classic game of Snake, but the developer left the winning flag in the binary a little too exposed.

Beginner 
100 points 

Lets look at the strings of the binary first
`strings snek`
I looked through it and maybe I wasn't looking hard enough, lets try to filter the result using grep and see if we get lucky.
`strings snek | grep "leveleffect"`
and we get our flag!

`flag: leveleffect{sn4k3_1n_th3_t411_gr455}`


