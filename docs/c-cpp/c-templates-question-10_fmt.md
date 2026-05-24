# C++ |模板|第 10 题

> 原文:[https://www.geeksforgeeks.org/c-templates-question-10/](https://www.geeksforgeeks.org/c-templates-question-10/)

输出？

```cpp
#include <iostream>
using namespace std;

template<int n> struct funStruct
{
    static const int val = 2*funStruct<n-1>::val;
};

template<> struct funStruct<0>
{
    static const int val = 1 ;
};

int main()
{
    cout << funStruct<10>::val << endl;
    return 0;
}
```

**(A)** 编译器错误
**(B)**1024
**(C)**2
**(D)**1

**答案:****(B)**

**解释:**这是[模板元编程](https://www.geeksforgeeks.org/template-metaprogramming-in-c/)的一个例子。这个程序主要计算 2^10.

[本题小考](https://www.geeksforgeeks.org/quiz-corner-gq/)