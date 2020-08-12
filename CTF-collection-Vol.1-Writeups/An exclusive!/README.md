## An exclusive!
The main idea finding the flag is to know XOR operation.

#### Step-1:
We are given 2 strings of different formats.

```
S1: 44585d6b2368737c65252166234f20626d  
S2: 1010101010101010101010101010101010
```

#### Step-2:
I wrote a `Flag.py` script to get the flag:

```
s1 = "44585d6b2368737c65252166234f20626d"
s2 = "1010101010101010101010101010101010"

a = hex(int(s1, 16) ^ int(s2, 16))[2:]
print(bytes.fromhex(a).decode('utf-8'))
```

After running the script, `python3 Flag.py`, we get our flag.

#### Step-3:
Finally the flag becomes:
`THM{3xclu51v3_0r}`