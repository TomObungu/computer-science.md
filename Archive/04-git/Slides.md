# `git status`
You can check the current status of the directory relative to the repository's memory using `git status`

# `git log`
After a commit you can check `git status` again and you can use `git log` to show the repositroy history, including, the commit IDs, authors and time and commit messages

# `git diff`
You can use the `git diff` command to compare the latest version in the repository to our the local directory changes, to see what has been done. 
You can compare against historic file versions like this
```
git diff [commitID] hello.txt
```

# `git restore`
You can use `git restore` to restore a current file to the repository with `git restore`

You can restore the to a specific commit ID like this
```
git restore -s [commitID] hello.tx
```

Remember you can get the commit ID of a branch using `git log`

# `git checkout`
Loads the contents of a commit into a repository. `git checkout main/master` goes back to the current directory contents

# `git remote`
To connect your existing repository to a new remote, use `git remote add origin [remote URL]`