Inside VSCode, there is this problem that involves using debugging. Sometimes when debugging C++ files after pressing the debug button, stepping into lines of code containing keywords of the `C++` standard library may trigger a step into the actual source file of the library. For example if your line of code contains code using `std::vector` such as the `.push_back()` function, the debugger may actual step into the `vector.h` header file and show all of the cryptic standard library implementation code. 

A quick search to fix says that putting this line of code below inside the `launch.json` configuration usually fixes it. 
```json
{
"configurations": [
{
	"name": 
	...
	"JustMyCode" : true
	...
	}
]
}
```

However sometimes this may throw an error like "This is not allowed here". In my case for the C++ example, in my Linux system I was using the `gdb` which comes with `gcc/g++`.  

Creating a file called `.gdbinnit` inside the home folder of my system and putting these lines of code will tell the `gdb` debugger to ignore the standard library files when debugging your code

```
skip -gfi /usr/include/c++/*/*/*
skip -gfi /usr/include/c++/*/*
skip -gfi /usr/include/c++/*
```