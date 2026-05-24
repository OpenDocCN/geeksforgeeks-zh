# C99 编程语言介绍：第三部分

> 原文：[https://www.geeksforgeeks.org/introduction-to-the-c99-programming-language-part-3/](https://www.geeksforgeeks.org/introduction-to-the-c99-programming-language-part-3/)

在阅读本文之前，请先阅读 C99 编程语言简介（第一部分）和 C99 编程语言简介（第二部分）。

## 1. 新增库函数

C99 提供了一些额外的库函数，如下所列。

它提供了像 `bool`、`true` 和 `false` 这样的宏。

| 库函数 | 用途 |
| --- | --- |
| `complex.h` | `complex.h` 支持复数运算 |
| `fenv.h` | `fenv.h` 允许... |
| `inttypes.h` | `inttypes.h` 支持处理长数字（更宽位数的数字）。它定义了一个标准且可移植的整数名称。 |
| `iso646.h` | `iso646.h` 定义的宏对应于像 `&&` 和 `||` 这样的运算符 |
| `stdint.h` | `stdint.h` 包含在 `inttypes.h` 头文件中。它提供了一套标准且可移植的整数名称。 |
| `tgmath.h` | `tgmath.h` 定义了泛型浮点宏 |
| `wchar.h` | |
| `wctype.h` | `wctype.h` 支持多字节和宽字符分类函数。 |

## 2. 新增格式说明符

在 C99 标准中，`printf()` 和 `scanf()` 函数被修改，使其能够处理 `long long` 和 `unsigned long long` 修饰符。`long long int` 的格式说明符是 `ll`，`unsigned long long int` 的是 `ull`。

下面的示例程序演示了长整型和无符号长整型值的使用。

```cpp
#include<stdio.h>

int main()
{
    long long int a=1121231456;
    unsigned long long int b=1124154632;
    printf("Long Number: %lld and"
    " Unsigned long: %llu",
    a, b);
}
```

## 3. `__func__` 标识符

C99 添加了 `__func__` 标识符，该标识符返回作为字符串调用的函数的名称。简单来说，如果在 `fun1()` 函数中调用了 `__func__`，那么它将返回字符串 `"fun1"`。

## 4. 隐式 int 声明

在 C89 标准中，我们不需要在函数中显式声明整数返回类型，即如果我们声明 `function_name(参数)`，编译器将假定整数为默认返回类型。在 C99 中，不再支持所有隐式函数声明。有些编译器会产生错误，而有些则显示与警告相同的错误。GCC 编译器显示为警告。

## 5. Void 返回类型

在 C89 标准中，我们可以省略函数的返回值。如果我们编写 `int fun1()` 并在不指定返回值的情况下执行，编译器将采用默认返回值自动执行。该值可以是 0 或垃圾值。但是在 C99 中，如果我们写 `int fun1()` 而没有返回语句，那么编译器会将它视为错误。

## 6. 扩展整数类型

C99 标准对整数类型进行了若干扩展。

| 扩展类型 | 含义 |
| --- | --- |
| `int16_t` | 整数正好有 16 位 |
| `int_least16_t` | 整数至少有 16 位。 |
| `int_fast32_t` | 至少有 32 位的最快整数类型。 |
| `intmax_t` | 保存最大整数类型 |
| `uintmax_t` | 保存最大无符号整数类型 |

这些一般很少使用。

这些是一些主要的变化，包括增加、改变和删除 C89 中的功能，以获得 C99 标准。