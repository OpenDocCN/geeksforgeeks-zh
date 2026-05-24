# wcs col()函数在 C++ 中

> 原文:[https://www.geeksforgeeks.org/wcscoll-function-in-c/](https://www.geeksforgeeks.org/wcscoll-function-in-c/)

**wcs col()**函数在 C++ 中比较两个空终止的字符串。该比较基于由 **LC_COLLATE** 类别定义的当前区域设置。
这个函数开始比较每个字符串的第一个字符。它们被认为是相等的，直到字符有所不同，或者直到一个空的宽字符表示到达字符串的末尾。

**语法:**

```cpp
int wcscoll( const wchar_t* wcs1, const wchar_t* wcs2 )
```

**参数:**该功能接受两个强制参数，如下所述:

1.  **wcs1:** 它是指向要比较的空终止宽字符串的指针。
2.  **wcs2:** 它是指向要比较的空终止宽字符串的指针。

**返回值:**该函数返回如下三个值:

1.  0，如果值指示两个字符串相等。
2.  正值，如果 wcs1 中不同的第一个字符大于 wcs2 中相应的字符。
3.  负值，如果 wcs1 中不同的第一个字符小于 wcs2 中相应的字符。

以下程序说明了上述功能:
**程序 1 :**

```cpp
// C++ program to illustrate
// wcsoll() function
#include <bits/stdc++.h>
using namespace std;

// function to compare two strings
void comparetwo(const wchar_t* wcs1, const wchar_t* wcs2)
{
    // pointer wcs1 points string
    // pointer wcs2 points string_
    if (wcscoll(wcs1, wcs2) < 0)
        wcout << wcs1 << L" precedes " << wcs2 << '\n';

    else if (wcscoll(wcs1, wcs2) > 0)
        wcout << wcs2 << L" precedes " << wcs1 << '\n';

    else
        wcout << wcs2 << L" equals " << wcs1 << '\n';
}

int main()
{
    // initializing two strings
    wchar_t string[] = L"article";
    wchar_t string_[] = L"everyone";

    // setting american locale
    setlocale(LC_ALL, "en_US.utf8");
    wcout << L"In American : ";

    // compare two strings with wcs1 and wcs2
    comparetwo(string, string_);

    // setting swedish locale
    setlocale(LC_ALL, "sv_SE.utf8");
    wcout << L"In Swedish : ";
    comparetwo(string, string_);

    return 0;
}
```

**Output:**

```cpp
In American : article precedes everyone
In Swedish : article precedes everyone

```

**程序 2 :**

```cpp
// C++ program to illustrate
// wcsoll() function
#include <bits/stdc++.h>
using namespace std;

// function to compare two strings
void comparetwo(const wchar_t* wcs1, const wchar_t* wcs2)
{
    // pointer wcs1 points string
    // pointer wcs2 points string_
    if (wcscoll(wcs1, wcs2) < 0)
        wcout << wcs1 << L" precedes " << wcs2 << '\n';
    else if (wcscoll(wcs1, wcs2) > 0)
        wcout << wcs2 << L" precedes " << wcs1 << '\n';
    else
        wcout << wcs2 << L" equals " << wcs1 << '\n';
}

int main()
{
    // initializing two strings
    wchar_t string[] = L"geekforgeeks";
    wchar_t string_[] = L"gfg";

    // setting Czech locale
    setlocale(LC_COLLATE, "cs_CZ.utf8");
    wcout << L"In Czech : ";

    // compare two strings with wcs1 and wcs2
    comparetwo(string, string_);

    // setting american locale
    setlocale(LC_COLLATE, "en_US.utf8");
    wcout << "In the American locale: ";
    comparetwo(string, string_);

    return 0;
}
```

**Output:**

```cpp
In Czech : geekforgeeks precedes gfg
In the American locale: geekforgeeks precedes gfg

```