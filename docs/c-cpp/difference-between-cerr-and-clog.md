# 【cerr 和 clog 的区别

> 原文:[https://www . geesforgeks . org/cerr-and-clog 之间的差异/](https://www.geeksforgeeks.org/difference-between-cerr-and-clog/)

在[中，C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 输入和输出是以字节序列或更常见的流的形式执行的。 [cerr](https://www.geeksforgeeks.org/cerr-standard-error-stream-object-in-cpp/) 和 clog 都与标准 C 误差输出流 stderr 相关联，但是 cerr**T5 是无缓冲的标准误差流，而 clog 是缓冲的标准误差流。在本文中，我们将通过示例详细了解这两种流的区别。**

**cerr:** 用于输出误差的是[无缓冲](https://www.geeksforgeeks.org/difference-between-buffered-and-unbuffered-memory/)标准误差流。这是[牡蛎类](https://www.geeksforgeeks.org/c-stream-classes-structure/)类似于 **cout** 的一个对象。它是无缓冲的，即当需要立即显示错误信息时使用。因为没有缓冲区，所以它不能存储错误消息以供以后显示。所以简单地说 **cerr** 是无缓冲的，它不能存储信息。

**例:**

## c++

```cpp
// c++ program to implement
// the above approach
#include <iostream>
using namespace std;

// Driver code
int main()
{
    cerr << "the message displayed is unbuffered";
    return 0;
}
```