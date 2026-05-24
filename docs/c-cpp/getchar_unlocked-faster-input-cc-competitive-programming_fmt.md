# getchar_unlocked() – 更快的 C/C++ 输入，用于竞争性编程

> 原文：`https://www.geeksforgeeks.org/getchar_unlocked-faster-input-cc-competitive-programming/`

[`getchar_unlocked()`](http://linux.die.net/man/3/getchar_unlocked) 与 `getchar()` 类似，只是它不是线程安全的。下面是一个示例代码。

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

## 以下是一些要点

1.  因为它不是线程安全的，所以避免了所有互斥锁的开销，比 `getchar()` 更快。
2.  对于竞争性编程问题中 "*: 对于大量 I/O 数据，请小心使用某些语言（尽管如果算法设计得当，大多数语言都应该能解决）*" 这条特别有用的警告。
3.  即使在多线程环境中使用 `getchar_unlocked()`，只要使用它的线程是唯一访问该文件对象的线程，就没有问题。
4.  与 `getchar()` 的另一个区别是，它不是 C 标准库函数，而是 POSIX 函数。它可能无法在基于 Windows 的编译器上工作。
5.  众所周知，它比 `scanf()` 快，也比 `cin` 快，而 `getchar()` 通常比 `scanf()` 快。`getchar_unlocked()` 比 `getchar()` 更快，所以它是最快的。
6.  类似地，`getc_unlocked()`、`putc_unlocked()` 和 `putchar_unlocked()` 是 `getc()`、`putc()` 和 `putchar()` 的两个非线程安全版本。

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

## 作为练习

读者可以使用 `getchar_unlocked()` 尝试此处给出的解决方案，并使用 `getchar()` 比较性能。

本文由 `Ayush Saluja` 供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论。