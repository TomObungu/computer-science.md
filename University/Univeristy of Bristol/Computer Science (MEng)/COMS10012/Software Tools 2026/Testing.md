Testing involves making assertions, unit testing, test-driven development, property testing, fuzzing and formal verification. 

# Making assertions
Assertions are mechanisms for making logical statements about variables in your program. You insert them to express what should be true about values of variables. 
```C
static void add_mime_mapping(const char *extension, const char *mimetype) {
    size_t i;
    assert(strlen(extension) > 0);
    assert(strlen(mimetype) > 0);
```
Assertions are good for testing assumptions while writing code but they are embedded within your code and thus are hard to review. 

For C, they are found in `#include <assert.h>` and use the `assert()` macro. 
# Unit Testing