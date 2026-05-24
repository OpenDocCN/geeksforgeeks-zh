# C 和 C++ 中字符常量的数据类型

> 原文:[https://www.geeksforgeeks.org/g-fact-19-2/](https://www.geeksforgeeks.org/g-fact-19-2/)

在 C 语言中，字元常数资料型别为 int，但在 C++ 中，相同的资料型别为 char。

如果我们将下面的程序保存为 *test.c* ，那么我们得到 4 作为输出(假设整数的大小是 4 字节)，如果我们将相同的程序保存为 *test.cpp* ，那么我们得到 1(假设字符的大小是 1 字节)

```cpp
#include<stdio.h>
int main()
{
  printf("%d", sizeof('a'));

  getchar();
  return 0;
} 
```

参考文献:
[http://en.wikipedia.org/wiki/C_syntax#Character_constants](http://en.wikipedia.org/wiki/C_syntax#Character_constants)