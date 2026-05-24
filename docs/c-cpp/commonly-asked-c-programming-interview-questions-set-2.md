# 常见 C 编程面试问题|第二集

> 原文:[https://www . geesforgeks . org/common-question-c-programming-interview-questions-set-2/](https://www.geeksforgeeks.org/commonly-asked-c-programming-interview-questions-set-2/)

本帖为第二套[常见 C 编程面试问题|第一套](https://www.geeksforgeeks.org/commonly-asked-c-programming-interview-questions-set-1/)
**C 语言的主要特点是什么？**
C 是一种程序语言。C 语言的主要特点包括对内存的低级访问、简单的关键字集和干净的风格。这些特性使它适用于操作系统或编译器开发等系统编程。

**i++ 和++ i 有什么区别？**
1)表达式‘i++’返回旧值，然后递增 I，表达式++ i 递增值，然后返回新值。
2)后缀++ 的优先级高于前缀++。
3)后缀++ 的结合性是从左到右，前缀++ 的结合性是从右到左。
4)在 C++ 中，+++ I 可以作为 l 值使用，但 i++ 不能。在 C 语言中，它们都不能用作 l 值。
详见[++ * p、*p++ 与* +++ p](https://www.geeksforgeeks.org/difference-between-p-p-and-p/)的区别。
**什么是 l 值？**
l 值或位置值是指赋值运算符左侧可以使用的表达式。例如，在表达式“a = 3”中，a 是 l 值，3 是 r 值。
l 值有两种类型:
“不可修改的 l 值”代表不可修改的 l 值。常量变量是“不可修改的 l 值”。
“可修改 l 值”代表可修改的 l 值。
详见[C 语言左值和右值](https://www.geeksforgeeks.org/lvalue-and-rvalue-in-c-language/)。
**数组和指针有什么区别？**
参见[数组 vs 指针](https://www.geeksforgeeks.org/difference-pointer-array-c/)
**如何编写自己的 sizeof 运算符？**

## c

```cpp
#define my_sizeof(type) (char *)(&type+1)-(char*)(&type)
```

详见[实现自己的](https://www.geeksforgeeks.org/implement-your-own-sizeof/)大小。
**不使用循环，如何打印 1 到 100 的数字？**
我们可以为此使用递归。

## C

```cpp
/* Prints numbers from 1 to n */
void printNos(unsigned int n)
{
  if(n > 0)
  {
    printNos(n-1);
    printf("%d ",  n);
  }
}
```

**什么是 volatile 关键字？**
volatile 关键字旨在防止编译器对对象应用任何可能以编译器无法确定的方式改变的优化。
在优化中省略了声明为 volatile 的对象，因为它们的值可以随时被当前代码范围之外的代码更改。详见[理解 C](https://www.geeksforgeeks.org/understanding-volatile-qualifier-in-c/) 中的“易变”限定词。
**变量可以既有常量又有变量吗？**
是的，const 表示不能给变量赋值。该值可以通过其他代码或指针进行更改。例如，以下程序运行良好。

## C

```cpp
#include <stdio.h>
int main(void)
{
    const volatile int local = 10;
    int* ptr = (int*)&local;
    printf("Initial value of local : %d \n", local);
    *ptr = 100;
    printf("Modified value of local: %d \n", local);
    return 0;
}
```

*   练习 C 上的[测验](https://www.geeksforgeeks.org/quiz-corner-gq/)
*   C [篇](https://www.geeksforgeeks.org/c/)

我们将很快发布更多常见的 C 编程问题集。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。