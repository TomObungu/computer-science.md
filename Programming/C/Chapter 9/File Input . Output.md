# 9.1 The FILE* Data Type

When dealing with I/O in C, we do so through the `FILE*` data type

Of the `FILE*` data types there are 'streams' where data can travel. Here are the various stream in which data can travel 

| `FILE*`  |                                                                          |
| -------- | ------------------------------------------------------------------------ |
| `stdin`  | The standard input stream. This generally from the keybaord              |
| `stdout` | The standard output stream.  Generally the screen or terminal by default |
| `stderr` | The standard error stream. Generally the screen or terminal by default.  |


For example you can use `fprintf` and specify the stream as ``