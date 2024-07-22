# If only it were this easy 



Flag: 577ca2e5adb9dc46b44f668923055b238243f9b398c670584430e1e327141949ed345afce50fa4c9de130d3c331936cebd5104206a959daf74b9f15b68cfb193

Key: 00112233445566778899aabbccddeeff00112233445566778899aabbccddeeff

IV: 0102030405060708090a0b0c0d0e0f10

Beginner 
100 points 

now the encryption looks like its AES because AES is the only one I know that uses a Initialization Vector(IV)
lets use cyberchef to decrypt it.
decrypting it gives us a base64 encoded string:
`bGV2ZWxlZmZlY3R7a2V5c19hcmVfbWVhbnRfdG9fYmVfa2VwdH0=`
decoding this gives us the flag

`flag: leveleffect{keys_are_meant_to_be_kept}`


