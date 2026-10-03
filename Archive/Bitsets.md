## Creating bitset from binary string
https://stackoverflow.com/questions/17129365/how-do-i-create-a-bitset-from-binary-string
First store the string:
```C++
string bit_string = "110010"
```
Then initial size the bitset with the size of the bitset being the size of the string:
```C++
bitset<8> b(bit_string)
```

Can print out the bitset as a string again using `to_string`:
```C++
cout << b.to_string() << '\n';
```
