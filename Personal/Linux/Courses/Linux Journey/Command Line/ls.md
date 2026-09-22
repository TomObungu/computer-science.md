You can do the `ls` command with `-a` to list hidden directories. 

You can do the `ls` command with `-l` for long format to show the  file permissions, number of links, owner, group, size, modification time and name.

You can also add `-h` for human-readable output. 

 The `-r` option lists files and directories in reverse order 

The `-t` can sort by modification time 

The `-S` can sort by file size.

The `-d` can list the directory itself instead of its contents

You can combine command flags like this
```bash
ls -lh
ls -la
ls -ltr
```

dotfiles are hidden by default and often store configuration such as `.bashrc`

It is possible to find group conditions using parenthesis and the Boolean -o 'OR' and -a 'AND' operators. 

When combining parenthesis you need them to control evaluation order. Since parenthesis are special characters, they must be escaped with backslashes or quoted. 

For example, the command below allows the use of multiple file 

```shell
find . -type f \(-name "*.mp4" -o -name "*.mov" \) -exec mv {} Videos \;
```