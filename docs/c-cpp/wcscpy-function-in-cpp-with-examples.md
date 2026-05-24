# wcscpy()函数在 C++ 中的应用举例

> 原文:[https://www . geesforgeks . org/wcscpy-function-in-CPP-with-examples/](https://www.geeksforgeeks.org/wcscpy-function-in-cpp-with-examples/)

**wcscpy()** 函数在**cwcchar . h**头文件中定义。wcscpy()函数用于将宽字符串从源复制到目标。

**语法:**

```cpp
wchar_t *wcscpy(wchar_t *dest, const wchar_t *src);
```

**参数:**该方法接受以下两个参数:

*   **dest:** Specify a pointer to the destination array.
*   **src:** Specify a pointer to the source array.

**返回值:**wcscpy()函数返回**修改后的目的地。**

**下面的程序说明了上述功能:-**

**例:-**

```cpp
// C++ program to demonstrate
// example of wcscpy() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{

    // maximum length of the destination string
    wchar_t dest[40];

     // initialize the source string
    wchar_t src[]=L"A computer science portal for geeks";

// Print the source string
    wcout << L"Source: " << src << endl;

// Print the destination string
    wcout << L"Destination: " << dest << endl;

// Copy source to destination
    wcscpy(dest, src);

// Print the modified destination
    wcout << L"After modification, destination: " << dest;

    return 0;
}
```

**输出:**

```cpp
Source: A computer science portal for geeks
Destination: 
After modification, destination: A computer science portal for geeks

```