# C++ |参考文献|问题 6

> 原文:[https://www.geeksforgeeks.org/c-references-question-3/](https://www.geeksforgeeks.org/c-references-question-3/)

下列哪个函数必须使用 reference？
**(A)** 赋值运算符函数
**(B)** 复制构造函数
**(C)** 析构函数
**(D)** 参数化构造函数

**答案:****(B)**

**解释:**通过值传递对象时调用复制构造函数。复制构造函数本身就是一个函数。因此，如果我们在复制构造函数中按值传递参数，将会调用复制构造函数来调用复制构造函数，这将成为一个非终止的调用链。因此，编译器不允许参数按值传递。

详见[https://www.geeksforgeeks.org/copy-constructor-in-cpp/](https://www.geeksforgeeks.org/copy-constructor-in-cpp/)。

[本题小考](https://www.geeksforgeeks.org/c-plus-plus-gq/references-gq/)