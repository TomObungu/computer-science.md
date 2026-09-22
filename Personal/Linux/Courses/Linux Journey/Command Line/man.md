Man bages are the built in documentation
```bash
man grep
```

You can use the page sections like this
```bash
:~$ man 1 grep
tom@tom-LOQ-15ARP9:~$ man 2 grep
No manual entry for grep in section 2
tom@tom-LOQ-15ARP9:~$ man 3 grep
No manual entry for grep in section 3

```

- `1`: User commands.
- `2`: System calls.
- `3`: Library functions.
- `5`: File formats.
- `8`: System administration commands.

- `/` and type a search term to search forward.
- Press `n` to jump to the next match.
- Press `N` to jump to the previous match.
- Press `q` to quit.