# C

中的 strrev()函数

> 原文:[https://www.geeksforgeeks.org/strrev-function-in-c/](https://www.geeksforgeeks.org/strrev-function-in-c/)

The **strrev()** function is a built-in function in C and is defined in **string.h** header file. The strrev() function is used to reverse the given string.

**语法:**

```cpp
char *strrev(char *str);

```

**参数:**

*   **字符串:**需要反转的给定字符串。

**返回:**该函数返回给定字符串反转后的字符串。

**注意:**这是一个非标准功能，只适用于旧版微软 c。

下面的程序说明了 C 语言中的 strrev()函数:

**实施例 1:-**

```cpp
// C program to demonstrate
// example of strrev() function

#include<stdio.h>
#include<string.h>

int main()
{
   char str[50] = "geeksforgeeks";

   printf("The given string is =%s\n",str);

   printf("After reversing string is =%s",strrev(str));

   return 0;
}
```

**输出:**

```cpp
The given string is =geeksforgeeks
After reversing string is =skeegrofskeeg

```

**实施例 2:-**

```cpp
// C program to demonstrate
// example of strrev() function

#include<stdio.h>
#include<string.h>

int main()
{
   char str[50] = "123456789";

   printf("The given string is =%s\n",str);

   printf("After reversing string is =%s",strrev(str));

   return 0;
}
```

**输出:**

```cpp
The given string is = 123456789
After reversing string is = 987654321

```