# c++ 中的字符串数组(5 种不同的创建方式)

> 原文:[https://www . geesforgeks . org/array-strings-c-3-differential-way-create/](https://www.geeksforgeeks.org/array-strings-c-3-different-ways-create/)

在 C 和 C++ 中，字符串是一维字符数组，而 C 中的字符串数组是二维字符数组。有许多方法可以声明它们，这里给出了一些有用的方法。

## **1。使用指针:**

我们通过创建指针数组来创建字符串数组。

这是 C 和 C++ 都支持的。

## CPP

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

**输出:**

```cpp
Blue
Red
Orange
Yellow
```

*   The number of strings is fixed, but it is not needed. 4 can be omitted, and the compiler will calculate the correct size.
*   These strings are constants and their contents cannot be changed. Because string literals (literally, quoted strings) exist in the read-only area of memory, we must specify "const" here to prevent unnecessary access that may cause the program to crash.

## **2。使用 2D 阵列:**

当已知所有字符串的长度并且需要特定的内存占用时，此方法非常有用。字符串的空间将在单个块中分配

这在 C 和 C++ 中都支持。

## CPP

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

**输出:**

```cpp
Blue
Red
Orange
Yellow
```

*   Both the number of strings and the size of strings are fixed. Similarly, 4 may be ignored, and the compiler will calculate the appropriate size. However, the second dimension (10 in this example) must be given so that the compiler can choose the appropriate memory layout.
*   Each string can be modified, but it will take up all the space given by the second dimension. Each one will be laid out next to each other in memory, and the size cannot be changed.
*   Sometimes, it is advisable to control memory usage, which will allocate a memory area with a fixed and regular layout.

## **3。使用字符串类:**

STL [字符串](https://en.cppreference.com/w/cpp/string/basic_string)类可以用来创建可变字符串的数组。在此方法中，字符串的大小不是固定的，可以更改字符串。

这仅在 C++ 中受支持，因为 C 没有类。

## CPP

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

**输出:**

```cpp
Blue
Red
Orange
Yellow
```