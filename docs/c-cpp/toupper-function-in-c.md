# C

中的 toupper()函数

> 原文:[https://www.geeksforgeeks.org/toupper-function-in-c/](https://www.geeksforgeeks.org/toupper-function-in-c/)

**toupper()** 函数用于将小写字母转换为大写字母。即，如果传递的字符是小写字母，那么 toupper()函数将小写字母转换成大写字母。在 **ctype.h** 头文件中定义。
**语法:**

```cpp
int toupper(int ch);
```

**参数:**接受单个参数:

*   **ch:** 表示要转换为大写的字符。

**返回:**该函数返回 ch 对应的大写字符。
下面的程序说明了 C:
**中的 toupper()函数示例 1:-**

## c

```cpp
// C program to demonstrate
// example of toupper() function.
#include <ctype.h>
#include <stdio.h>

int main()
{
    char ch;

    ch = 'g';
    printf("%c in uppercase is represented as  %c",
           ch, toupper(ch));

    return 0;
}
```

**Output:** 

```cpp
g in uppercase is represented as  G
```