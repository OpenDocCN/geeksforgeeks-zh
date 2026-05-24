# 在 C 和 C++ 中将变量声明为常量的不同方式

> 原文：`https://www.geeksforgeeks.org/different-ways-declare-variable-constant-c-c/`

有许多不同的方法使变量成为常数。

## 1. 使用 `const` 关键字
`const` 关键字指定变量或对象值是常量，在编译时不能修改。

```cpp
// C program to demonstrate const specifier
#include <stdio.h>
int main()
{
    const int num = 1;
    num = 5; // Modifying the value
    return 0;
}
```

它将抛出一个错误，例如：
```
error: assignment of read-only variable ‘num’
```

## 2. 使用 `enum` 关键字
枚举（或 `enum`）是 C 和 C++ 中的一种用户定义数据类型。它主要用于为整型常量赋予名称，使程序易于阅读和维护。

```cpp
// In C and C++ internally the default
// type of 'var' is int
enum VARS { var = 42 };

// In C++ 11 (can have any integral type):
enum : type { var = 42; }
// where mytype = int, char, long etc.
// but it can't be float, double or
// user defined data type.
```

**注意：** `枚举`的数据类型当然是有限的，正如我们在上面的例子中看到的。

## 3. 使用 `constexpr` 关键字
在 C++（而非 C）中使用 `constexpr` 可以声明变量为有保证的常量。但如果其初始值设定项不是常量表达式，则编译会失败。

```cpp
#include <iostream>
int main()
{
    int var = 5;
    constexpr int k = var;
    std::cout << k;
    return 0;
}
```

上述程序将抛出一个错误：

```
error: the value of ‘var’ is not usable in a constant expression
```

因为变量 `var` 不是常量表达式。因此，为了使它成为常数，我们必须用 `const` 关键字声明变量 `var`。

## 4. 使用宏
我们也可以使用宏来定义常量，但是有一个陷阱。

```cpp
#define var 5
```