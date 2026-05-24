# C/c++ 中的 INT_MAX 和 INT_MIN 及其应用

> 原文:[https://www . geesforgeks . org/int _ max-int _ min-cc-applications/](https://www.geeksforgeeks.org/int_max-int_min-cc-applications/)

大多数时候，在竞争性编程中，需要分配变量，即数据类型可以容纳的最大值或最小值，但是记住如此大而精确的数字是一项困难的工作。因此，C++ 有某些宏来表示这些数字，这样就可以直接将这些数字赋给变量，而无需实际键入整数。

根据编译器和 C++ 标准，您可能需要在 C 或 C++ 源代码中分别包含头文件***<【limits . h】>***或***<climits>***。所以建议包含这个头文件来使用 INT_MAX、INT_MIN 宏。关于这个头文件的进一步阅读，[参考本文](https://www.geeksforgeeks.org/climits-limits-h-cc/)。

INT_MAX 是一个宏，它指定整数变量不能存储超过这个限制的任何值。
INT_MIN 指定整数变量不能存储低于此限制的任何值。

```cpp
Values of INT_MAX and INT_MIN may vary
from compiler to compiler. Following are
typical values in a compiler where integers
are stored using 32 bits.

Value of INT_MAX is +2147483647.
Value of INT_MIN is -2147483648.
```

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to print values of INT_MAX
// and INT_MIN
#include <bits/stdc++.h>
using namespace std;
int main()
{
    cout << INT_MAX << endl;
    cout << INT_MIN;
    return 0;
}
```

## C

```cpp
// C program to print values of INT_MAX
// and INT_MIN
// we have to include limits.h for results in C
#include <limits.h>
#include <stdio.h>
int main()
{
    printf("%d\n", INT_MAX);
    printf("%d", INT_MIN);
}
```

**Output**

```cpp
2147483647
-2147483648
```