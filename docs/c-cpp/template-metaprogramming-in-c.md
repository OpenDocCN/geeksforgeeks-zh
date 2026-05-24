# c++ 中的模板元编程

> 原文:[https://www . geesforgeks . org/template-meta programming-in-c/](https://www.geeksforgeeks.org/template-metaprogramming-in-c/)

预测后续 C++ 程序的输出。

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
#include <iostream>
using namespace std;

template<int n> struct funStruct
{
    enum { val = 2*funStruct<n-1>::val };
};

template<> struct funStruct<0>
{
    enum { val = 1 };
};

int main()
{
    cout << funStruct<8>::val << endl;
    return 0;
}
```

**输出:**

```cpp
256
```

程序计算“2 升 8 次方(或 2^8)".事实上，结构*函数结构*可以用来计算任何已知 n(或常数 n)的 2^n。上述程序的特别之处在于:**计算是在编译时**完成的。所以，计算 2^8.的是编译器为了理解编译器是如何做到这一点的，让我们考虑以下关于模板和枚举的事实:
1)我们可以将非类型参数(不是数据类型的参数)传递给类/函数模板。
2)像其他常量表达式一样，枚举常量的值在编译时计算。
3)当编译器看到模板的新参数时，编译器会创建模板的新实例。
让我们仔细看看原来的节目。当编译器看到*funStruct<8>:val*时，试图创建一个参数为 8 的 *funStruct* 的实例，结果发现 *funStruct < 7 >* 也必须创建为枚举常量 *val* 必须在编译时求值。对于 *funStruct < 7 >* ，编译器需要 *funStruct < 6 >* 等等。最后，编译器使用*funStruct<1>:val*，编译时递归终止。所以，利用模板，我们可以编写在编译时做计算的程序，这样的程序叫做[模板元程序](http://en.wikipedia.org/wiki/Template_metaprogramming)。模板元编程实际上是[图灵完成](http://en.wikipedia.org/wiki/Turing_completeness)，这意味着任何可由计算机程序表达的计算都可以以某种形式由模板元程序来计算。模板元编程通常不用于实际的程序，尽管这是一个有趣的概念。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。