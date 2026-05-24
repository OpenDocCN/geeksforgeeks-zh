# C++ |构造函数|第 14 题

> 原文:[https://www.geeksforgeeks.org/c-constructors-question-14/](https://www.geeksforgeeks.org/c-constructors-question-14/)

关于构造函数，以下哪一项是正确的？
1) 它们不能是虚拟的。
2) 它们不能是私有的。
3) `new`操作符自动呼叫它们。
**(A)** 全部 1、2、3
**(B)** 只有 1、3
**(C)** 只有 1、2
**(D)** 只有 2、3

**答案:****(B)**

**解释:**
1) 真: `虚拟构造函数`没有意义，是吗
2) False: `构造函数`可以是私有的，例如，当我们不想创建可复制的对象时，我们将`复制构造函数`设为私有。不制作可复制对象的原因可能是为了避免浅层复制。
3) True: `构造函数`由`new`运算符自动调用，我们实际上可以将参数传递给`构造函数`。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)