# Think you're flag worthy? 

The flag may be encrypted but it most certainly can be recovered. Can you retrieve it?

There are a few ways to approach this one, some more efficient than others.

```
$key = "seinfeld"; -join ([char[]](([Text.Encoding]::UTF8.GetString(([Convert]::FromBase64String("GgNJRkdFNxcHFwAAAThWXjoWJxsKCSMWNggZGh9NNzcKFh0LC0spCgUMGwEICAkKBzhTVCEAGCEdEwAcCQsBAR0RPw8UDA0GHwBBSTYpKSUgIE5HT0xMH3lFSU5GQQoIEgJJU0ZHAAEFAAULAAMJBwceGgsUAAINBxw2AAkSEUZ5RUlORjIeDQcARCETERwRB0VLLwUGCRcARQ4cBwsYARdJSRoOAEwCHwQOTg8WVkRXAwUPAUdmGVMABR0DRRduU0VJTjEXBRAWSCYbEhUZEFNHKAZKRQ0MX0UIBkdFNQsGRQ0HAgtLEFMWCBdGEQQBUwgICQ8GTBMcFw1PRG8R") | % { [char]($_ -bxor [byte][char]$key[$i++ % $key.Length]) } -begin { $i=0 }))))) | iex
```

Intermediate 
250 points 

Now you can try to decode the base64 string and do it manually, but notice that the output of the variable is piped to iex, which runs the string as a command, the string being $key presumably. 
So we can just remove the iex, and echo out the variable to see what the command is.

lets run just this part in powershell and see what happens:
` $key = "seinfeld"; -join ([char[]](([Text.Encoding]::UTF8.GetString(([Convert]::FromBase64String("GgNJRkdFNxcHFwAAAThWXjoWJxsKCSMWNggZGh9NNzcKFh0LC0spCgUMGwEICAkKBzhTVCEAGCEdEwAcCQsBAR0RPw8UDA0GHwBBSTYpKSUgIE5HT0xMH3lFSU5GQQoIEgJJU0ZHAAEFAAULAAMJBwceGgsUAAINBxw2AAkSEUZ5RUlORjIeDQcARCETERwRB0VLLwUGCRcARQ4cBwsYARdJSRoOAEwCHwQOTg8WVkRXAwUPAUdmGVMABR0DRRduU0VJTjEXBRAWSCYbEhUZEFNHKAZKRQ0MX0UIBkdFNQsGRQ0HAgtLEFMWCBdGEQQBUwgICQ8GTBMcFw1PRG8R") | % { [char]($_ -bxor [byte][char]$key[$i++ % $key.Length]) } -begin { $i=0 })))))`

the output we get is:
```
if (! [string]::IsNullOrEmpty([System.Environment]::GetEnvironmentVariable('PLEASE'))) {
    $flag = "leveleffect{serenity_now}"
    Write-Output "Access granted, the flag is: $flag"
} else {
    Write-Output "Ah, ah, ah! You didn't say the magic word!"
}
```
the script checks if theres an environment variable PLEASE available, if it is, it prints the flag.
now if the flag was obfuscated we would set the env variable using the following command:
`$Env:PLEASE='plz gib flag'`

and running the script now will give you the flag.



`flag: leveleffect{serenity_now}`
