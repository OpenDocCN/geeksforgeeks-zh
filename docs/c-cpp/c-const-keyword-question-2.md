# C++ | const 关键字|问题 2

> 原文:[https://www.geeksforgeeks.org/c-const-keyword-question-2/](https://www.geeksforgeeks.org/c-const-keyword-question-2/)

在 C++ 中，const 限定符可以应用于
1)类的成员函数
2)函数参数
3)声明为静态的类数据成员
4)引用变量
**(A)** 只有 1、2 和 3
**(B)** 只有 1、2 和 4
**(C)** 全部
**(D)** 只有 1、3 和 4

当我们不想修改参数并将其作为引用或指针传递时，我们使用 const 限定符，以便该参数不会在函数中被意外修改。

对于类范围的常量，类数据成员可以声明为常量和静态。

引用变量引用常量位置时可以是常量。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)