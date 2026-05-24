# 获取堆栈大小，在 C

中设置线程属性的堆栈大小

> 原文:[https://www . geesforgeks . org/get-stack-size-set-stack-size-thread-attribute-c/](https://www.geeksforgeeks.org/get-stack-size-set-stack-size-thread-attribute-c/)

先决条件:[多线程](https://www.geeksforgeeks.org/multithreading-c-2/)

**语法:**

```cpp
// to get size of stack
int pthread_attr_getstacksize(const pthread_attr_t* restrict attr,
                                          size_t* restrict stacksize);

// to set size of stack
int pthread_attr_setstacksize(pthread_attr_t* attr, size_t stacksize);
```

。
**pthread _ attr _ getstacksize():**
它用于获取线程堆栈大小。stacksize 属性给出了分配给线程堆栈的最小堆栈大小。当成功运行时，它给出 0，否则给出任何值。

*第一个参数–*它采用 pthread 属性。
*第二个参数–*它接受一个变量并给出线程属性的大小。

**pthread _ attr _ setstacksize():**
用于设置新线程堆栈大小。stacksize 属性给出了分配给线程堆栈的最小堆栈大小。当成功运行时，如果错误给出任何值，则给出 0。

*第一个参数–*它采用 pthread 属性。
*第二个参数–*它采用新堆栈的大小(以字节为单位)

```cpp
#include <stdio.h>
#include <stdlib.h>
#include <pthread.h>

int main()
{

    // for takes the size of threads stack
    size_t stksize;

    // attribute declaration
    pthread_attr_t atr;

    // it gets the threads stack size and give 
    // value in stksize variable
    pthread_attr_getstacksize(&atr, &stksize);

    // print the current threads stack size
    printf("Current stack size - > %d\n", stksize);

    // then set the new threads stack size
    pthread_attr_setstacksize(&atr, 320000034);
    pthread_attr_getstacksize(&atr, &stksize);

    // print the new stack size
    printf("New stack size-> %d\n", stksize);
    return 0;
}
```

**输出:**

```cpp
Current stack size - > 4196464
New stack size-> 320000034

```

**为编译使用 gcc program _ name . c-lpthread**

本文由 **Devanshu Agarwal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。