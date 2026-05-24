# C++ |异常处理|问题 10

> 原文:[https://www . geesforgeks . org/c-异常处理-问题-10/](https://www.geeksforgeeks.org/c-exception-handling-question-10/)

关于 C++ 中的异常处理，以下哪一项是正确的？

1)有一个标准的异常类，像 Java 中的 exception 类。
2)c++ 中所有异常都是不检查的，即编译器不检查异常是否被捕获。
3)在 C++ 中，函数可以使用逗号分隔的列表指定它可以抛出的异常列表，如下所示。

```cpp
  void fun(int a, char b) throw (Exception1, Exception2, ..) 
```

**(A)** 1 和 3
**(B)** 1、2 和 3
**(C)** 1 和 2
**(D)** 2 和 3

**回答:****(B)**

**解释:**参见[c++ 和 Java 中异常处理的比较](https://www.geeksforgeeks.org/comparison-of-exception-handling-in-c-and-java/)