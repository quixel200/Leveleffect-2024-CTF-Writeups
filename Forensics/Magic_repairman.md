# Magic repairman 

You'll probably need some tools to fix this one. Hexedit, HxD or hexed.it are commonly used.

we are provided with a .png, however we cant open it. running the file command just shows 'data'.
Now the way files are recognized on your system are through file signatures. This is a unique hex value at the beginning indicating its type. For example, Portable executables always start with a .MZ

we can check the file signatures for various file formats here:
https://en.wikipedia.org/wiki/List_of_file_signatures

for a png file, the magic bytes at the beginning are:
`89 50 4E 47 0D 0A 1A 0A`

looking at the files bytes we see:(using xxd or hexdump)
`00000000: 8952 4e47 0d0a 1a0a 0000 000d 4948 4452  .RNG........IHDR`

we can fix the header using something like hexedit,HxD or if you're feeling like a pro...using vim.

after we fix the image, we get the flag
![flag](/Images/magic_repairman.png)

`flag: leveleffect{corrupted_magic_purification}`


