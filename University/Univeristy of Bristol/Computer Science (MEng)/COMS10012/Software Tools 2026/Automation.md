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