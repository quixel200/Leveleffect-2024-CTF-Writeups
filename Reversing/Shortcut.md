# Shortcut 

The key to solving this challenge is LNKing things together!

Advanced 
300 points

Lets take a look at the flag.ps1 script. The GetFlag just seems to call the script.
The script contains some heavily obfuscated code, first, lets rename the variables to something that makes a little more sense.
```
param ([string]$param1)

$hash = ('2348f'+'9'+'987'+'442125'+'7'+'5d8595'+'9'+'674f9'+'607ab26f6'+'7708a'+'9171574728323'+'86337c9'+'04')
$calculated_hash = [BitConverter]::"TOs`Tri`NG"([Security.Cryptography.SHA256]::"cre`A`TE"()."COmp`UTE`hA`Sh"([Text.encoding]::"u`TF8"."geTb`yt`es"($param1)))."rE`PLAce"("-", "")."t`Olo`WER"()

if ($calculated_hash -eq $hash) {
    $b64_encoded_str = [Convert]::"FROmB`As`E`64sTri`Ng"(('k+pPN'+'S6'+'diYRE'+'xok'+'cOJhw3C+Zim2e'+'nMC6zgfJ'+'v'+'vJVZTUW7mXo513bM'+'n'+'xLSQ'+'Mhn'+'b'+'D'+'f'))

    $c2FsdA = [byte[]]::"n`Ew"(8)
	$aXRlcg = 10000
    $a2V5 = [Security.Cryptography.Rfc2898DeriveBytes]::"N`eW"($param1, $c2FsdA, $aXRlcg)."GE`TBYT`ES"(32)
    $aXY = [byte[]]::"n`ew"(16)

    $YWVz = [Security.Cryptography.Aes]::"CRE`ATE"()
    $YWVz."K`EY" = $a2V5
    $YWVz."I`V" = $aXY

    $flag = [Text.encoding]::"ut`F8"."gEts`T`RiNg"($YWVz."cREA`Te`de`cRYPtOR"()."t`Ra`NsFoRMF`i`NalBLO`Ck"($b64_encoded_str, 0, $b64_encoded_str."leN`Gth"))

	$env_variable = [Text.encoding]::"UT`F8"."GetS`T`RInG"([Convert]::"FROM`BaS`e64s`Tri`Ng"(('c2'+'VzYW1'+'l')))
	if ($env:P2 -eq $env_variable) {
		.('Writ'+'e-O'+'utpu'+'t') ('Nic'+'e '+'work'+'!'+' '+(('Here'+'ca'+'Ks ') -replace ([Char]99+[Char]97+[Char]75),[Char]39)+'yo'+'ur '+'flag:'+' '+"$flag")
		.('Sta'+'rt-Slee'+'p') -Seconds 10
	} else {
		.('Write'+'-O'+'ut'+'put') (('ThatXh0s on'+'ly '+'o'+'ne c'+'orr'+'ect p'+'art'+' of'+' the '+'pas'+'sp'+'h'+'ra'+'se you '+'ha'+'ve'+' the'+'re '+'..'+'.')."ReP`La`cE"(([cHAR]88+[cHAR]104+[cHAR]48),[sTrING][cHAR]39))
		.('S'+'t'+'art-Slee'+'p') -Seconds 2
	}
} else {
    &('Wri'+'te-O'+'utp'+'ut') ('Ex'+'i'+'ting'+' ...')
	.('Start'+'-'+'Sleep') -Seconds 2
}
```

The script takes one parameter as its argument.
the $hash variable has a harcoded hash that looks like sha256, the $calculated_hash seems to convert the argument we provide into a hash.
it then checks if both the hashes are equal.
At first I thought that the argument might be a file so I googled it, which led me to this website:
https://www.perturb.org/content/hashes/?word=open

so turns out its the sha256 hash for the word 'open', maybe something like hashcat could have cracked it.

now if the hashes are equal, it performs a bunch of stuff that I am assuming is calculating the value of the flag.
the important part we care about is the $env_vaiable
it converts a base64 string and checks if the value of the variable env:P2 is equal to the b64 value, lets check what that value is
`echo "c2VzYW1l" | base64 -d `

it says 'sesame'!

lets set the variable P2 to sesame in powershell and run the flag.ps1, with an argument of 'open'

```
$env:P2='sesame'
.\flag.ps1 "open"
```
which gives us the flag.

`flag: leveleffect{threat_actors_love_shortcuts}`

