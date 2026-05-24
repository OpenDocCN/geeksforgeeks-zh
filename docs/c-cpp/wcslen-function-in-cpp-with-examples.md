# wcslen()函数在 C++ 中的使用示例

> 原文:[https://www . geesforgeks . org/wcs len-function-in-CPP-with-examples/](https://www.geeksforgeeks.org/wcslen-function-in-cpp-with-examples/)

**wcslen()** 函数在**cwcchar . h**头文件中定义。函数 wcslen()函数返回给定宽字符串的长度。

**语法:**

```cpp
size_t wcslen(const wchar_t* str);
```

**参数:**此方法采用单个参数**字符串**，该参数表示指向要计算长度的宽字符串的指针。

**返回值:**该函数返回宽字符串的**长度**。

以下程序说明了上述功能

**例 1:-**

```cpp
// c++ program to demonstrate
// example of wcslen() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Get the string to be used
    wchar_t str[] = L"geeks";

    // Get the length of the string using wcslen()
    wcout << L"The length of '" << str
          << L"' is =" << wcslen(str) << endl;

    return 0;
}
```

**输出:**

```cpp
The length of 'geeks' is =5

```

**例 2:-**

```cpp
// c++ program to demonstrate
// example of wcslen() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Get the string to be used
    wchar_t str[] = L"A computer science portal for geeks";

    // Get the length of the string using wcslen()
    wcout << L"The length of '" << str
          << L"' is =" << wcslen(str) << endl;

    return 0;
}
```

**输出:**

```cpp
The length of 'A computer science portal for geeks' is =35

```

=