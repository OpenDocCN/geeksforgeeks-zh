# wcsncat()函数在 C/C++ 中

> 原文:[https://www.geeksforgeeks.org/wcsncat-function-in-c-c/](https://www.geeksforgeeks.org/wcsncat-function-in-c-c/)

**wcsncat()** 函数将**源**的字符追加到**目的地**中，包括一个终止的空宽字符。如果**源**中的字符串长度小于**数**。则仅复制直到终止空宽字符的内容。

**语法:**

```cpp
wchar_t* wcsncat (wchar_t* destination, const wchar_t* source, size_t num)
```

**参数:**该功能接受三个强制参数，描述如下:

*   **目标:**指定指向目标数组的指针
*   **来源:**指定要添加到目的地的字符串
*   **num:** 指定要添加的最大字符数

**返回值:**该功能返回**目的地**。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate
// wcsncat() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // maximum length of the destination string
    wchar_t destination[20];

    // maximum length of the source string
    wchar_t source[20];

    // initialize the destination string
    wcscpy(destination, L"Geekforgeeks ");

    // initialize the source string
    wcscpy(source, L"is the best");

    // initialize the length of
    // the resulted string you want
    wcsncat(destination, source, 20);
    wprintf(L"%ls\n", destination);
    return 0;
}
```

**Output:**

```cpp
Geekforgeeks is the best

```

**程序 2 :**

```cpp
// C++ program to illustrate
// wcsncat() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // maximum length of the destination string
    wchar_t destination[40];

    // maximum length of the source string
    wchar_t source[40];

    // initialize the destination string
    wcscpy(destination, L"only some of the  ");

    // initialize the source string
    wcscpy(source, L"letters will be copied");

    // initialize the length of
    // the resulted string you want
    wcsncat(destination, source, 20);
    wprintf(L"%ls\n", destination);
    return 0;
}
```

**Output:**

```cpp
only some of the  letters will be copi

```