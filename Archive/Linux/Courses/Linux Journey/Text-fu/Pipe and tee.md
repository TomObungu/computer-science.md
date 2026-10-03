The pipe `|` operator takes the standard output of the command on its left and uses it as the standard  input for the command on the right.

Note it only runs the output of the command. It is not the same as running multiple commands

For example the command 
```bash
mkdir -p this/is/for/test/puposes/only | cd 

```
will not work as intended due to the `mkdir` command not sending any output

Whereas a command like this
```bash
ls -la ./Downloads | less
```
Will simply open the entire output for the 

The `tee` command save the output of a file to a text file 

```bash
ls -la ./Downloads | tee my_downloads.txt

```

This command outputs the result of `ls` whilst also saving that output in a file called `my_downloads.txt`