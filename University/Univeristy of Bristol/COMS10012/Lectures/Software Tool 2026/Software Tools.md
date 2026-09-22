Flags are special arguments that modify how the command works. Short ones have one 

Running `man -k` or apropos to search for the manual things. 

See `man intro` for beginner stuff, 

The will try and stick to POSIX with the lab machines the standard. 

# OpenSSH

The SSH protocol lets you login and run commands on remote computers. It runs on port 22. 

OpenSSH is the most common implementation of the protocol. It was developed alongside the OpenBSD subsystems.

For example running the ssh command would look like this:
```shell
ssh evelyn@imac

ssh -X evelyn@imac firefox
```


The default package manager for Debian Linux is apt. Other package mangers such as RPM for Red hat 


The bash for the whole previous command typed is:
```
sudo !!
```


# Users, groups and the UNIX DAC
In linux and most UNIX systems, the concept of users means each user has control over the minimum things they need to work. 

If you would want to do something that could mess up the system for other users like installing/removing/changing software. Only the root user is allowed.

The command Sudo means `Super User DO`. This allows you to temporarily become the root user. 

UNIX systems traditionally control access to everything through files. Almost everything is treated as a file which can be read, written and executed. (RWX)

Every file is owned by exactly one user and on group. 

The RWX system can be represented as binary and octal 

For example the file can be read to written to and executed can be written as 
```
RWX = 111_2 = 7_8
R-x = 101_2 = 5_8
--- = 000_2 = 0_8
```

The chmod command is used to change permissions. 

Systemd is a service manager for Linux.  It can show the state of your server state machine. The command to see the state of your server is 
```
systemctl status
```

The command will also show the system logs. In this case the prefix `-n 3` will show the last 3 logs.
```
journalctl -n 3
```