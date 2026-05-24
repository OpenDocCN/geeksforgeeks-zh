# strlen()函数在 c

中

> 原文:[https://www.geeksforgeeks.org/strlen-function-in-c/](https://www.geeksforgeeks.org/strlen-function-in-c/)

**strlen()** 函数计算给定字符串的长度。 **strlen()** 函数在 **string.h** 头文件中定义。它不计算空字符' \0 '。

**语法:**

```cpp
int strlen(const char *str);

```

**参数:**

*   **str:** 它代表我们必须找到其长度的字符串变量。

**返回:**这个函数返回传递的字符串长度。

下面的程序说明了 C 语言中的 strlen()函数:

**实施例 1:-**

```cpp
// c program to demonstrate
// example of strlen() function.

#include<stdio.h>
#include <string.h>

int main()
{
   char ch[]={'g', 'e', 'e', 'k', 's', '\0'};

   printf("Length of string is: %d", strlen(ch));

 return 0;
}
```

输出:

```cpp
Length of string is: 5
```

**实施例 2:-**

```cpp
// c program to demonstrate
// example of strlen() function.

#include<stdio.h>
#include <string.h>

int main()
{
   char str[]= "geeks";

   printf("Length of string is: %d", strlen(str));

 return 0;
}
```

**输出:**

```cpp
Length of string is: 5
```

**实施例 3:-**

```cpp
// c program to demonstrate
// example of strlen() function.
#include<stdio.h>
#include <string.h>

int main()
{
   char *str = "geeks";

   printf("Length of string is: %d", strlen(str));

 return 0;
}
```

输出:

```cpp
Length of string is: 5
```