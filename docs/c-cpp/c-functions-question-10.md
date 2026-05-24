# C |功能|问题 10

> 原文:[https://www.geeksforgeeks.org/c-functions-question-10/](https://www.geeksforgeeks.org/c-functions-question-10/)

在 C 语言中，跟随空参数表的函数原型是什么意思

```cpp
void fun()
{
   /* .... */
}
```

**(A)** 函数只能在没有任何参数的情况下调用
**(B)** 函数可以用任意类型的任意数量的参数调用
**(C)** 函数可以用任意数量的整数参数调用。
**(D)** 函数可以用一个整数参数调用。

**回答:****(B)**

**说明:**C 中的空列表表示参数列表没有指定，可以用任意参数调用函数。在 C 语言中，要声明一个只能在没有任何参数的情况下调用的函数，我们应该使用“void fun(void)”

顺便说一下，在 C++ 中，空列表意味着函数只能在没有任何参数的情况下调用。在 C++ 中，void fun()和 void fun(void)都是相同的。

[本题小考](https://www.geeksforgeeks.org/functions-properties-and-types-injective-surjective-bijective/)