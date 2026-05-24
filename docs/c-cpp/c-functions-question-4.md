# C |功能|问题 4

> 原文:[https://www.geeksforgeeks.org/c-functions-question-4/](https://www.geeksforgeeks.org/c-functions-question-4/)

```cpp
#include <stdio.h>
int main()
{
  printf("%d", main);  
  return 0;
}
```

**(A)** 主函数的地址
**(B)** 编译器错误
**(C)** 运行时错误
**(D)** 一些随机值

**答案:****(A)**

**解释:**解释:函数的名字实际上是函数的指针变量，打印函数的地址。符号表是这样实现的。

```cpp
struct
{
   char *name;
   int (*funcptr)();
}
symtab[] = {
   "func", func,
   "anotherfunc", anotherfunc,
};
```