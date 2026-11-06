# Testing as a pre-commit hook
It is possible to create a directory within the folder called `.git/hooks/pre-commit` and run the unit tests. This is possible using bash scripts:
```bash
#!/bin/sh

gcc -I /usr/local/include/unity -o tests test.c -l unity 
./tests 
```
After creating the pre-commit hook, ensure to change the permissions of the file 
```bash
chmod +x .git/hooks/pre-commit
```
Now trying to commit the tests will throw an error like this:
```shell
test.c:9:test_add:FAIL: Expected 4 Was 0
test.c:9:test_add:FAIL: Expected 4 Was 0

-----------------------
2 Tests 2 Failures 0 Ignored 
FAIL
```
If you want to commit without the tests passing you can do `git commit --no-verify`. 

# Workflows
Create a workflow like 
```shell
mkdir -p .github/workflows
```
It is possible to run a `test.yml`. This work flow works by getting the repository for the unity library, and then using athe `-I` tag to include the unity source code in `-I unity/src/` it then compiles your code as `main/test.c` and then unity testing library `unity/src/unity.c -o tests`

```yml
name: Compile and Test Under Unity

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest
    steps:

      - name: Checkout your code
        uses: actions/checkout@v7
        with:
          path: main

      - name: Checkout Unity
        uses: actions/checkout@v7
        with: 
          repository: ThrowTheSwitch/Unity
          path: unity

      - name: Set up GCC
        run: sudo apt-get install -y gcc

      - name: Compile tests 
        run: gcc -I unity/src/ main/test.c unity/src/unity.c -o tests

      - name: Run tests
        run: ./tests
```

The workflow runs on the GitHub VM and will test the checks before pushing the code. 