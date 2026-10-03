By default when you use `echo`, the text is redirected to `stdout`. This is usually your terminal screen or console.

Running
```bash
echo "Hello World!"
```
prints to the terminal 

You can use `>` to redirect the output say to a file. For example we can create a file called `myfile.txt` and then write to it `This is my file`. 
```bash
tom@tom-LOQ-15ARP9:~$ echo "This is my file" > myfile.txt
tom@tom-LOQ-15ARP9:~$ cat myfile.txt
This is my file
```

If you don't want to erase the contents of a file when adding to it, use the `>>` operator

This also makes sense why the `>>` operator is used in `C++` code like this
```C++
cout >> "Hello World!"
```

You are appending to the `stdout`, the text "Hello World!"

Below is an example 

```bash
echo "and this is some text added to it" >> myfile.txt 
tom@tom-LOQ-15ARP9:~$ cat myfile.txt 
This is my file
and this is some text added to it

```