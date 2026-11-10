Debugging tools involve `strace` for tracing system calls, `gdb` for command line debugging and `valgrind` for memory leaks. ]

# Strace
`strace` runs the command line until it exits. While the process is running, `strace` intercepts and displays system calls made by the process.
For example you can show the system calls when running the `ls` command.
```shell
strace ls
```
You can see what system calls with strace
```shell
strace -e open, openat ls
```
Use `-p` to attach `strace` to an already running process
```shell
ps aux | grep [process_name]
strace -p [pid]
```

# Valgrind
You can install the latest version of Valgrind using `wget` or `curl`
```shell
wget https://sourceware.org/pub/valgrind/valgrind-3.xx.x.tar.bz2
```
Run `tar -xvf valgrind-3.xx.x.tar.bz2` and in the directory, run `sudo make -j$(nproc)`
To use valgrind, compile some code and use the `valgrind --leak-check=` The code `badcode` contains a segfault
```shell
gcc -o badcode demo.c
valgrind --leak-check=yes ./badcode
```
That was usage of the `memcheck` module, other modules of Valgrind involve
- `callgrind`: Profiling code to find which instructions are being executed most often
- `hellgrind`: Similar, creates a call graph of relations between calls
- `massif`: Measure memory usage over time
# gdb
To use gdb, you must compile your code with `gcc` and ensure the `-g` tag is included in the compiling tags:
```shell
gcc -Wall -Wextra -Wpedantic -fsanitize=address -fsanitize=undefined -g3 -O0 -o badcode demo.c
```
You can pass a program into argument to `gdb` like 
```shell
gdb ./badcode
```
To view source in multiple formats run this command and press enter a few times.
```
(gdb) lay next
```
You can then run the debugger by running `(gdb) run` or `(gdb) r`.
You can set breakpoints using `break [function_name]`, you can see what functions using `info functions`. You can step in execution 