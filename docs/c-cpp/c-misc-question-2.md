# C | Misc |问题 2

> 原文:[https://www.geeksforgeeks.org/c-misc-question-2/](https://www.geeksforgeeks.org/c-misc-question-2/)

C 语言是。(GATE CS 2002)
**(A)** 一种上下文无关语言
**(B)** 一种上下文相关语言
**(C)** 一种常规语言
**(D)** 只有通过图灵机才能完全解析

**答案:****(B)**

T21】解释: C 和 C++ 都是上下文相关的

有几个原因:

1.  要解析 C 和 C++，首先要使用非常强大的*预处理器*。这些预处理程序不可避免地是手工编写的(它们不像正则表达式或上下文无关语法那样基于理论基础)。
2.  语法是模糊的:它有 LR 冲突，比如 if-then-else 冲突。解析器通常使用上下文来解决这个问题(一个“else”匹配最接近的“if”)。
3.  C and C++ lexers require lexical feedback to differentiate between typedef names and identifiers. That is, the context-sensitive lexer needs help from the “context-free” parser to distinguish between an identifier “foo” and a typedef name “foo”. In this snippet,

    ```cpp
    int foo;
    typedef int foo;
    foo x;
    ```

    第一个“foo”是标识符，而第二个和第三个是 typedef 名称。您需要解析 typedef 声明来解决这个问题(由于类型有嵌套的括号，这肯定至少和解析上下文无关的语言一样困难)。
    这意味着解析器和 lexer 是相互递归的，所以说解析器是上下文无关的，而 lexer 是上下文相关的是没有意义的。

参考: [C 和 C++ 不是上下文无关的](http://trevorjim.com/c-and-cplusplus-are-not-context-free/)

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/misc-gq/)