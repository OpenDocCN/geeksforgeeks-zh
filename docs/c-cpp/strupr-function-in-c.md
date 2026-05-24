# c

中的 strupr()函数

> 原文:[https://www.geeksforgeeks.org/strupr-function-in-c/](https://www.geeksforgeeks.org/strupr-function-in-c/)

**strupr( )** 函数用于将给定的字符串转换为大写。

**语法:**

```cpp
char *strupr(char *str);

```

**参数:**

*   **str:** 这表示我们想要转换成大写的给定字符串。

**返回:**返回给定字符串的字符转换为大写后得到的修改后的字符串。

下面的程序说明了 C 语言中的 strupr()函数:

**实施例 1:-**

```cpp
// c program to demonstrate
// example of strupr() function.
#include<stdio.h>
#include<string.h>

int main()
{
    char str[ ] = "geeksforgeeks is the best";
    //converting the given string into uppercase.
    printf("%s\n", strupr (str));
    return  0;
}
```

**输出:**

```cpp
GEEKSFORGEEKS IS THE BEST

```

**实施例 2:-**

```cpp
// c program to demonstrate
// example of strupr() function.

#include<stdio.h>
#include <string.h>

int main()
{
  char str[] = "CompuTer ScienCe PoRTAl fOr geeKS";

  printf("Given string is: %s\n", str);

  printf("\nstring after converting to the uppercase is: %s", strupr(str));
  return 0;
}
```

**输出:**

```cpp
Given string is: CompuTer ScienCe PoRTAl fOr geeKS

string after converting to the uppercase is: COMPUTER SCIENCE PORTAL FOR GEEKS

```

 **注意:**这是一个非标准函数，只适用于旧版微软 c。