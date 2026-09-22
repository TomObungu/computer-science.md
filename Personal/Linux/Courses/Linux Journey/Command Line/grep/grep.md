Instead of manually digging through countless lines of text to find a specific string or configuration, you can simply use `grep` to do the heavy lifting

At its core, grep searches for patterns within a file. 

For example this grep command allows a recursive search of every subdirectory containining the string `SDL_Window`
```bash
grep -irn "SDL_Window" ./*
```

The `i` is case insensitive, the `r` is recursive and `n` is the word numbers