# 在 C 语言中不使用循环、递归和宏扩展，打印一个数字 100 次？

> 原文:[https://www . geesforgeks . org/print-number-100-遍-不使用-循环-递归-宏-扩展-c/](https://www.geeksforgeeks.org/print-number-100-times-without-using-loop-recursion-macro-expansion-c/)

使用循环或递归方法可以解决这个问题。并且我们已经看到了使用 [#define 指令(宏扩展)](https://www.geeksforgeeks.org/print-number-100-times-without-using-loop-recursion-c/)的解决方案，但是如果三者都不允许呢？
一个简单的解决方法是在 cout 语句中把数字写 100 遍。更好的解决方法是使用中[的概念，跳步和龙跳的概念。](https://www.geeksforgeeks.org/g-fact22-concept-of-setjump-and-longjump/)

```cpp
// CPP program to print one 100 times.
#include <iostream>
#include <setjmp.h>
using namespace std;

jmp_buf buf;

int main()
{
    int x = 1;

    // Setup jump position using buf
    setjmp(buf);
    cout << "1"; // Prints 1

    x++ ;
    if (x <= 100)

        // Jump to the point setup by setjmp
        longjmp(buf, 1);

    return 0;
}
```

输出:

```cpp
 100 times 1.

```

同样的也可以写成 C。

本文由 [Aditya Rakhecha](https://www.linkedin.com/in/aditya-rakhecha-34a597129/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。