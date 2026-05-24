# 扩展整数类型(在 C/C++ 中选择正确的整数大小)

> 原文:[https://www . geesforgeks . org/extended-integral-type-choice-correct-integer-size-cc/](https://www.geeksforgeeks.org/extended-integral-types-choosing-correct-integer-size-cc/)

C/C++ 对其基本整数数据类型(char、short、int、long 和 long long)的定义非常松散。这种语言保证了它们至少可以表示一定范围的值，但是任何特定的平台(编译器、操作系统、硬件)都可能比这更大。

一个很好的例子很长。在一台机器上，它可能是 32 位(C 语言要求的最小值)。另一个是 64 位。如果你想要一个精确到 32 位的整数类型，你会怎么做？这就是 int32_t 的用武之地:它是特定系统中 32 位整数类型的别名。

模板:

```cpp
intN_t or uintN_t
Where N is width of integer which can be 8, 16, 32, 64
or any other type width supported by the library.

```

```cpp
// C++ program to show use of extended integral types
#include <iostream>
using namespace std;

int main()
{
    uint8_t i;      // i with width of exact 8 bits

    // Minimum value represented by unsigned 8 bit is 0
    i = 0;
    cout << "Minimum value of  i\t: "<< (int)i << endl;

    // Maximum value represented by unsigned 8 bit is 255
    i = 255;
    cout << "Maximum value of i\t: "<< (int)i << endl;

    // Warning: large integer implicitly truncated to
    // unsigned type. It will print any garbage value
    i = 2436;
    cout << "Beyond range value of i\t: " << (int)i << endl;

    return 0;
}
```

输出:

```cpp
 In function 'int main()':
19:7: warning: large integer implicitly truncated to unsigned type [-Woverflow]
     i = 2436;
       ^

Minimum value of  i	: 0
Maximum value of i	: 255
Beyond range value of i	: 132

```

**异变**
1。固定宽度无符号 8 位整数: **uint8_t**
意思是给我一个正好 8 位的无符号整数。

2.最小宽度无符号 8 位整数: **uint_least8_t**
意思是给我最小类型的无符号整数，至少有 8 位。针对内存消耗进行了优化。

3.最快最小宽度无符号 8 位整数: **uint_fast8_t**
它的意思是给我一个至少 8 位的无符号整数，这将使我的程序更快。出于对齐考虑，它可能会选择较大的数据类型。针对速度进行优化。

因此，uint8_t 保证正好是 8 位宽。uint_least8_t 是保证至少 8 位宽的最小整数。uint_fast8_t 是保证至少 8 位宽的最快整数。

所以扩展整型帮助我们编写**便携**和**高效**代码。

本文由**罗希特·卡斯勒**供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。