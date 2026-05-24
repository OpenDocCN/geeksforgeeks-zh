# wcscat()函数在 C++ 中

> 原文:[https://www.geeksforgeeks.org/wcscat-function-in-c/](https://www.geeksforgeeks.org/wcscat-function-in-c/)

**wcscat()** 函数在头文件**cwcchar . h**中指定，该函数用于将一个宽字符串的副本附加到另一个字符串的末尾。

**语法:**

```cpp
wchar_t* wcscat( wchar_t* dest, const wchar_t* src );
```

**参数:**该函数取两个参数:

*   **dest:** Specify a pointer to the destination array.
*   **src:** Specify the string to be added to the destination.

**返回:**该函数返回新的**附加字符串。**

下面的程序说明了上述功能

**例:-**

```cpp
// C++ program to demonstrate
// example of wcscat() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // maximum length of the destination string
    wchar_t dest[30];

    // maximum length of the source string
    wchar_t src[30];

    // initialize the destination string
    wcscpy(dest, L"Geekforgeeks ");

    // initialize the source string
    wcscpy(src, L"is the best");

    wcscat(dest, src);
    wprintf(L"%ls\n", dest);
    return 0;
}
```

**输出:**

```cpp
Geekforgeeks is the best

```