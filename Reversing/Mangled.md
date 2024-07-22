# Mangled

Pack? Sure. Unpack? Well...


Advanced
350 points 

From the description, it seems that we have a packed binary on our hands.
binary packing is the technique of compressing executables to make them smaller, also very useful in obscuring content.

Basically in a packed binary you will find a stub section, the stub section will first run, unpacking the binary and then jump into the unpacked code.
If you look through the disassembler for a packed binary, you will notice a repeating pattern:
a bunch of cmp and jmp instructions.
and then jumps to a function or address that is outside the memory of the program.

if you run strings, you will also notice that the binary is way too clean. Sometimes the name of the packer can be found in the strings.
heres a great article where you can read more about unpacking and identifying them:
https://book.hacktricks.xyz/crypto-and-stego/cryptographic-algorithms/unpacking-binaries

I will be using x64dbg to run the program in a debugger.

Now we're only insterested in the strings of the program once its done unpacking, so we don't really need an exact address for the breakpoint, lets just try one towards the end that doesnt quit the program.
I just set a breakpoint at the very last ret instruction, and looked at the memory dump,Found it!

![the flag](/Images/mangled_flag.png)

`flag: leveleffect{upx_i_did_it_again}`
