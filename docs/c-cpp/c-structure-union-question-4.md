# C |结构&联合|问题 4

> 原文:[https://www.geeksforgeeks.org/c-structure-union-question-4/](https://www.geeksforgeeks.org/c-structure-union-question-4/)

考虑以下 C 声明

```cpp
struct { 
    short s[5];
    union { 
         float y; 
         long z; 
    }u; 
} t;
```

假设短、浮点和长类型的对象分别占用 2 字节、4 字节和 8 字节。忽略对齐考虑，变量 t 的内存要求为(GATE CS 2000)

**(A)** 22 字节
**(B)** 14 字节
**(C)** 18 字节
**(D)** 10 字节

**答案:****(C)**
**说明:**短数组 s[5]将取 10 字节作为大小的短为 2 字节。

当我们声明一个联合时，分配给该联合的内存等于它的最大成员所需的内存，并且所有成员共享这个相同的内存空间。由于 u 是一个并集，分配给 u 的内存将是浮点 y(4 字节)和长 z(8 字节)的最大值。因此，总大小将为 18 字节(10 + 8)。

[本题小考](https://www.geeksforgeeks.org/c-language-2-gq/structure-union-gq/)