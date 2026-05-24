# C/c++

中的 nextafter()和 next 朝向()

> 原文:[https://www . geeksforgeeks . org/g-fact-37-next after-next 朝向-c/](https://www.geeksforgeeks.org/g-fact-37-nextafter-nexttoward-c/)

**你会如何用 C/C++ 解决下面的问题？**

*   C/C++ 中最小的可表示的正浮点数是多少？
*   C/C++ 中最大可表示的负浮点数是多少？
*   给定一个正浮点数 x，求小于 x 的最大可表示浮点值？

**nextafter(x，y)和 next 朝向(x.y)**
在 C 和 C++ 中，nextafter(x，y)和 next 朝向(x.y)都是在 math.h 或 cmath 头文件中定义的类似函数。它们都沿 y 方向返回 x 之后的下一个可表示值。【next 朝向()具有更精确的第二个参数 y。

以下程序演示了这一概念:

```cpp
// C program to demonstrate use of nextafter() and nexttoward()
#include <stdio.h>
#include <math.h>
int main ()
{
    // using nextafter
    printf ("Smallest positive floating point number : %e\n",
            nextafter(0.0, 1.0));
    printf ("Largest negative floating point number :%e\n",
            nextafter(0.0, -1.0));
    printf ("Largest positive floating point number smaller than 0.5 : %e\n",
            nextafter(0.5, 0.0));

    // using nexttoward
    printf ("Smallest positive floating point number : %e\n",
            nexttoward(0.0, 1.0));
    printf ("Largest negative floating point number : %e\n",
            nexttoward(0.0, -1.0));
    printf ("Largest positive floating point number smaller than 0.5 : %e\n",
            nexttoward(0.5, 0.0));
    return (0);
}
```

输出:

```cpp
nextafter first value greater than zero: 4.940656e-324
nextafter first value less than zero: -4.940656e-324
nexttoward first value greater than zero: 4.940656e-324
nexttoward first valnextafter first value greater than zero: 4.940656e-324
nextafter first value less than zero: -4.940656e-324
nexttoward first value greater than zero: 4.940656e-324
nexttoward first value less than zero: -4.940656e-324 ue less than zero: -4.940656e-324 
```

本文由**阿迪蒂亚·查特吉供稿。**如果你喜欢 GeeksforGeeks 并想投稿，你也可以写一篇文章，把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论