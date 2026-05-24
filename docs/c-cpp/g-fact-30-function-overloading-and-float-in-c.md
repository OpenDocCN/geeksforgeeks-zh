# c++ 中函数重载和浮点

> 原文:[https://www . geesforgeks . org/g-fact-30-function-overload-and-float-in-c/](https://www.geeksforgeeks.org/g-fact-30-function-overloading-and-float-in-c/)

虽然多态性在 C++ 中是一个非常有用的现象，但是它有时会非常复杂。例如，考虑以下代码片段:

```cpp
#include<iostream>
using namespace std;
void test(float s,float t)
{
    cout << "Function with float called ";
}
void test(int s, int t)
{
    cout << "Function with int called ";
}
int main()
{
    test(3.5, 5.6);
    return 0;
}
```

对 main()中的函数测试的调用可能会导致输出“调用了 float 的函数”，但代码给出了以下错误:

```cpp
In function 'int main()':
13:13: error: call of overloaded 'test(double, double)' is ambiguous
 test(3.5,5.6);
```

[函数重载](http://geeksquiz.com/function-overloading-c/)中有一个众所周知的事实，编译器决定重载函数中需要调用哪个函数。如果编译器不能在两个或多个重载函数中选择一个函数，这种情况就是-【函数重载】中的**歧义**。

*   The reason behind the ambiguity of the above code is that the floating characters **3.5** and **5.6** are actually regarded as double precision by the compiler. ***According to the C++ standard, floating-point characters (compile-time constants) are regarded as double precision, unless explicitly specified by suffixes [see 2.14.4 [(here,](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3690.pdf) )*** of the C++ standard]. Because the compiler can't find the function with two parameters and can't figure out whether to convert the value from double to int or float.

**纠正错误:**我们可以通过提供**后缀 f** 简单的告诉编译器，文字是浮点数，不是双精度的。

看下面的代码:

```cpp
#include<iostream>
using namespace std;
void test(float s,float t)
{
    cout << "Function with float called ";
}
void test(int s,int t)
{
    cout << "Function with int called ";
}
int main()
{
    test(3.5f, 5.6f); // Added suffix "f" to both values to 
                     // tell compiler, it's a float value
    return 0;
}
```

**输出:**

```cpp
Function with float called
```

本文由**阿卡斯·萨其德瓦供稿。**如果你喜欢 GeeksforGeeks 并想投稿，你也可以写一篇文章，把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享关于上面讨论的主题的更多信息，请写评论