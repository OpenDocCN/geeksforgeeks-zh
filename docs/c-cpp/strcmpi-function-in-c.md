# C

中的 strcmpi()函数

> 原文:[https://www.geeksforgeeks.org/strcmpi-function-in-c/](https://www.geeksforgeeks.org/strcmpi-function-in-c/)

**str MPI()**函数是 C 语言中的内置函数，在“string.h”头文件中定义。str MPI()函数与 strcmp()函数相同，但唯一的区别是 str MPI()函数不区分大小写，另一方面 strcmp()函数区分大小写。

**语法:**

```cpp
int strcmpi (const char * str1, const char * str2 );

```

**参数:**

*   **str1:** 第一个字符串。
*   **str2:** 第二串。

**返回:**如果给定的两个字符串相同，则该函数返回 0，如果 str1 的长度小于 str2 的长度，则返回负值，如果 str1 的长度大于 str2，则该函数返回正值。

**注意:**这是一个非标准功能，只适用于旧版微软 c。

下面的程序说明了 C 语言中的 strcmpi()函数:

**程序 1:**

```cpp
// C program to demonstrate
// example of strcmpi() function

#include <stdio.h>
#include <string.h>

int main( )
{
   char str1[] = "geeks" ;
   char str2[] = "geeks" ;

   int j = strcmpi ( str1, str2 ) ;

   printf ( "The function returns = %d",j ) ;
   return 0;
}
```

**输出:**

```cpp
The function returns = 0

```

**程序 2:**

```cpp
// C program to demonstrate
// example of strcmpi() function

#include <stdio.h>
#include <string.h>

int main( )
{
   char str1[ ] = "geeks" ;
   char str2[ ] = "ForGeeks" ;

   int i = strcmpi ( str1, str2 ) ;

   printf ( "The function returns = %d", i ) ;
   return 0;
}
```

**输出:**

```cpp
The function returns = 1

```