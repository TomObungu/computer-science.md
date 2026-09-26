Flags are special arguments that modify how the command works. Short ones have one 

Running `man -k` or apropos to search for the manual things. 

You can also use `man man` to find the manual for the manual. 

See `man intro` for beginner stuff, 

The will try and stick to POSIX with the lab machines the standard. 

# User group and 

# OpenSSH

The SSH protocol lets you login and run commands on remote computers. It runs on **port 22.** 

OpenSSH is the most common implementation of the protocol. It was developed alongside the OpenBSD subsystems.

For example running the ssh command would look like this:
```shell
ssh evelyn@imac

ssh -X evelyn@imac firefox
```

The default package manager for Debian Linux is apt. Other package mangers such as RPM for Red hat 

To install `.deb` files you can use
`sudo apt install
`dpkg -i`
`sudo aptitude

To copy files remotely you can use
```shell
man sftp 
```
or
```shell
man scp
```

The bash for the whole previous command typed is:
```
sudo !!
```

The first time you try to use `ssh`,  you will recieve a warning like this:
```
The authenticity of host 'sdf.org (205.166.94.16)'
can't be established.
ED25519 key fingerprint is:
SHA256: Zjwb07AU8hrHJExYrmZS2LqGZ7WfdoELfMrF65W92PYA
This key is not known by another other name.
Are you sure you want to continue connecting.
```

If you have somone with physical access to the machine, they check the authenticity of the key using this command:
```shell
ssh-keyscan -q -t ed25519 localhost
```

## Why check the key
Most of the time, checking the key is redundant, however there might be the cases of a man in the middle attack.

For example a **user A** may trick user B into connecting to **their** machine instead of the **actual** machine. **User A** may convice **user B** that the connection is authentic by resending data to the **actual** machine and delivering responses back to **user A.** However, user B could recording and saving all the of the data being sent from **user A.** **User B** could also potentially tweak data being sent from **User A.**

![[Pasted image 20260926181627.png]]

User A can prevent this man in the middle attack by checking the authenticity of the key fingerprint with the known actual machine key.

### arp spoofing
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

# Service Managers
## Systemd
Systemmd is a service manager for Linux. The most 'normal' or commonly used one is system. You can run the command `systemctl status` to see the status of your linux server.
```shell
systemctl
```
You can also use `journalctl` to see the logs of your computer/system to monitor activity within your system server
```shell
journalctl -n 3
```
The `-n` suffix allows your specify the amount of log information you want to see. 
The  `systemctl status sshd`  allows you to monitor the status of your `sshd` unit service once it has been turned on. 

However in order to actually turn on the sshd service, you need to run the command:
```shell
systemctl start sshd
```
In order to cause the `sshd` service to run at boot you use the `enable` tag. Furthermore you can use the `--now` tag to simulatanously turn it on and enable it at boot
```shell
systemctl enable sshd
systemctl enable --now sshd
```
`
Once your `sshd` service has started, you can run
```shell
systemctl status sshd
```

# Question
A file is owned by brian (group users), and has permissions 0754. Can nigel (group) read it and can he edit. 