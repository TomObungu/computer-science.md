You can use `typedef` to rename existing types to another name. Can be useful long complicated types. This is more the case in C++ but the same applies to C. 

When dealing with typedefs and structs. You need to put the name of the struct to use the format 

```C
// original name
// |
// v
// |-----------|
typedef struct animal {
char *name;
int leg_count, speed;
} animal; // <-- new name
struct animal y; // This works
animal z; // This also works because "animal" is an alias
```

```C
struct animal y;
animal z;
```

If you use an anonymous struct. It wont work anymore:

```C
// Anonymous struct! It has no name!
// |
// v
// |----|
typedef struct {
char *name;
int leg_count, speed;
} animal; // <-- new name
//struct animal y; // ERROR: this no longer works--no such struct
```