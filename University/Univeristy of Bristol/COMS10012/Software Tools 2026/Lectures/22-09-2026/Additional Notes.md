# OpenSSH
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

# The Linux Filesystem
Running the `tree -L` command on the root folder `/` allows inspection of the filesystem of a linux machine. 
![[Pasted image 20260926182800.png]]

Binary programs go in `bin/`. Bootloader stuff goes in `boot/`. Device files such as raw disks are in `dev/`.  Configuration files go in `etc/`. Programs for the root user go in `sbin/`. Temporary files go in `/tmp`. Files being served go in `/srv` or var/

`run/` is for runtime things. 

`/usr` contains the same again but its stuff that the OS thinks you need.  

`/usr/local` contains the same local things needed but for stuff that has been locally installed on the specific machine. 

`/opt` may also contain the same.

The filesystem configuarions will be different for each system. It will be different on MAC, WSL and openBSD.

# Users, groups 
Almost everything is treated as file which can be read, written or executed. Every file is owned by exactly one user and one group. Running the `ls -l` allows seeing the groups and users of a listed files. 