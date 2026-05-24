# c++ 14 中的二进制文字，示例

> 原文:[https://www . geesforgeks . org/binary-lithos-in-C14-with-examples/](https://www.geeksforgeeks.org/binary-literals-in-c14-with-examples/)

在本文中，我们将讨论 C++ 14 中的二进制文字。

在编写涉及数学求值或各种类型数字的程序时，我们通常喜欢用特定的前缀来指定每个数字类型，即 F 或**十六进制数**使用前缀**‘0x’**，对于**八进制数**使用前缀**‘0’**。下面是同样的程序来说明:

**程序 1:**

## c++ 14

```cpp
// C++ program to illustrate the
// Hexadecimal and Octal number
// using literals
#include <iostream>
using namespace std;

// Driver Code
int main()
{
    // Hexadecimal number with
    // prefix '0x'
    int h = 0x13ac;

    // Octal number with prefix '0'
    int o = 0117;

    // Print the number of the
    // hexadecimal form
    cout << h << endl;

    // Print the number of the
    // octal form
    cout << o;

    return 0;
}
```

**输出:**

```cpp
5036
79

```