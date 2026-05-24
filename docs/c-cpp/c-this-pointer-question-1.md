# C++ |这个指针|问题 1

> 原文:[https://www.geeksforgeeks.org/c-this-pointer-question-1/](https://www.geeksforgeeks.org/c-this-pointer-question-1/)

关于这个指针，以下哪一项是正确的？
**(A)** 作为隐藏参数传递给所有函数调用
**(B)** 作为隐藏参数传递给所有非静态函数调用
**(C)** 作为隐藏参数传递给所有静态函数
**(D)** 以上

**均无答案:****(B)**

**解释“this”指针是一个常量指针，保存当前对象的内存地址。“this”指针在静态成员函数中不可用，因为静态成员函数可以在没有任何对象(带有类名)的情况下调用。**

来源:[【这个】指针在 C++ ](https://www.geeksforgeeks.org/this-pointer-in-c/)

[本题竞猜](https://www.geeksforgeeks.org/quiz-corner-gq/)