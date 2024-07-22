# The trees speak hexadecimal

As a result of their investigation, the Incident Response team has identified 10 malicious files and provided us the "bad" hashes in iocs.txt.

They have also collected various file hashes across 20 different hosts on our network. These are stored in text files where each host has its own file containing 40 hashes, all bundled up in collections.zip. The bad hashes are likely present in some of the collections.

Your objective is to identify the number of occurrences of each bad hash across the host collection files. The flag is the sum of the occurrences of all bad hashes.

Advanced 
300 points

The first thing I did was combine all the hashes into a single file using the command:
`cat host*.txt > allhashes.txt`

now that we have all the hashes in a single file, we can use python to store the iocs in a list and see how many of them occur in file containing all the hashes.

heres the script I wrote:

```
iocs = open("iocs.txt").read().split() 
bad_hashes = 0
with open("allhashes.txt") as file:
    hashes = file.read().split()
    for i in hashes:
        if i in iocs:
            bad_hashes+=1
print(bad_hashes)
```

pretty simple script, read the iocs, store them in a list, traverse the allhashes.txt and check if the hash is in the ioc list, if it is we increment count.
print the final count.

running the script gives us the answer which is 16.

`flag: leveleffect{16}`
