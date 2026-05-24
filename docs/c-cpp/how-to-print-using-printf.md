# 如何使用 printf()打印% 1？

> 原文:[https://www.geeksforgeeks.org/how-to-print-using-printf/](https://www.geeksforgeeks.org/how-to-print-using-printf/)

由 Tanuj 提问

这是 C.
中 printf 函数的标准原型

```cpp
          int printf(const char *format, ...);

```

格式字符串由零个或多个指令组成:普通字符(非%)，不变地复制到输出流中；和转换规范(如果给定的参数不够多，则是错误的)。

字符%后跟以下字符之一。

标志字符
字段宽度
精度
长度修饰符
转换说明符:

以上所有角色详见[http://swoolley.org/man.cgi/3/printf](http://swoolley.org/man.cgi/3/printf)。标准中需要注意的主要是下面关于转换说明符的一行。

```cpp
A `%' is written. No argument is converted. The complete conversion specification is`%%'.

```

因此，我们可以使用“%%”打印“%”

```cpp
/* Program to print %*/
#include<stdio.h>
/* Program to print %*/
int main()
{
   printf("%%");
   getchar();
   return 0;
}
```

我们也可以使用下面的打印“%”。

```cpp
printf("%c", '%');
printf("%s", "%");
```