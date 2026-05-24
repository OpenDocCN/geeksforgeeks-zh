# 为什么变量名不以 C 中的数字开头？

> 原文:[https://www . geesforgeks . org/变量名-非起始数字-c/](https://www.geeksforgeeks.org/variable-name-not-start-numbers-c/)

在 C 语言中，除了关键字，C 程序中的所有东西都被视为标识符。标识符可以是变量、常数、函数和用户定义数据的名称。变量名可以由字母(大写、小写)、数字(0-9)和 _(下划线)字符组成。但是任何变量的名称都不能以数字开头。现在我们肯定有了答案，为什么不能以数字开头命名一个变量。以下可能是其原因。编译器有如下 7 个阶段:

```cpp
    Lexical Analysis
    Syntax Analysis
    Semantic Analysis
    Intermediate Code Generation
    Code Optimization
    Code Generation
    Symbol Table

```

在编译这段代码时，在词法分析阶段避免了回溯。像苹果这样的变量；，在词法分析阶段遇到字母‘A’字符时，编译器会马上知道它是一个标识符。然而，像 123apple 这样的变量；，编译器将无法决定它是一个数字还是一个标识符，直到它遇到“a ”,它需要回溯到词法分析阶段，以识别它是一个变量。但是编译器不支持它。
解析令牌时，您只需查看第一个字符来确定它是标识符还是文字，然后将其发送到正确的函数进行处理。这就是性能优化。

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。