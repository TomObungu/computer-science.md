# Recap
Say if you want to take a project to a new direction, it's often good to do it in a branch. To create a new branch use.
```
git branch newidea
```
To switch to it use:
```
git switch newidea
```

You can merge the changes to your branch using `git merge`

If the `newidea` branch still exists after the merge, but doesn't contain unmerged changes. If you don't want to use it again use `-d`
```
git branch -d newidea
```
Use the `-D` tag to delete the branch without merging 
```
git branch -D badidea
```
# Merge Conflicts
