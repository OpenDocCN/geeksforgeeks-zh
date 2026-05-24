# 标准::C++ 17 中的 LCM

> 原文:[https://www.geeksforgeeks.org/stdlcm-in-cpp17/](https://www.geeksforgeeks.org/stdlcm-in-cpp17/)

竞争规划通常涉及两个数的最小公倍数的计算。一种方法是使用 **boost::math::lcm()** ，这是我们在文章–[中讨论的用于在 C++ 中计算 lcm 的内置函数。](https://www.geeksforgeeks.org/inbuilt-function-calculating-lcm-cpp/)
但是，最近，C++ 在其最新版本 C++ 17 中也包含了另一个用于计算 LCM 的内置函数， **std::lcm()** 。这个函数是在头文件中定义的。

**语法:**

```cpp
std::lcm (m, n)
Arguments: m, n
Returns: 0, if either of m or n are 0
         else, returns lcm of mod(m) and mod(n)

```

请记住，由于这个特性是在最新版本的 C++ 中定义的，所以在不支持 C++ 17 的编译器中使用这个函数，会抛出一个错误。

```cpp
// CPP program to illustrate
// std::lcm function of C++
#include <iostream>
#include <numeric>

using namespace std;

int main()
{
    cout << "LCM(10, 20) = " << std::lcm(10, 20)
         << endl;
    return 0;
}
```

输出:

```cpp
20

```

**要点:**

1.  这个函数对**正数**起作用，如果有一个自变量是负数，首先转换成它的模，然后计算 LCM。
2.  此外，它只在**整数数据类型**上工作，如果在其参数中提供了任何其他数据类型，如 char、double，那么它将抛出一个错误。

**参考:**

1.  [C++ 周刊–Ep 67–c++ 17 的标准::gcd 和标准::lcm](https://www.youtube.com/watch?v=akak2jYXOVg)

本文由**姆里根德拉·辛格**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。