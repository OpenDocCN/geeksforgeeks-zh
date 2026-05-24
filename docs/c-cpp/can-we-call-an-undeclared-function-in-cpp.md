# 我们可以在 C++ 中调用未声明的函数吗？

> 原文:[https://www . geeksforgeeks . org/can-we-call-a-未声明的函数 in-cpp/](https://www.geeksforgeeks.org/can-we-call-an-undeclared-function-in-cpp/)

在 C 中调用未声明的函数是一种糟糕的风格(参见[这个](https://www.geeksforgeeks.org/g-fact-95/))，在 c++ 中是非法的，使用不列出参数类型的声明将参数传递给函数也是非法的。

如果我们在 C 语言中调用一个未声明的函数并编译它，它可以毫无错误地工作。但是，如果我们在 C++ 中调用一个未声明的函数，它不会编译并产生错误。

在以下示例中，代码将在 C、

## 【C】

```cpp
// C Program to demonstrate calling an undeclared function
#include <stdio.h>

// Argument list is not mentioned
void f();

// Driver Code
int main()
{
    // This is considered as poor style in C, but invalid in
    // C++
    f(2);
    getchar();
    return 0;
}

void f(int x) { printf("%d", x); }
```

**输出**中正常工作

```cpp
2
```