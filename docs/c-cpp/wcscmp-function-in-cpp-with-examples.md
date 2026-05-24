# wcscmp()函数在 C++ 中的实现，示例

> 原文:[https://www . geesforgeks . org/wcscmp-function-in-CPP-with-examples/](https://www.geeksforgeeks.org/wcscmp-function-in-cpp-with-examples/)

**wcscmp()** 功能在**cwcchar . h**头文件中定义。wcscmp()函数用于比较两个空终止宽字符串，这种比较是按字典顺序进行的。

**语法:**

```cpp
int wcscmp(const wchar_t* str1, const wchar_t* str2);
```

**参数:**该方法取以下两个参数:

*   **STR1:** This means a pointer to the first string to be compared.
*   **STR2:** This indicates the pointer of the second string to be compared.

**返回值:**该方法返回:

*   **零:**如果 str1 和 str2 相同。
*   **正值:**如果 str1 中的第一个不同字符大于 str2 中的对应字符。
*   **负值:**如果 str1 中的第一个不同字符小于 str2 中的对应字符。

**以下程序说明了上述功能:-**

**例 1:-**

```cpp
// c++ program to demonstrate
// example of wcscmp() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialize the str1
    wchar_t str1[] = L"Computer";

    // initialize the str2
    wchar_t str2[] = L"Science";

    // Compare and print results
    wcout << L"Comparing " << str1 << L" and "
          << str2 << L" = " << wcscmp(str1, str2) << endl;

    // Compare and print results
    wcout << L"Comparing " << str2 << L" and "
          << str2 << L" = " << wcscmp(str2, str2) << endl;

    // Compare and print results
    wcout << L"Comparing " << str2 << L" and "
          << str1 << L" = " << wcscmp(str2, str1) << endl;

    return 0;
}
```

**输出:**

```cpp
Comparing Computer and Science = -1
Comparing Science and Science = 0
Comparing Science and Computer = 1

```