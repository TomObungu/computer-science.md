You can copy several files using the `cp` command like this
```bash 
cp report.txt notes.txt /home/pete/Documents
```

Use the `-R/-r` tag to copy all the items recursively

Use the `-i` tag to warn of overwrite

Use the `-f` to force overwriting of the file

Use the `-p` to preserve all the files attributes and metadata

Use `-n` to not overwite existing files

Use `-a` to copy as archive mode. Can specify the 

You can use wildcares such as `*`, `?` and `[]` to move types of files e.g
```bash
cp *.jpg /home/pete/Pitcures
```