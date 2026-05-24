# strwr()函数在 C

中

> 原文:[https://www.geeksforgeeks.org/strlwr-function-in-c/](https://www.geeksforgeeks.org/strlwr-function-in-c/)

**strwr()**函数是 C 语言中的内置函数，用于将给定字符串转换为小写。

**语法:**

```cpp
char *strlwr(char *str);

```

**参数:**

*   **str:** 这表示我们想要转换成小写的给定字符串。

**返回:**返回给定字符串的字符转换为小写后得到的修改后的字符串。

**注意:**这是一个非标准功能，只适用于旧版微软 c。

下面的程序说明了 C 语言中的 strlwr()函数:

**实施例 1:-**

```cpp
// C program to demonstrate
// example of strlwr() function

#include<stdio.h>
#include<string.h>

int main()
{
    char str[ ] = "GEEKSFORGEEKS IS THE BEST";

    // converting the given string into lowercase.
    printf("%s\n",strlwr (str));

    return  0;
}
```

**输出:**

```cpp
geeksforgeeks is the best

```

**实施例 2:-**

```cpp
// C program to demonstrate
// example of strlwr() function.

#include<stdio.h>
#include <string.h>

int main()
{
  char str[] = "CompuTer ScienCe PoRTAl fOr geeKS";

  printf("Given string is: %s\n",str);

  printf("\nString after converting to the "
             "lowercase is: %s",strlwr(str));

  return 0;
}
```

**输出:**

```cpp
Given string is: CompuTer ScienCe PoRTAl fOr geeKS

String after converting to the lowercase is: computer science portal for geeks

```