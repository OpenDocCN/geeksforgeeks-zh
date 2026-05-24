# C 中 size_t 数据类型是什么？

> 原文:[https://www.geeksforgeeks.org/size_t-data-type-c-language/](https://www.geeksforgeeks.org/size_t-data-type-c-language/)

**size_t** 是一种无符号整数数据类型，在各种头文件中定义，如:

```cpp
<stddef.h>, <stdio.h>, <stdlib.h>, <string.h>, <time.h>, <wchar.h>
```

它是一种用于以字节表示对象大小的类型，因此被的**大小[运算符](http://pubs.opengroup.org/onlinepubs/9699919799/basedefs/stddef.h.html)用作返回类型。它保证足够大，以容纳主机系统可以处理的最大对象的大小。基本上，最大允许大小取决于编译器；如果编译器是 32 位，那么它只是一个用于**无符号 int** 的 typedef(即别名)，但是如果编译器是 64 位，那么它将是用于**无符号 long** 的 typedef。 **size_t** 数据类型从不为负。
因此像 *malloc、memcpy 和 strlen* 这样的许多 C 库函数将它们的参数和返回类型声明为 **size_t** 。例如** 

```cpp
// Declaration of various standard library functions.

// Here argument of 'n' refers to maximum blocks that can be
// allocated which is guaranteed to be non-negative.
void *malloc(size_t n);

// While copying 'n' bytes from 's2' to 's1'
// n must be non-negative integer.
void *memcpy(void *s1, void const *s2, size_t n);

// strlen() uses size_t because the length of any string
// will always be at least 0.
size_t strlen(char const *s);
```

**size_t** 或任何无符号类型都可以被视为循环变量，因为循环变量通常大于或等于 0。
**注意:**当我们使用 **size_t** 对象时，我们必须确保在所有使用它的上下文中，包括算术，我们只想要非负值。例如，下面的程序肯定会给出意想不到的结果:

```cpp
// C program to demonstrate that size_t or
// any unsigned int type should be used 
// carefully when used in a loop.
#include<stdio.h>

#define N 10

int main()
{
    int a[N];

    // This is fine.
    for (size_t n = 0; n < N; ++ n) {
        a[n] = n;
    }

    // But reverse cycles are tricky for unsigned 
    // types as they can lead to infinite loops.
    for (size_t n = N-1; n >= 0; --n)
        printf("%d ", a[n]);
}
```

```cpp
Output
Infinite loop and then segmentation fault

```

本文由 [Shubham Bansal](https://www.quora.com/profile/Shubham-Bansal-209) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。