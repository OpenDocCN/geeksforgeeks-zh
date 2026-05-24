# isdigit() 函数详解（C/C++）

> 原文：[https://www.geeksforgeeks.org/isdigit-function-in-c-c-with-examples/](https://www.geeksforgeeks.org/isdigit-function-in-c-c-with-examples/)

`isdigit(c)` 是 [C](https://www.geeksforgeeks.org/c-programming-language/) 中的一个函数，用于检查传递的字符是否是数字。如果是数字，则返回非零值，否则返回 `0`。例如，它为字符 **“0”** 到 **“9”** 返回一个非零值，为其他值返回零。

*   它在 [`ctype.h`](https://www.geeksforgeeks.org/ctype-hcctype-library-in-c-c-with-examples/) [头文件](https://www.geeksforgeeks.org/header-files-in-c-cpp-and-its-uses/)中声明。
*   用于检查输入的字符是否为数字字符 **【0–9】**。
*   它采用整数形式的单个参数，并返回类型为 `int` 的值。
*   即使 `isdigit()` 作为参数，字符也会传递给函数。在内部，字符被转换为其用于检查的 `ASCII` 值。

## 头文件

```cpp
#include <ctype.h>
```

## 语法

```cpp
std::isdigit(int arg)
```

## 参数

`std::isdigit()` 接受整数类型的单个参数。

## 返回类型

该函数根据传递给它的参数返回一个整数值，如果参数是一个数字字符，那么它返回一个**非零值**（真值），否则它返回**零**（假值）。

下面是同样的程序来说明：

## C 语言示例

```cpp
// C program to demonstrate isdigit()
#include <ctype.h>
#include <stdio.h>

// Driver Code
int main()
{
    // Taking input
    char ch = '6';

    // Check if the given input
    // is numeric or not
    if (isdigit(ch))
        printf("\nEntered character is"
               " numeric character");
    else
        printf("\nEntered character is not"
               " a numeric character");
    return 0;
}
```

## C++ 语言示例

```cpp
// C++ program to demonstrate isdigit()
#include <ctype.h>
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    // Taking input
    char ch = '6';

    // Check if the given input
    // is numeric or not
    if(isdigit(ch))
        cout << "\nEntered character is"
             << " numeric character";
    else
        cout << "\nEntered character is not"
             << " a numeric character";
    return 0;
}
```

## 输出

```cpp
Entered character is numeric character
```