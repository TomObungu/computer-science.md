
You can find file types like this
```bash
find ./Downloads -name "*.jpg"

```

The `-name` operator works by finding by filename

You could also do `-iname` to ignore case. 

You can find directories using the `type` and `-d`. For regular files do `f`

## Running Actions on results
 You can use the `-exec`  tag to run actions on each file that is found

For example here is a command that  recursively finds all the `.png` files inside a folder called `Downloads-backup`, deletes them whilst printing out what's been deleted. 

```bash
find ./Downloads-backup/ -type f -name "*.png" -exec rm -rfv {} \;
```

the `{}` placeholder is regex to show that the command is replaced by each matching path. 

The `\;` marks the end of the command. 

You can also use the `-print` command to print out the files types. This is like `ls` but with wildcards

```bash
find -type f -name ".jpg" -print 

```
# Size and time 
Below is a command to find a file greater than 10 megabytes in the home directory 
```bash
find ~ -type f -size +10M
```

Below is a command that finds a file that has been edited within the last 9 days
```bash
find ./Downloads -type f -mtime -9
-mtime -
```