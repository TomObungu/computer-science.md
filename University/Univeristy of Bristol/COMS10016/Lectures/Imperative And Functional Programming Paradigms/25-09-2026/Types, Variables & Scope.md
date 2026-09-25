# Platforms and Types
A platform is a combination of processor, operating system device drivers, libraries, compilers, runtime systems and settings of all of those - anything which affects programs. Usually, we abbreviate talking about Linux, MacOS Windows and mobile platforms such as Android. 

A data type is a class of data item, as defined by the variables it can take and the operations that can be performed on it. 

However in imperative languages such as C, the properties of types may differ on different platforms. For example in one machine architecure, an `int` type may be 32 bits however in some archtectures may be 16 bits. 

## Common Arithmetic Types in C
Below is a table for the most common ranges for arithmetic types in C:

| Type          | Usual Size | Usual Range                 | Specifier |
| ------------- | ---------- | --------------------------- | --------- |
| `signed char` | 8 bits     | $[-128, 127]$               | `%hhi`    |
| `int`         | 16 bit     | $[-2^{31}, 2^{31}-1]$       | `%d`      |
| `long`        | 64 bit     | $[-2^{63}, 2^{63}-1]$       | `%li`     |
| `double`      | 64 bit     | $\text{Based on precision}$ | `%lf`     |
