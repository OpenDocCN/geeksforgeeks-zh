# C 和 C++ 中是否需要“长”数据类型？

> 原文:[https://www.geeksforgeeks.org/need-long-data-type-c-cpp/](https://www.geeksforgeeks.org/need-long-data-type-c-cpp/)

在 [C](https://www.geeksforgeeks.org/c/) 和 [C++ ](https://www.geeksforgeeks.org/c-plus-plus/) 中，有四种不同的数据类型可用于保存整数，即**短、int、long** 和**长**。每种数据类型都需要不同的内存。
但有一个蹊跷的是，**“长”**数据类型的大小并不像其他数据类型那样固定。它因架构、操作系统甚至我们使用的编译器而异。在某些系统中，它的行为类似于 **int** 数据类型或**long**数据类型，如下所示:

```cpp
  OS               Architecture          Size
Windows       IA-32                     4 bytes
Windows       Intel® 64 or IA-64        4 bytes
Linux         IA-32                     4 bytes
Linux         Intel® 64 or IA-64        8 bytes
Mac OS X      IA-32                     4 bytes
Mac OS X      Intel® 64 or IA-64        8 bytes 

```

它也因编译器而异。但在此之前，我们先来了解一下[交叉编译器](https://en.wikipedia.org/wiki/Cross_compiler)的概念。 *交叉编译器是一种能够为运行编译器的平台之外的平台创建可执行代码的编译器。*例如，如果我在运行 64 位 Ubuntu 的 64 位架构中编译以下程序，我将得到如下结果:

## C++

```cpp
// C++ program to check the size of 'long' 
// data type 
#include <bits/stdc++.h>
using namespace std;

int main() 
{ 
    cout << "Size of int = "<< sizeof(int) << endl; 
    cout << "Size of long = " << sizeof(long) << endl; 
    cout << "Size of long long = " << sizeof(long long); 
} 

// This code is contributed by shubhamsingh10
```

## C

```cpp
// C program to check the size of 'long'
//  data type
#include<stdio.h>
int main()
{
    printf("Size of int = %ld\n", sizeof(int));
    printf("Size of long = %ld\n", sizeof(long));
    printf("Size of long long = %ld", sizeof(long long));
}
```

```cpp
Output in 32 bit gcc compiler:-
Size of int = 4
Size of long = 4
Size of long long = 8

Output in 64 bit gcc compiler:-
Size of int = 4
Size of long = 8
Size of long long = 8

```

详见[这篇](https://www.geeksforgeeks.org/compile-32-bit-program-64-bit-gcc-c-c/)文章，了解如何用 32 位或 64 位 gcc 编译器编译程序。

从上面我们得出结论，只有“长”数据类型的大小因编译器而异。现在的问题是这里到底发生了什么？让我们以编译器如何在内部分配内存的方式来讨论它。

中央处理器通过给内存地址寄存器地址从内存中调用数据。找到该位置，并将数据传输到内存数据寄存器。该数据被记录在处理器的一个寄存器中，以供进一步处理。这就是为什么数据总线的大小决定了处理器中寄存器的大小。现在，一个 32 位寄存器一次只能调用 4 字节大小的数据。如果数据大小超过 32 位，则需要两个周期的提取才能将数据放入其中。与 64 位相比，这降低了 32 位机器的速度，64 位只能在一个提取周期内完成操作。因此，很明显，对于较小的数据，如果我的处理器以相同的速度运行，也没有什么区别。编译器旨在为目标机器架构生成最高效的代码。

因此，简而言之，变量的大小取决于编译器，因为它基于目标体系结构和系统体系结构生成指令，而目标体系结构只处理数据总线的大小及其传输。
**注**:有趣的是我们不需要任何“长”数据类型，因为它们的替换(int，long long)已经可以从 [C99](https://en.wikipedia.org/wiki/C99) 标准中获得。

> **建议**:如果整数类型在所有英特尔平台上具有相同的大小对您来说很重要，那么可以考虑将**“长”**替换为**“int”**或**“长”**。对于操作系统、体系结构和编译器的所有上述组合，“int”整数类型的大小是 4 字节，“long long”整数类型的大小是 8 字节。

**参考文献:**
[https://software . Intel . com/en-us/articles/size-of-long-integer-type-on-异架构-os](https://software.intel.com/en-us/articles/size-of-long-integer-type-on-different-architecture-and-os)

本文由 [Shubham Bansal](https://www.quora.com/profile/Shubham-Bansal-209) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。