# 如何在不使用循环或递归的情况下打印 N 次？

> 原文:[https://www . geesforgeks . org/如何在不使用循环或递归的情况下打印 n 次/](https://www.geeksforgeeks.org/how-to-print-n-times-without-using-loops-or-recursion/)

如何在不使用循环或递归或 goto 的情况下打印 N 次“Hello”(其中 N 是用户输入)。

> 输入:N，表示要打印语句的次数。
> 输出:N 次语句

首先我们创建一个类。之后，我们需要通过在 cout/print 语句中写入要打印的语句来初始化类的构造函数。这里使用的基本思想是“创建类的对象的次数，该类的构造函数被调用的次数。”

```cpp
// CPP program to print a sentence N times
// without loop and recursion.
// Author : Rohan Prasad
#include <iostream>
using namespace std;
class Print {

public:
    Print()
    {
        cout << "Hello" << endl;
    }
};

int main()
{
    int N = 5;
    Print a[N];
    return 0;
}
```

**Output:**

```cpp
Hello
Hello
Hello
Hello
Hello

```