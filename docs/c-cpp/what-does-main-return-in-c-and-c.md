# C 和 C++ 中 main()返回什么？

> 原文:[https://www . geesforgeks . org/main-in-c-and-c/](https://www.geeksforgeeks.org/what-does-main-return-in-c-and-c/)返回什么

**C**

根据编码标准，一个好的返回程序必须用 **0** 退出主功能。虽然我们在 **C** 中使用`**void main()**`，其中我们不应该编写任何类型的返回语句，但这并不意味着 C 代码不需要 0 作为**退出代码**。让我们看一个例子来澄清我们对代码中的**返回 0** 语句的需求的想法。

**示例#1 :**

```cpp
#include <stdio.h>

void main()
{

    // This code will run properly
    // but in the end,
    // it will demand an exit code.
    printf("It works fine");
}
```

**输出:**

```cpp
It works fine
```

**运行时错误:**

```cpp
NZEC
```