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

# mv

The `mv` command can also be used with wildcard

Can move multiple files at once like this
```bash
$ mv file_1 file_2 somedirectory/
```

# mkdir

You can create nested directories using the `-p` command

You can set permissions using `-m` 


You can move a file with a backup like this
```bash
$ mv -b file1 directory_with_file1
```

You print out what a file is doing using the `-v` tag
```bash
$ mv -v file1 file2 somedirectory/
```
# find

