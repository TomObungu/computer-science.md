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

For C, they are found in `#include <assert.h>` and use the `assert()` macro. Assertions can be entirely removed by the compiler with the `-DNDEBUG=1` option. The avoids assertion failures crashing your production code. 
# Unit Testing
Unit tests run your code against a set of inputs, comparing the actual result of running the code to what you declare the result should be. 

If any test fails, your current version of the code is broken, you need to fix it so the tests pass. If code was passing tests before work started and isn't working after you finished work, you have introduced a regression.

## Unity
Unity is an example of a unit testing framework for C projects. 
```C
#include "unity.h"
void test_add(void) {
    TEST_ASSERT_EQUAL(4, add(2, 2));
}
int main(void) {
    UNITY_BEGIN();
    RUN_TEST(test_add);
    return UNITY_END();
}
```

# When to Write Tests
A typical development process goes as writing code, writing tests for code and occasionally running the tests. 

However this is a bad Idea. Instead you should use a test-driven development. Test driven development involves:
1. Write tests for the behaviour of what you want
2. Write code that passes the tests

# Test Driven Development (TDD)
The TDD workflow follows what is known as the 'RED-GREEN-REFACTOR' model. 

- Red - Write a single test for what the output should be and ensure it fails
- Green - Introduce the simplest change that will cause your code to pass the tests
- Refactor - Improve the code to improve its structure and readability while keeping the tests green. 

Adopting new software engineering practices is often more about changing mindset than learning a new tool. Discipline is the bridge between goals and accomplishment. Embrace discipline of testing first. 

# Property Testing
A popular property testing framework is called QuickCheck
```C
#include "quickcheck4c.h"

QCC_TestStatus mulCommutativity(QCC_GenValue **vals, int len, QCC_Stamp **stamp) {
  int a = *QCC_getValue(vals, 0, int*);
  int b = *QCC_getValue(vals, 1, int*);

  return a*b == b*a;
}

int main(int argc, char **argv) {
  QCC_init(0);
  QCC_testForAll(100, 1000, mulCommutativity, 2, QCC_genInt, QCC_genInt);
}
```

# Fuzzing
Random input generation is an  excellent way to discover bugs in code. Fuzzers are programs that are meant to break other programs. They generate demented input to stress-test the designers' assumptions. 

# Evading the Fuzz
To protect your code against deranged input generator, you need to be able to prove that this cannot go wrong. You could use formal methods such as mathematical proofs. You could also use formal verification, it is possible to prove that desirable properties of your program will always hold. 

Lean is a prgarmming langauge designed to enable you to write formally verified code. 