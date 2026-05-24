# C++ 中函数重载和浮点

> 原文: [https://www.geeksforgeeks.org/g-fact-30-function-overloading-and-float-in-c/](https://www.geeksforgeeks.org/g-fact-30-function-overloading-and-float-in-c/)

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

对 `main()` 中的函数 `test` 的调用可能会导致输出“调用了 float 的函数”，但代码给出了以下错误:

```cpp
In function 'int main()':
13:13: error: call of overloaded 'test(double, double)' is ambiguous
 test(3.5,5.6);
```

[函数重载](http://geeksquiz.com/function-overloading-c/)中有一个众所周知的事实，编译器决定重载函数中需要调用哪个函数。如果编译器不能在两个或多个重载函数中选择一个函数，这种情况就是函数重载中的歧义。

造成上述代码歧义的原因是，浮点字符 `3.5` 和 `5.6` 实际上被编译器视为双精度数。根据 C++ 标准，浮点字符（编译时常量）被视为双精度数，除非通过后缀明确指定（参见 C++ 标准的 [2.14.4 节](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3690.pdf)）。因为编译器找不到具有两个参数的函数，也无法确定是将值从 `double` 转换为 `int` 还是 `float`。

**纠正错误:** 我们可以通过提供后缀 `f` 简单地告诉编译器，字面量是浮点数，不是双精度的。

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

本文由阿卡斯·萨其德瓦供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以写一篇文章，把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享关于上面讨论的主题的更多信息，请写评论。