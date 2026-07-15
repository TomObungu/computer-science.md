The paste command output the contents of text in a specific manner.

```bash
paste -s sample2.txt
The	Quick	Brown	Fox
tom@tom-LOQ-15ARP9:~$ paste -d ' ' -s sample2.txt
The Quick Brown Fox

```

The delimiter is `TAB` by default. Using `-d` followed by the delimiter gives the text in a specific manner
