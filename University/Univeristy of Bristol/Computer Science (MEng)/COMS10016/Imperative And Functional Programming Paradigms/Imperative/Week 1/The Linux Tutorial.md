# The `ls` command and security
You can get given more information from the `ls` command by using an option with the `ls -l` command.
![[Pasted image 20260928063333.png]]

The final three characters shows the permissions allowed to anyone who has a UserID on this linux system. It is reffered to either "world" or "other". 

# Changing the security permissions
## The `chmod` command
It is possible to change security using the chmod command like this
```shell
chmod 700 file
chmod ugo+rw file
chmod ugo-rwx file
chmod 727 file
```

Each digit within the 3 digit tags are in octal notation and each digit responds to either a user, group or 'other'.

# Other useful commands
Use `du -h` to see how much space is being sued
Use `df -h` how much different filesystems and partitions
`scp -p -r [path to folder to copy/*] [username]@[other machine]:[pathto dir on other machine]` Use secure copy to a file to a ssh.

```
cat /proc/meminfo | more //RAM
```

```
cat /proc/cpuinfo | more //CPU
```

# Compressing/extracting stuff using `tar`
https://linuxize.com/post/how-to-create-and-extract-archives-using-the-tar-command-in-linux/
The `tar` command is as follows 
```shell
tar 
[OPERATION_AND_OPTIONS] [ARCHIVE_NAME] [FILE_NAME(s)]
```

The following operations is allowed and required. The most frequently used operations are:

`--create (-c)`
`--extract (-x)`
`--list (-l)`

The most frequently used options are
`--verbose (-v)` shows the files being processed by the tar cosmmand
`--file=archive-name (-f archive-name)` specifies the archive filename.

You can use the `j` tag to create a `bzip2` arcjove and the `z` tag to create a `gzip` archive