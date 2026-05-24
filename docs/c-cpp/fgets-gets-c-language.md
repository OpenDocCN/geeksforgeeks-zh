# 用 C 语言 fgets()和 get()

> 原文:[https://www.geeksforgeeks.org/fgets-gets-c-language/](https://www.geeksforgeeks.org/fgets-gets-c-language/)

为了读取带有空格的字符串值，我们可以在 C 编程语言中使用 get()或 fgets()。在这里，我们将看到 get()和 fgets()之间的区别。

**fgets()**

它从指定的流中读取一行，并将其存储到 str 指向的字符串中。当读取(n-1)个字符、读取换行符或到达文件结尾时(以先到者为准)，它停止。
**语法:**

```cpp
char *fgets(char *str, int n, FILE *stream)
str : Pointer to an array of chars where the string read is copied.
n : Maximum number of characters to be copied into str 
(including the terminating null-character).
*stream : Pointer to a FILE object that identifies an input stream.
stdin can be used as argument to read from the standard input.

returns : the function returns str

```

*   它遵循一些参数，如最大长度、缓冲区、输入设备参考。
*   使用**是安全的**，因为它检查数组边界。
*   它会一直读取，直到遇到新的行字符或字符数组的最大限制。

例如:假设最大字符数为 15，输入长度大于 15，但 fgets()仍然只能读取 15 个字符并打印出来。

```cpp
// C program to illustrate
// fgets()
#include <stdio.h>
#define MAX 15
int main()
{
    char buf[MAX];
    fgets(buf, MAX, stdin);
    printf("string is: %s\n", buf);

    return 0;
}
```

因为 fgets()从用户那里读取输入，所以我们需要在运行时提供输入。

```cpp
Input:
Hello and welcome to GeeksforGeeks

Output:
Hello and welc

```

**get()**

从标准输入(stdin)中读取字符，并将它们作为 C 字符串存储到 str 中，直到到达换行符或文件结尾。
**语法:**

```cpp
char * gets ( char * str );
str :Pointer to a block of memory (array of char) 
where the string read is copied as a C string.
returns : the function returns str

```

*   使用它不安全，因为它不检查数组绑定。
*   它用于从用户处读取字符串，直到没有遇到换行符。

示例:假设我们有一个 15 个字符的字符数组，并且输入大于 15 个字符，get()将读取所有这些字符并将它们存储到变量中。因为，get()不检查输入字符的最大限制，所以在任何时候编译器都可能返回缓冲区溢出错误。

```cpp
// C program to illustrate
// gets()
#include <stdio.h>
#define MAX 15

int main()
{
    char buf[MAX];

    printf("Enter a string: ");
    gets(buf);
    printf("string is: %s\n", buf);

    return 0;
}
```

由于 get()从用户那里读取输入，我们需要在运行时提供输入。

```cpp
Input:
Hello and welcome to GeeksforGeeks

Output:
Hello and welcome to GeeksforGeeks

```