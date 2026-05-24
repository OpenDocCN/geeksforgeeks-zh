# erf |在 C++ 中使用 cmath 的错误函数

> 原文:[https://www . geesforgeks . org/ERF-error-functions-using-cmath-c/](https://www.geeksforgeeks.org/erf-error-functions-using-cmath-c/)

在数学中，[误差函数](https://en.wikipedia.org/wiki/Error_function)(也称为高斯误差函数)是一种特殊的 sigmoid 形状的函数(非初等)，出现在概率、统计和描述扩散的偏微分方程中。

它是均值为 0、方差为 0.5 的正态随机变量取值在[-x，x]之间的概率。它由 erf(x)表示，计算方法如下

![{\displaystyle {\begin{aligned}\operatorname {erf} (x)&={\frac {1}{\sqrt {\pi }}}\int _{-x}^{x}e^{-t^{2}}\,dt\\[5pt]&={\frac {2}{\sqrt {\pi }}}\int _{0}^{x}e^{-t^{2}}\,dt.\end{aligned}}}](img/62a1a8b648fc0fad8ac3ab6f89a6e8c1.png "Rendered by QuickLaTeX.com")

在 C++ 的 **cmath** 库中，已经实现了错误函数。有两种这样的功能:-

1.  **erf(x)** :该内置函数计算 x 输入值的误差函数，参数 x 可以是 int 或 float 或 double。它返回一个双精度值，即 erf(x)。
2.  **erfc(x)** :此内置函数计算 x 输入值的误差函数的余数，参数 x 可以是 int 或 float 或 double。它返回一个 1–ERF(x)的双精度值。

```cpp
/* C++ code to use erf */
#include <iostream>
#include <cmath>     /* erf */

using namespace std;

double findProbability(double a)
{
    double prob_x_a = erf(a);
    return prob_x_a;
}

int main ()
{
    double a = 0.25;
    cout << "probability that normal r.v "
            "X takes value between " 
         << -a << " & " << a << " is " 
         << findProbability(a) << endl;
    return 0;
}
```

输出:

```cpp
probability that normal r.v X takes value
between -0.25 & 0.25 is 0.276326

```

参考:
[维基百科](https://en.wikipedia.org/wiki/Error_function)

本文由 [**普拉蒂克·查哈尔**](https://pratik-chhajer.github.io/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。