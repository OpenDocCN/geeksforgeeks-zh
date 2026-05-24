# C

中的 putchar()函数

> 原文:[https://www.geeksforgeeks.org/putchar-function-in-c/](https://www.geeksforgeeks.org/putchar-function-in-c/)

C 语言中的 **putchar(int char)** 方法用于将无符号字符类型的字符写入 stdout。此字符作为参数传递给此方法。

**语法:**

```cpp
int putchar(int char)
```

**参数:**该方法接受一个强制参数**字符**，它是要写入 stdout 的字符。

**返回值:**该函数将写在 stdout 上的字符作为无符号字符返回。当出现一些错误时，它也会返回 EOF。

下面的例子说明了 putchar()方法的使用:

**例 1:**

```cpp
// C program to demonstrate putchar() method

#include <stdio.h>

int main()
{

    // Get the character to be written
    char ch = 'G';

    // Write the Character to stdout
    putchar(ch);

    return (0);
}
```

**Output:**

```cpp
G

```

**例 2:**

```cpp
// C program to demonstrate putchar() method

#include <stdio.h>

int main()
{

    // Get the character to be written
    char ch = '1';

    // Write the Character to stdout
    for (ch = '1'; ch <= '9'; ch++)
        putchar(ch);

    return (0);
}
```

**Output:**

```cpp
123456789

```