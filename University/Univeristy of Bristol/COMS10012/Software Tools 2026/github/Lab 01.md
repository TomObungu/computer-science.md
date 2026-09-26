# Secure Shell (SSH)
SSH is a protocal to allow you to remotely connect to another computer, such as a lab machine. Almost everyone who uses SSH uses the free openSSH implementation. 

`ssh` is the client, which runs on the machine to connect to another machine.

`sshd` is the server, or daemon in UNIX-speak. It runs on the background on the machine you want to connect. 

SSH uses port 22 by default. 

You can test the status of your connectivity as a client using 
```
ssh localhost
```

If it asks for a password, then the ssh client is working and a ssh server is running on your current machine. If it succeeds without a password, then the client is working and a ssh server is running on your machine and either you don't have a password or a key is setup. 

If an error is shown that ssh is not found, you don't have (Open)SSH installed .

# Connecting via ssh
You can use ssh to remotely connect to your instituions lab machines. Often time your institution will set up a network access portal and a domain that can be connected to. The command for connecting often follows.
```shell
ssh USERNAME@YOUR-INSTITUION-DOMAIN.COM
```
In my case, my instition required connected to portals vpn via web browser before forming the ssh.

You can then type `whoami` and `uname -a` to check who you are logged in as. You can then try `hostname` which prints the machine name
# Setting up ssh keys
