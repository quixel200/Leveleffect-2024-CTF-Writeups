# That's epoch 

Learning about the Y2K38 problem will lead you to a way to decode the flag. 1721387471

The flag is in the format leveleffect{dd MMMM yyyy HH:mm:ss}

Beginner 
100 points

searching for the Y2K38 leads us to the wikipedia article
`The year 2038 problem (also known as Y2038,[1] Y2K38, Y2K38 superbug or the Epochalypse[2][3]) is a time computing problem that leaves some computer systems unable to represent times after 03:14:07 UTC on 19 January 2038.

The problem exists in systems which measure Unix time—the number of seconds elapsed since the Unix epoch `

so it occurs due to unix time, seeing the flag requires a specific time, im guessing the integer represents unix time.

heres a code I got to convert the time in python:
```
import datetime

# Given Unix timestamp
timestamp = 1721387471

# Convert to human-readable date and time
date_time = datetime.datetime.utcfromtimestamp(timestamp)

# Format the date and time as per the required flag format
flag = date_time.strftime('leveleffect{%d %B %Y %H:%M:%S}')

print(flag)
```

`flag: leveleffect{19 July 2024 11:11:11}`

