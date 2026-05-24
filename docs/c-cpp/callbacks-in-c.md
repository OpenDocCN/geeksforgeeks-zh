# C 中的回调

> 原文:[https://www.geeksforgeeks.org/callbacks-in-c/](https://www.geeksforgeeks.org/callbacks-in-c/)

回调是作为参数传递给其他代码的任何可执行代码，预计这些代码会在给定时间回调(执行)该参数[来源: [Wiki](https://en.wikipedia.org/wiki/Callback_(computer_programming)) ]。用简单的语言来说，如果一个函数的引用作为参数传递给另一个函数来调用它，那么它将作为回调函数来调用。

在 C 语言中，回调函数是通过[函数指针](https://www.geeksforgeeks.org/function-pointer-in-c/)调用的函数。

下面是 C 中的一个简单的例子来说明上面的定义，让它更清晰:

```cpp
// A simple C program to demonstrate callback
#include<stdio.h>

void A()
{
    printf("I am function A\n");
}

// callback function
void B(void (*ptr)())
{
    (*ptr) (); // callback to A
}

int main()
{
    void (*ptr)() = &A;

    // calling function B and passing
    // address of the function A as argument
    B(ptr);

   return 0;
}
```

```cpp
I am function A

```

在 C++ STL 中，[函子](https://www.geeksforgeeks.org/functors-in-cpp/)也用于此目的。

本文由 [**【巨然活女神】**](https://auth.geeksforgeeks.org/profile.php?user=Ranju Kumari&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。