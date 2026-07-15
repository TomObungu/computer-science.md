Both `stdout` and `stderr` write to the terminal screen directly. 

To select whether to write to `stdin` `stdout` or `stdout` you can use the file descriptors. These are
`0`: stdin
`1`:stdin 
`2`:stderror

You can use the file descriptor `2` follow by `>` this can send any error messages to a specified `stderr` file