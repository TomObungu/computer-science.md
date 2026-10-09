- All words containing the letter Q, capitalised. 
```shell
> grep "Q" /usr/share/dict/words
```
Output:
BB==🔴Q==
Big==🔴Q==uery
Big==🔴Q==uery'

- All words starting with the letter R, in either upper or lower-case. _(
```shell
grep -i '^R' /usr/share/dict/words 
```

Output : 
==🔴R==yder's
==🔴R==yukyu
==🔴R==yukyu's

- All words ending in j.
```shell
grep 'j$' /usr/share/dict/words 
```

Output:
Maj
adj
con

- The number of words containing the letter Q, ignoring case (e.g. capitalised or not). Remember 
```shell
grep -i "Q" /usr/share/dict/words | wc -l
```

- The first five words containing the letter sequence 'cl'
```shell
grep "^cl" /usr/share/dict/words | head -n 5
```

- All words containing the sequence "kp", but not "ckp"
```shell
grep [^c]kp /usr/share/dict/words
```

- The last 15 words of exactly two letters.
```shell
grep ^..$ /usr/share/dict/words | tail -n 15
```

