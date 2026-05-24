# C 语言中浮点数中的集合位如何计数？

> 原文:[https://www . geesforgeks . org/count-set-bits-floating-number/](https://www.geeksforgeeks.org/count-set-bits-floating-point-number/)

给定一个[浮点数](http://en.wikipedia.org/wiki/Floating_point)，编写一个函数来计算其二进制表示中的设置位。
例如，0.15625 的浮点表示有 6 个设定位(见[本](http://en.wikipedia.org/wiki/Single_precision#IEEE_754_single-precision_binary_floating-point_format:_binary32))。典型的 C 编译器使用[单精度浮点格式](http://en.wikipedia.org/wiki/Single_precision)。
我们可以用这里[讨论的思路](https://www.geeksforgeeks.org/how-will-you-show-memory-representation-of-c-variables/)。其思想是在指针变量中获取给定浮点数的地址，将指针类型转换为 char *类型，并逐个处理单个字节。我们可以使用这里[和](https://www.geeksforgeeks.org/count-set-bits-in-an-integer/)讨论的技术轻松计算一个字符中的设定位。
以下是上述思路的 C 实现。

## C

```cpp
#include <stdio.h>

// A utility function to count set bits in a char.
// Refer http://goo.gl/eHF6Y8 for details of this function.
unsigned int countSetBitsChar(char n)
{
    unsigned int count = 0;
    while (n)
    {
      n &= (n-1);
      count++ ;
    }
    return count;
}

// Returns set bits in binary representation of x
unsigned int countSetBitsFloat(float x)
{
    // Count number of chars (or bytes) in binary representation of float
    unsigned int n = sizeof(float)/sizeof(char);

    // typecast address of x to a char pointer
    char *ptr = (char *)&x; 

    int count = 0;   // To store the result
    for (int i = 0; i < n; i++)
    {
         count += countSetBitsChar(*ptr);
         ptr++ ;
    }
    return count;
}

// Driver program to test above function
int main()
{
    float x = 0.15625;
    printf ("Binary representation of %f has %u set bits ", x,
             countSetBitsFloat(x));
    return 0;
}
```

**输出:**

```cpp
Binary representation of 0.156250 has 6 set bits
```

本文由**维内特·古普塔**供稿。如果你发现任何不正确的地方，请写评论，或者你想分享更多关于上面讨论的话题的信息