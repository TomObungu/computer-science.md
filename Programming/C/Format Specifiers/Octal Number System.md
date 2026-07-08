https://www.youtube.com/watch?v=MGu-P4OOnh0

Octal number system is like hex but instead of using `8 4 2 1` it only uses `4 2 1`. 

Hexadecimal is a base $16$ system whereas Octal is a base `8` system. This is because octal can only be represented 8 digits of `0-7` and hex represented as `0-9` and `A-F`

![[Pasted image 20260708090456.png]]

Thus the binary number `110 111` can be represented in octal like this

| 1   | 1   | 0   | \|  | 1   | 1   | 1   |
| --- | --- | --- | --- | --- | --- | --- |
| 4   | 2   | 1   | \|  | 4   | 2   | 1   |
| 6   |     |     | \|  | 7   |     |     |

Thus the base 2 binary number `110111` has value `67` in octal. 

In general we represent octal numbers like this `Oo67`

To convert from octal to decimal you take each individual digit and multiply it by $8^{x}$ where $x$ is the index of the digit 

E.g 
$627_{8} = 6(8^{2}) +2(8^{1}) + 7(8^{0}) = 1580_8$

To convert from decimal to octal, you can convert to binary then to octal 
