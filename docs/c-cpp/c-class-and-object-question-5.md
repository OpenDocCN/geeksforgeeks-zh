# C++ |类和对象|问题 5

> 原文:[https://www . geesforgeks . org/c-class-and-object-question-5/](https://www.geeksforgeeks.org/c-class-and-object-question-5/)

假设一个整数和一个指针各取 4 个字节。此外，假设对象中没有对齐。

预测程序的输出。

```cpp
#include<iostream>
using namespace std;

class Test
{
    static int x;
    int *ptr;
    int y;
};

int main()
{
    Test t;
    cout << sizeof(t) << " ";
    cout << sizeof(Test *);
}
```

**(A)**12 4
**(B)**12 12
**(C)**8 4
**(D)**8 8

**答案:****(C)**

**解释:**对于指针取 4 字节的编译器，语句“sizeof(Test *)”返回 4(指针 PTT 的大小)

语句“sizeof(t)”返回 8。因为静态不与类的每个对象相关联，所以我们得到(8 而不是 12)。

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)