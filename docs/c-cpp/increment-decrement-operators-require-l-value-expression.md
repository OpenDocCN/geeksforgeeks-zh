# 增量(减量)运算符需要 L 值表达式

> 原文:[https://www . geesforgeks . org/increment-减量-operators-require-l-value-expression/](https://www.geeksforgeeks.org/increment-decrement-operators-require-l-value-expression/)

以下程序的输出将是什么？

```cpp
#include<stdio.h>
int main()
{
   int i = 10;
   printf("%d", ++(-i));
   return 0;
}
```

```cpp
A) 11 B) 10 C) -9 D) None
```

**回答:** D，无–编译错误。

**说明:**

在 C/C++ 中，前递增(递减)和后递增(递减)运算符需要一个 L 值表达式作为操作数。提供一个 [R 值](http://en.wikipedia.org/wiki/Value_(computer_science))或一个*常量*限定变量会导致编译错误。

在上面的程序中，表达式 *-i* 产生 R 值，R 值是预增量运算符的操作数。预递增运算符需要一个 L 值作为操作数，因此编译器会抛出一个错误。

递增/递减运算符需要在[序列点](http://en.wikipedia.org/wiki/Sequence_point)之后更新操作数，因此需要一个 L 值。一元运算符如-、+，不需要 L 值作为操作数。表达式 *-(++ i)* 有效。

在 C++ 中，由于引用，规则有点复杂。我们可以将这些前/后递增(递减)操作符应用于未被*常量*限定的引用变量。引用也可以从函数中返回。

由**文基**表述的谜题。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。