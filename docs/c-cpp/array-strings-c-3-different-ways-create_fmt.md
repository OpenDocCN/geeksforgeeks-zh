# C++ 中的字符串数组（5 种不同的创建方式）

> 原文：[https://www.geeksforgeeks.org/array-strings-c-3-different-ways-create/](https://www.geeksforgeeks.org/array-strings-c-3-different-ways-create/)

在 C 和 C++ 中，字符串是一维字符数组，而 C 中的字符串数组是二维字符数组。有许多方法可以声明它们，这里给出了一些有用的方法。

## 1. 使用指针

我们通过创建指针数组来创建字符串数组。

这是 C 和 C++ 都支持的。

```cpp
// C++ program to demonstrate array of strings using
// 2D character array
#include <iostream>

int main()
{
    // Initialize array of pointer
    const char *colour[4] = { "Blue", "Red",
                              "Orange", "Yellow" };

    // Printing Strings stored in 2D array
    for (int i = 0; i < 4; i++)
        std::cout << colour[i] << "\n";

    return 0;
}
```

**输出：**

```
Blue
Red
Orange
Yellow
```

*   字符串的数量是固定的，但并非必须指定。可以省略 `4`，编译器会计算出正确的大小。
*   这些字符串是常量，其内容不能被更改。因为字符串字面量（即带引号的字符串）存在于内存的只读区域，我们必须在这里指定 `const` 来防止可能导致程序崩溃的非法访问。

## 2. 使用二维数组

当已知所有字符串的长度并且需要特定的内存占用时，此方法非常有用。字符串的空间将在单个块中分配。

这在 C 和 C++ 中都支持。

```cpp
// C++ program to demonstrate array of strings using
// 2D character array
#include <iostream>

int main()
{
    // Initialize 2D array
    char colour[4][10] = { "Blue", "Red", "Orange",
                           "Yellow" };

    // Printing Strings stored in 2D array
    for (int i = 0; i < 4; i++)
        std::cout << colour[i] << "\n";

    return 0;
}
```

**输出：**

```
Blue
Red
Orange
Yellow
```

*   字符串的数量和每个字符串的大小都是固定的。同样，可以忽略 `4`，编译器会计算出合适的大小。但是，必须给出第二个维度（本例中是 `10`），以便编译器选择合适的内存布局。
*   每个字符串都可以被修改，但它将占用第二个维度所给出的全部空间。每个字符串在内存中将彼此相邻地排列，且大小无法更改。
*   有时，为了控制内存使用，会采用具有固定和规则布局的内存区域分配方式。

## 3. 使用字符串类

STL [`string`](https://en.cppreference.com/w/cpp/string/basic_string) 类可以用来创建可变字符串的数组。在此方法中，字符串的大小不是固定的，可以更改字符串。

这仅在 C++ 中受支持，因为 C 没有类。

```cpp
// C++ program to demonstrate array of strings using
// array of strings.
#include <iostream>
#include <string>

int main()
{
    // Initialize String Array
    std::string colour[4] = { "Blue", "Red",
                              "Orange", "Yellow" };

    // Print Strings
    for (int i = 0; i < 4; i++)
        std::cout << colour[i] << "\n";
}
```

**输出：**

```
Blue
Red
Orange
Yellow
```