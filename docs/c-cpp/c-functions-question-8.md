# C |功能|问题 8

> 原文:[https://www.geeksforgeeks.org/c-functions-question-8/](https://www.geeksforgeeks.org/c-functions-question-8/)

函数声明前使用 extern 是什么意思？

例如，下面的函数求和是在外部进行的

```cpp
extern int sum(int x, int y, int z)
{
    return (x + y + z);
}
```

**(A)** 功能全球可用
**(B)** extern 不代表什么，sum()没有 extern 关键字也一样。
**(C)** 函数在使用前不需要声明
**(D)** 函数是本地文件。

**回答:****(B)**

**说明:** extern 关键字用于全局变量。函数是全局的，所以添加 extern 不会增加任何东西。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)