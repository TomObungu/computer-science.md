To see environment variables you use the`env` command.  Various environment variables include `$HOME` `$USER`

One of the most important environment variables is the `PATH` variable

Running `echo $PATH` returns a colon-separated list of directories. These directories are the list of directories the system searches through when a command is run. 

Adding executable paths to the `$PATH` allows running of the executable from anywhere. 

# Setting an environment variable

To add for the current terminal session only do:
```
export TEST=test`.
```
This makes a variable `TEST` and sets the value equal to `test`.

## Making the environment variable persistent across all sessions

To make the environment variables persist across all sessions. You must add `export` to the end of the `~/.bashrc` file. 

To apply changes to the `~/.bashrc` file run:
`source ~/.bashrc

`