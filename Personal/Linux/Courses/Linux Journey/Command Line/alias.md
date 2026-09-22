You can add an alias to command like this. You must use the `''` 
```bash
alias destroyjpgs='find ./Downloads-backup/ -type f -name "*.jpg" -exec rm -rfv {} \;'

```

aliases are stored in `~/.bashrc`

You can unlias like this
```
unalias destroyjpgs
```

You can use `type` to see what will run when a command is entered