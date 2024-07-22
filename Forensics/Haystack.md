#  Haystack 



The flag is in here somewhere...

Intermediate 
250 points 

we have a folder named haystack that has contains multiple folders with the name `level1,level2 etc.` and each of these folders contain `effect1,effect2 etc.` and within these folders theres multiple flag.txt files.

opening one of the flags at random we see:
`62 47 56 32 5a 57 78 6c 5a 6d 5a 6c 59 33 52 37 5a 6d 46 72 5a 56 39 6d 62 47 46 6e 66 51 3d 3d`

which when decoded from hex gives us,
`bGV2ZWxlZmZlY3R7ZmFrZV9mbGFnfQ==`
and now decode base64,
`leveleffect{fake_flag}`

I noticed that this pattern is in every file I opened, which means the real flag must be different.
lets make a python script to find it for us.

```
import os

def find_real_flag(root_folder):
    for dirpath, dirnames, filenames in os.walk(root_folder):
        for file in filenames: # traverse each file in the directory
            if file.startswith('flag'): 
                file_path = os.path.join(dirpath, file) # join the name to the filepath to open
                with open(file_path, 'r') as f:
                    content = f.read()
                    if '62 47 56 32 5a 57 78 6c 5a 6d 5a 6c 59 33 52 37 5a 6d 46 72 5a 56 39 6d 62 47 46 6e 66 51 3d 3d' not in content: # this is the fake flag we found earlier
                        print(f"Real flag found in: {file_path}")
                        print(f"Content: {content}")
                        break
    print("Real flag not found.")

find_real_flag('/home/quixel/Desktop/leveleffect/haystack')
```

the os.walk yields a tuple with 3 values: (directory path,directory name,filenames)
we will traverse each file in the directory, open the file and check if its not equal to fake flag.
if it is not, we will print it.

lets run it.

```
Real flag found in: /home/quixel/Desktop/leveleffect/haystack/Level17/Effect13/flag37.txt
Content: 62 47 56 32 5a 57 78 6c 5a 6d 5a 6c 59 33 52 37 63 6a 4e 6e 4d 33 68 66 5a 6e 52 33 66 51 3d 3d
```

lets decode this
hex -> base64

`flag: leveleffect{r3g3x_ftw}`
