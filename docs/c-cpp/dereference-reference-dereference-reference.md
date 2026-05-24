# 程序输出|取消引用，引用，取消引用，引用…

> 原文:[https://www . geesforgeks . org/取消引用-引用-取消引用-引用/](https://www.geeksforgeeks.org/dereference-reference-dereference-reference/)

预测下面程序的输出

```cpp
#include<stdio.h>
int main()
{
 char *ptr = "geeksforgeeks";
 printf("%c\n", *&*&*ptr);

 getchar();
 return 0;
}
```

输出:g

解释:运算符*用于取消引用，运算符&用于获取地址。这些运算符在相继使用时会相互抵消。我们可以多次交替使用它们。比如*ptr 给我们 g，&*ptr 给 g 的地址，*&*ptr 再给 g，&*&*ptr 给 g 的地址，最后*&*&*ptr 给‘g’

现在试试下面

```cpp
#include<stdio.h>
int main()
{
 char *ptr = "geeksforgeeks";
 printf("%s\n", *&*&ptr);

 getchar();
 return 0;
}
```