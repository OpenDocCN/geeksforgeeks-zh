# C 中静态变量的默认值是什么？

> 原文:[https://www.geeksforgeeks.org/g-fact-53/](https://www.geeksforgeeks.org/g-fact-53/)

在 C 语言中，如果有静态存储时长的对象没有显式初始化，那么:
—如果有指针类型，则初始化为 NULL 指针；
—如果有算术类型，则初始化为零(正或无符号)；
—如果它是一个集合，则根据这些规则初始化(递归地)每个成员；
—如果是联合，则根据这些规则初始化(递归地)第一个命名成员。

例如，以下程序打印:
*g = 0 的值
SG = 0 的值
s = 0 的值* 

```cpp
#include<stdio.h>
int g;  //g = 0, global objects have static storage duration
static int gs; //gs = 0, global static objects have static storage duration
int main()
{
  static int s; //s = 0, static objects have static storage duration
  printf("Value of g = %d", g);
  printf("\nValue of gs = %d", gs);
  printf("\nValue of s = %d", s);

  getchar();
  return 0;
}
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。

参考文献:
C99 标准