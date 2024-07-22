# Pefect match

Regex - love it or hate it, it's an invaluable skill to have as a defender.

The goal of this challenge is to extract all IPv4 addresses from the contents of the file input.txt . A starter script has been provided below and by download. All you need to do is insert a regex pattern to finish the job. You can submit your code in the code submission box.

Note: If you write your own script, you must read in the data from input.txt specifically as shown in the example.

Intermediate 
250 points 

now I suck at regex too...
lets just ask claude
heres the answer I got:
`\b(?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\b`

heres the explanation:
```
\b: Word boundary, ensures we're matching whole IP addresses, not parts of larger strings.
(?:...): Non-capturing group, used to group parts of a regex together.
(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?): This part matches a single octet (0-255):

25[0-5]: Matches 250-255
2[0-4][0-9]: Matches 200-249
[01]?[0-9][0-9]?: Matches 0-199


\.: Matches a literal dot.
{3}: Repeats the previous group (octet + dot) three times.
The pattern ends with another octet without a trailing dot.
\b: Another word boundary to end the match.
```
heres the final python script:

```
import re

PATTERN = re.compile(r'\b(?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\b')

def extract_ips(data):
    ips = PATTERN.findall(data)

    unique_ips = []
    [unique_ips.append(str(ip)) for ip in ips if ip not in unique_ips]

    return unique_ips

def main():
    with open("input.txt") as f:
        data = f.read()
        extracted_ips = extract_ips(data)

    for ip in extracted_ips:
        print(ip)

main()
```

