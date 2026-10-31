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

### ARP spoofing
https://en.wikipedia.org/wiki/ARP_spoofing
ARP spoofing is is technique used by a man in the middle attacker. It involves associatiating the attacker's MAC address with the target IP such that any data being sent to the target IP is sent to the attacker instead. 

The attack involves the user sending spoofed addresses onto a network. A spoofed address is an address that falsly identifies as another address by falsifying data. 

# The Linux Filesystem
Running the `tree -L` command on the root folder `/` allows inspection of the filesystem of a linux machine. 
![[Pasted image 20260926182800.png]]

Binary programs go in `bin/`. Bootloader stuff goes in `boot/`. Device files such as raw disks are in `dev/`.  Configuration files go in `etc/`. Programs for the root user go in `sbin/`. Temporary files go in `/tmp`. Files being served go in `/srv` or var/

`run/` is for runtime things. 

`/usr` contains the same again but its stuff that the OS thinks you need.  

`/usr/local` contains the same local things needed but for stuff that has been locally installed on the specific machine. 

`/opt` may also contain the same.

The filesystem configuarions will be different for each system. It will be different on MAC, WSL and openBSD.

# Users, groups and the UNIX DAC
In linux and most UNIX systems, the concept of users means each user has control over the minimum things they need to work. 

If you would want to do something that could mess up the system for other users like installing/removing/changing software. Only the root user is allowed.

The command Sudo means `Super User DO`. This allows you to temporarily become the root user. 

UNIX systems traditionally control access to everything through files. Almost everything is treated as a file which can be read, written and executed. (RWX)

**Every file is owned by exactly one user and on group.** 

When using `ls -l`, it is possible to show the group and user for each file
For example, the file `.deb` file below is owned by user `tom`and group `tom`
```shell
-rw-rw-r--  1 tom tom 117341968 Sep 26 11:56 linux_f5vpn.x86_64.deb

```

Inspecting the file output from running `ls -` some more we can see that:
$$
\underbrace{ - }_{ directory }\underbrace{ rw- }_{ user }\underbrace{ rw- }_{ group }\underbrace{ r-- }_{ other }  1 \ tom \ tom  \ 117341968 \ Sep 26 11:56  \ linux_f5vpn.x86_64.deb
$$
We can see the RWX permission for each user, group or other for the file.

The RWX system can be represented as binary and octal 

For example the file can be read to written to and executed can be written as 
```
RWX = 111_2 = 7_8
R-x = 101_2 = 5_8
--- = 000_2 = 0_8
```

The chmod command is used to change permissions. 
For example running
```
 chmod 666 linux_f5vpn.x86_64.deb 
```
Changes the permission for the group, user and other from:
```shell
-rw-rw-rw-  1 tom tom 117341968 Sep 26 11:56 linux_f5vpn.x86_64.deb
```
To:
```shell
--wx-wx-wx  1 tom tom 117341968 Sep 26 11:56 linux_f5vpn.x86_64.deb
```

Systemd is a service manager for Linux.  It can show the state of your server state machine. The command to see the state of your server is 
```
systemctl status
```

The command will also show the system logs. In this case the prefix `-n 3` will show the last 3 logs.
```
journalctl -n 3
```

The directory of what users and groups exist and who belongs to what is kept in `/etc/passwd` and `/etc/group`. User passwords are somtimes kept in `/etc/shadow`.

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

# Things to do on the computer:
![[Pasted image 20260926191725.png]]
# Question
A file is owned by brian (group users), and has permissions 0754. Can nigel (group) read it and can he edit. 
![[Pasted image 20260926191829.png]]
Remember that 
$$
\underbrace{ 0 }_{ \text{directory} }\underbrace{ 7 }_{ user }\underbrace{ 5 }_{ group }\underbrace{ 4 }_{ other }
$$
Since nigel is part of the same group, he has permission 5. Now the permission is in octal. Converting this to binary gives 
```shell
5_8 = 101_2
```
Comparing this with the RWX strcuture we are given:
```
R W X
1 0 1
```
Meaning nigel has permission to read the file, no permission to write (edit) to the file and permission to execute the file. 