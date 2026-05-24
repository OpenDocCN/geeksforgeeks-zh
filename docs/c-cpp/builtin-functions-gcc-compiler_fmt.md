# GCC 编译器的内置函数

> 原文：[https://www.geeksforgeeks.org/builtin-functions-gcc-compiler/](https://www.geeksforgeeks.org/builtin-functions-gcc-compiler/)

这是 GCC 编译器中四个重要的内置函数：

## `__builtin_popcount(x)`

此函数用于计算一个整数中 1 的数量（设置位）。

**例：**

```cpp
if x = 4
binary value of 4 is 100
Output: No of ones is 1.
```

### C

```cpp
// C program to illustrate __builtin_popcount(x)

#include <stdio.h>
int main()
{
    int n = 5;

    printf("Count of 1s in binary of %d is %d ",
           n, __builtin_popcount(n));
    return 0;
}
```

**输出：**

```cpp
Count of 1s in binary of 5 is 2
```

**注意：** 同样，您可以使用 `__builtin_popcountl(x)` 和 `__builtin_popcountll(x)` 来处理长数据类型和长长数据类型。

## `__builtin_parity(x)`

该功能用于检查一个数字的[奇偶校验](https://www.geeksforgeeks.org/program-to-find-parity/)。这个函数返回真（1），如果这个数字有奇数个 1，否则它返回假（0）表示偶数个 1。

**例：**

```cpp
if x = 7
7 has odd no. of 1's in its binary(111).
Output: Parity of 7 is 1
```

### C

```cpp
// C program to illustrate __builtin_parity(x)

#include <stdio.h>
int main()
{
    int n = 7;

    printf("Parity of %d is %d ",
           n, __builtin_parity(n));
    return 0;
}
```

**输出：**

```cpp
Parity of 7 is 1
```

**注意：** 同样，您可以使用 `__builtin_parityl(x)` 和 `__builtin_parityll(x)` 来处理长数据类型和长长数据类型。

## `__builtin_clz(x)`

此函数用于计算整数的前导零。注意：`clz` = 计算前导零的数量。

**示例：** 它计算第一次出现 1（设置位）之前的零的数量。

```cpp
a = 16
Binary form of 16 is 00000000 00000000 00000000 00010000
Output: 27
```

### C

```cpp
// C program to illustrate __builtin_clz(x)
#include <stdio.h>
int main()
{
    int n = 16;

    printf("Count of leading zeros before 1 in %d is %d",
           n, __builtin_clz(n));
    return 0;
}
```

**输出：**

```cpp
Count of leading zeros before 1 in 16 is 27
```

**注意：** `__builtin_clz(x)` 这个函数只接受无符号的值。
**注意：** 同样你可以使用 `__builtin_clzl(x)` 和 `__builtin_clzll(x)` 来表示长的和长长的数据类型。

## `__builtin_ctz(x)`

此函数用于计算给定整数的尾随零。注意：`ctz` = 计算尾随零。

**示例：** 从最低有效位到第一次出现 1（设置位）计算零的数量。

```cpp
a = 16
Binary form of 16 is 00000000 00000000 00000000 00010000
Output: ctz = 4
```

### C

```cpp
// C program to illustrate __builtin_ctz(x)
#include <stdio.h>
int main()
{
    int n = 16;

    printf("Count of zeros from last to first "
           "occurrence of one is %d",
           __builtin_ctz(n));
    return 0;
}
```

**输出：**

```cpp
Count of zeros from last to first occurrence of one is 4
```

**注意：** 同样，您可以使用 `__builtin_ctzl(x)` 和 `__builtin_ctzll(x)` 来处理长数据类型和长长数据类型。