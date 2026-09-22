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
