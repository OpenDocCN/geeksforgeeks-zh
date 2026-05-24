# getchar _ unlock()–更快的 C/C++ 输入，用于竞争性编程

> 原文:[https://www . geesforgeks . org/getchar _ unlock-fast-input-cc-competitive-programming/](https://www.geeksforgeeks.org/getchar_unlocked-faster-input-cc-competitive-programming/)

[getchar _ unlock()](http://linux.die.net/man/3/getchar_unlocked)与 getchar()类似，只是它不是线程安全的。下面是一个示例代码。

```cpp
// A simple C program to demonstrate
// working of getchar_unlocked()
#include <stdio.h>
int main()
{
    // Syntax is same as getchar()
    char c = getchar_unlocked();

    printf("Entered character is %c", c);

    return 0;
}
```

```cpp
Input: g
Output: Entered character is g 
```

以下是一些要点:

1.  Because it is not thread safe, it avoids all the overhead of mutual exclusion and is faster than getchar ().
2.  A particularly useful warning for competitive programming problems with "*: Be careful with some languages for large I/O data (although most of them should be possible if the algorithm is well designed)* "
3.  Even if getchar _ unlocked () is used in a multithreaded environment, there is no problem, as long as the thread that uses it is the only thread that accesses the file object.
4.  Another difference from getchar () is that it is not a C standard library function, but a POSIX function. It may not work on a Windows-based compiler.
5.  ***It is well known that it is faster than scanf () than cin, while getchar () is generally faster than scanf (). Getchar _ unlocked () is faster than getchar (), so it is the fastest.***
6.  Similarly, there are two non-thread safe versions of getc _ unlock()putc _ unlock () and putchar _ unlocked (), which are getc (), putc () and putchar () respectively.

    ```cpp
    // A simple C program to demonstrate
    // working of putchar_unlocked()
    #include <stdio.h>
    int main()
    {
        // Syntax is same as getchar()
        char c = getchar_unlocked();

        putchar_unlocked(c);

        return 0;
    }
    ```

    ```cpp
    Input: g
    Output: g

    ```

作为练习，读者可以使用 getchar _ unlocked()尝试此处给出的解决方案，并使用 getchar()比较性能。

本文由 **Ayush Saluja** 供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论