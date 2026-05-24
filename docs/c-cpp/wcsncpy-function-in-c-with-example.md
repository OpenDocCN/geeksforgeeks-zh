# wcsncpy()函数在 C++ 中用示例

> 原文:[https://www . geeksforgeeks . org/wcsncpy-function-in-c-with-example/](https://www.geeksforgeeks.org/wcsncpy-function-in-c-with-example/)

**wcsncpy()** 函数在**cwcchar . h**头文件中定义。wcsncpy()函数将指定数量的宽字符从源复制到目标。

**语法:**

```cpp
wchar_t *wcsncpy(wchar_t *dest, 
                 const wchar_t *src, 
                 size_t n);

```

**参数:**该方法接受以下三个参数:

*   **dest:** 指定指向目标数组的指针。
*   **src:** 指定指向源数组的指针。
*   **n:** 代表要复制的字符数。

**返回值:**该函数返回修改后的目的地。

以下程序说明了上述功能

**例 1:**

```cpp
// c++ program to demonstrate
// example of wcsncpy() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialize the source string
    wchar_t src[] = L"A Computer Science portal for geeks";

    // maximum length of the destination string
    wchar_t dest[40];

    // copy the source to destination using wcsncpy
    wcsncpy(dest, src, 19);

    // Print the copied destination
    wcout << "Destination string is : " << dest;

    return 0;
}
```

**Output:**

```cpp
Destination string is : A Computer Science

```

**实施例 2:-**

```cpp
// c++ program to demonstrate
// example of wcsncpy() function.

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialize the source string
    wchar_t src[] = L"GeeksforGeeks";

    // maximum length of the destination string
    wchar_t dest[40];

    // copy the source to destination using wcsncpy
    wcsncpy(dest, src, 5);

    // Print the copied destination
    wcout << "Destination string is : " << dest;

    return 0;
}
```

**Output:**

```cpp
Destination string is : Geeks

```