# Puzzle pieces 

I had a flag on this handy QR code, but a fiend cut it up into pieces and threw one of them away! Is there still a way to retrieve the flag?

Advanced 
350 points 

We have three segments of a qr code with one segment missing

heres the basic structure of a qr code:
![qr code structure](Images/qr_code_structure.png)

I also found this website that tells you how to read QR codes manually:
https://qr.blinry.org/

this was my original plan but I couldn't figure out how to apply the mask pattern and sought other methods.

now for every qr code the alignment pattern(the big squares on three sides) and the timing pattern(alternating stripes of black and white) do not change.
so lets try to reassmble the qr code and fill those in.
heres the result:
![kinda complete](Images/qr_code_incomplete.png)

Now the version information can also be recovered because the bits repeat and after all that I get this:
![the final code](Images/qr.png)

I first tried decoding it manually, failed miserably.
Then I searched for tools online that could perform qr code analysis and recovery, which lead me to this site:
https://merri.cx/qrazybox/

lets open the qr we created,
select tools->Extract QR Information

`Decoded data : leveleffect{r3dund4n7_d4t4} Congrats!UEll playUUUJªª`

and we have our flag!

`flag: leveleffect{r3dund4n7_d4t4}`
