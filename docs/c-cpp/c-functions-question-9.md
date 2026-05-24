# C |功能|问题 9

> 原文:[https://www.geeksforgeeks.org/c-functions-question-9/](https://www.geeksforgeeks.org/c-functions-question-9/)

函数声明前使用静态是什么意思？

例如，下面的函数 sum 是静态的

```cpp
static int sum(int x, int y, int z)
{
    return (x + y + z);
}
```

**(A)** Static 表示无，sum()没有 Static 关键字也一样。
**(B)** 函数在使用前无需声明
**(C)** 对静态函数的访问仅限于声明它们的文件
**(D)** 静态函数是内联的

**答案:****(C)**

**解释:**在 C 语言中，函数默认是全局的。与全局函数不同，对静态函数的访问仅限于声明它们的文件。我们可以在 C 语言中使用静态变量/函数进行文件级封装，因为当我们将一个全局变量设为静态时，对该变量的访问将被限制在声明它的文件中。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)