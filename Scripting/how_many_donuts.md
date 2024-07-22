# How many donuts?

Samwise, I've had enough of your lembas bread. I want donuts. How many you ask? well I wrote you a script. It mostly works, but the answer will be revealed when it does. I mean at least a couple of them!

Intermediate 
200 points 

Now I suck at shell scripting so I turned to claude for some help and heres the response I got:
```
#!/bin/bash

# Define the list of ASCII values
ascii_values=(102 104 116 122 117 113 106 116 107 103 116 125 106 115)

# Function to convert ASCII values to characters and print them as a word
print_word_from_ascii() {
    local word=""
    for value in "${ascii_values[@]}"; do
        char=$(printf \\$(printf '%03o' "$value"))
        word+="$char"
    done
    echo "$word"
}

# Loop to print the word 3 times, decreasing ASCII values each time
for i in {1..3}; do
    print_word_from_ascii
    # Decrease each ASCII value by 11
    for j in "${!ascii_values[@]}"; do
        ascii_values[j]=$((ascii_values[j] - 11))
    done
done
```

```
Here are the changes I made:

In the print_word_from_ascii function:

Changed the printf command to use octal format ('%03o') for proper ASCII conversion.
Removed the duplicate addition of $char to word.

In the main loop:

Changed the loop count from 5 to 3 as per your comment.
Removed the argument passed to print_word_from_ascii as it's not needed (the function uses the global ascii_values array).
```

now I noticed some mistakes in the script, the first one:
the loop is supposed to run 5 times
and the value needs to be decremented by 1, not 11.


This still gave me gibberish for output, so I decided to experiment some more

heres the final edited script:
```
#!/bin/bash

# You wanted to know how many donuts I wanted? I wrote a script for you that will provide you the answer. Pretty sure it works - I think.

# Define the list of ASCII values
ascii_values=(102 104 116 122 117 113 106 116 107 103 116 125 106 115)

# Function to convert ASCII values to characters and print them as a word
print_word_from_ascii() {
    local word=""
    for value in "${ascii_values[@]}"; do
        char=$(printf "\\$(printf '%03o' "$value")")
        word+="$char"
    done
    echo "$word \n"
}

# Loop to print the word 5 times, decreasing ASCII values each time
for i in {1..7}; do
    print_word_from_ascii 
    # Decrease each ASCII value by 1
    for j in "${!ascii_values[@]}"; do
        ascii_values[j]=$((ascii_values[j]-1))
    done
done
for i in "${ascii_values[@]}"; do
        echo "$i"
done
```

instead of 5 times I tried running the loop 7 times, and I got the answer.
dont mind the final for loop, thats just something I made for debugging.

the output is:
```
fhtzuqjtkgt}js \n
egsytpisjfs|ir \n
dfrxsohrier{hq \n
ceqwrngqhdqzgp \n
bdpvqmfpgcpyfo \n
acoupleofboxen \n
`bntokdneanwdm \n
95
97
109
115
110
106
99
109
100
96
109
118
99
108
```

and in the 6th entry, we see 'acoupleofboxen', which is our flag.

`flag: leveleffect{acoupleofboxen}`
