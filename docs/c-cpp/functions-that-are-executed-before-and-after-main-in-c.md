# 在 C

中 main()前后执行的功能

> 原文:[https://www . geeksforgeeks . org/c 中 main 前后执行的函数/](https://www.geeksforgeeks.org/functions-that-are-executed-before-and-after-main-in-c/)

使用 GCC 系列的 C 编译器，我们可以在 main()之前和之后标记一些要执行的函数。所以有些启动代码可以在 main()启动之前执行，有些清理代码可以在 main()结束之后执行。例如，在下面的程序中，在 main()之前调用 myStartupFun()，在 main()之后调用 myCleanupFun()。

```cpp
#include<stdio.h>

/* Apply the constructor attribute to myStartupFun() so that it
    is executed before main() */
void myStartupFun (void) __attribute__ ((constructor));

/* Apply the destructor attribute to myCleanupFun() so that it
   is executed after main() */
void myCleanupFun (void) __attribute__ ((destructor));

/* implementation of myStartupFun */
void myStartupFun (void)
{
    printf ("startup code before main()\n");
}

/* implementation of myCleanupFun */
void myCleanupFun (void)
{
    printf ("cleanup code after main()\n");
}

int main (void)
{
    printf ("hello\n");
    return 0;
}
```

输出:

```cpp
startup code before main()
hello
cleanup code after main()

```

和上面的特性一样，GCC 在标准 C 语言中增加了许多其他有趣的特性。详见[本](http://drdobbs.com/cpp/184401956)。

**相关文章:**
[在 C–幕后执行 main()](https://www.geeksforgeeks.org/executing-main-in-c-behind-the-scene/)

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。