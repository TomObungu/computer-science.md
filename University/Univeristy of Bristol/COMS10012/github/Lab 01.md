# Secure Shell (SSH)
SSH is a protocal to allow you to remotely connect to another computer, such as a lab machine. Almost everyone who uses SSH uses the free openSSH implementation. 

`ssh` is the client, which runs on the machine to connect to another machine.

`sshd` is the server, or daemon in UNIX-speak. It runs on the background on the machine you want to connect. 

SSH uses port 22 by default. 

You can test the status of your connectivity as a client using 
```
ssh localhost
```

If it asks for a password, then the ssh client is working. 