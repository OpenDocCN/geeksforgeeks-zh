# wmemcpy()函数在 C/C++ 中

> 原文:[https://www.geeksforgeeks.org/wmemcpy-function-in-c-c/](https://www.geeksforgeeks.org/wmemcpy-function-in-c-c/)

**wmemcpy()** 函数在头文件**cwcchar . h**中指定，并将指定数量的字符从一个字符串复制到另一个字符串。该函数不会检查第一个名为**的字符串中是否有任何终止的空宽字符来源**它总是精确地将 **n** 个字符复制到第二个名为**目的地**的字符串中。

**语法:**

```cpp
wchar_t* wmemcpy( wchar_t* destination, const wchar_t* source, size_t n )
```

**参数:**该功能接受三个强制参数，如下所述:

*   **目的地:**指定要复制字符的指针。
*   **来源:**指定数据所在的指针。
*   **n:** 指定要复制的字符数。

**返回值:**函数返回目标字符串。

以下程序说明了上述功能:

**程序 1 :**

## C++

```cpp
// C++ program to illustrate
// wmemcpy() function

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialize the destination size
    wchar_t destination[20];

    // initialize the source string
    wchar_t source[] = L"geeks are for geeks";

    // till number of characters
    int n = 13;

    // function to copy from source to
    // destination
    wmemcpy(destination, source, n);

    wcout << L"Initial string -> " << source << "\n";

    // print the copied string
    wcout << L"Final string -> ";
    for (int i = 0; i < n; i++)
        putwchar(destination[i]);

    return 0;
}
```

**Output:** 

```cpp
Initial string -> geeks are for geeks
Final string -> geeks are for
```

**程序 2 :**

## C++

```cpp
// C++ program to illustrate
// wmemcpy() function
// when 'n' is equal to the number of
// characters in the source string
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialize the destination size
    wchar_t destination[3];

    // initialize the source string
    wchar_t source[] = L"GFG";

    // till number of characters
    int n = 3;

    // function to copy from source to
    // destination
    wmemcpy(destination, source, n);

    wcout << L"Initial string -> " << source << "\n";

    // print the copied string
    wcout << L"Final string -> ";
    for (int i = 0; i < n; i++)
        putwchar(destination[i]);

    return 0;
}
```

**Output:** 

```cpp
Initial string -> GFG
Final string -> GFG
```