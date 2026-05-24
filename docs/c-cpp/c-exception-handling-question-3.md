# C++ |异常处理|问题 3

> 原文:[https://www . geesforgeks . org/c-异常处理-问题-3/](https://www.geeksforgeeks.org/c-exception-handling-question-3/)

一个*试一下*块应该放什么？

```cpp

1. Statements that might cause exceptions
2. Statements that should be skipped in case of an exception 
```

**(A)** 仅 1
**(B)** 仅 2
**(C)**1 和 2

**均回答:****(C)**

**说明:**对可能引起问题的语句进行试块。此外，在遇到问题后不应该执行的语句被放在 try 块中。请注意，一旦捕获到异常，控件将转到 catch 块之后的下一行。

[本题小测验](https://www.geeksforgeeks.org/quiz-corner-gq/)