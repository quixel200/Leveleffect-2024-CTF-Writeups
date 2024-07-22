# Git 'em 

We have observed conversations on an underground forum that indicate potential plans to target Goodcorp. Here's a snippet of the discussion. Can you find more information on these users and figure out their plan?

Шадоу
14:04 (22 minutes ago)
To jakearmitage1337

Чувак! Нафига ты такую инфу на всеобщее обозрение выложил! 
Быстро убери, пока вся операция не накрылась! 

----------------------------------------------------------

jakearmitage1337
14:09 (17 minutes ago)
To Шадоу

Сорян, босс! Проглядел. Уже убрал, так что всё норм.

Advanced 
300 points

A snippet of the discussion is provided, lets use google translate and see what it says.

`Dude! Why did you post such information for everyone to see! 
Clean it up quickly before the whole operation is covered!`

`Sorry, boss! I missed it. I already removed it, so everything is fine.`

hmm...interesting so something important was posted for everyone to see and then changed, I first googled for the user 'jakearmitage1337' but that wound up with no results.
the challenge name says "git em" so maybe it has something to do with github?
searching github for the user...we got a result!

the user has one repo named SuperSecretProject

lets git clone the repository and look at it.
`git clone https://github.com/jakearmitage1337/SuperSecretProject.git`

looking at the files...none of them seem to contain the flag, the conversation did mention that it was changed so lets check the log using 
`git log`

the first commit has:
```
commit 23647d7154b75efe923d46515e809d74a18c60f6
Author: jakearmitage1337 <jakearmitage1337@gmail.com>
Date:   Mon Jun 17 11:33:32 2024 -0500

    innocuous file
```

lets see what the file is using 
`git checkout 23647d7154b75efe923d46515e809d74a18c60f6`

now we have a testfile, looking at the contents of the testfile...its the flag!

`flag: leveleffect{051n7_15_4_p0w3rfu1_t001}`

