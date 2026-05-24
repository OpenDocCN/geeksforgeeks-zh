# C 库中的 snprintf()

> 原文:[https://www.geeksforgeeks.org/snprintf-c-library/](https://www.geeksforgeeks.org/snprintf-c-library/)

snprintf()函数格式化一系列字符和值并将其存储在数组缓冲区中。函数的作用是:增加 n 个参数，表示要写入缓冲区的最大字符数(包括空字符的末尾)。在 **< stdio.h >** 头文件中定义。

snprintf()函数用于将 printf()函数的输出重定向到缓冲区。

snprintf()还返回写入缓冲区的字符数，类似于 printf 语句，该语句返回在 stdout 中打印的字符数。

**语法:**

```cpp
int snprintf(char *str, size_t size, const char *format, ...);

*str : is a buffer.
size : is the maximum number of bytes
(characters) that will be written to the buffer.
format : C string that contains a format
string that follows the same specifications as format in printf
... : the optional ( …) arguments 
are just the string formats like (“%d”, myint) as seen in printf.
```

## C

```cpp
// C program to demonstrate snprintf()
#include <stdio.h>

int main()
{
    char buffer[50];
    char* s = "geeksforgeeks";

    // Counting the character and storing
    // in buffer using snprintf
    int j = snprintf(buffer, 6, "%s\n", s);

    // Print the string stored in buffer and
    // character count
    printf("string:\n%s\ncharacter count = %d\n",
                                     buffer, j);

    return 0;
}
```

输出:

```cpp
string:
geeks
character count = 14
```