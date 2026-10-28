# Pipes
The `|` takes the output of whatever is on the left hand side and pipes it in as input to the right hand side. 

The `>` operator takes the output from the left and creates a new files in the path on the right. 
The `>` operator takes the contents of the path on the right and feeds it into the output of the command of the left

# What happens when a  program loads?
Linux supports many different program formats. The most common are `ELF` files. `ELF` files are compiled binaries and shellscripts.

When an ELF file executed it is passed into a dynamic linker to have the appropiate libraries loaded. In Windows dynamically linked files have the file extension `.dll` whereas in Linux and other UNIX-like systems they have the file extension `.so`.

However if the file is a text and starts with starts with `#!` then something special happens - a shell script is formed. Shell scripts can be interpreted using various langauges. On most UNIX-like systems tshe `bash` language is used. However it is possible to set other languages such as `python-3` to interpret the shell script. 

In computer-science-lex, the `#` is pronounced as 's' as you would in saying "shout" whereas the `!` is prounounced as "bang".

Below is a following example of a shell script

```shell
#! /usr/bin/env bash
# Everything within a shell script is be sent line by line (interpreted)
```
