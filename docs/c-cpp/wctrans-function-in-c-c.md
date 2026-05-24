# wctrans()函数在 C/C++ 中

> 原文:[https://www.geeksforgeeks.org/wctrans-function-in-c-c/](https://www.geeksforgeeks.org/wctrans-function-in-c-c/)

C/C++ 中的这个 **wctrans()** 在头文件**cwcytepe . h**中指定，并返回一个与转换对应的 wctrans_t 类型的值。特定的区域设置可以接受字符的多种转换。以下是一些公认的转型:

*   **“to lower”**->改为小写|[**to lower**](https://www.geeksforgeeks.org/towlower-function-in-c-c/)
*   **“to upper”**->改为大写|[**to upper**](https://www.geeksforgeeks.org/towupper-function-in-c-c/)

**语法:**

```cpp
wctrans_t wctrans( const char* string )
```

**参数:**该函数接受一个强制参数**字符串**，该字符串指定了一个标识字符转换的字符串。
**返回值:**该函数返回如下两个值:

*   如果当前区域设置不提供映射，则返回零。
*   否则，它将返回一个对象，该对象可与 towctrans()一起用于映射宽字符。

以下程序说明了上述功能:
**程序 1 :**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate
// towctrans() function

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialize the string
    wchar_t string[] = L"GeeksForGeeks";
    wcout << L"Initial string -> " << string << endl;

    wctype_t first = wctype("lower");
    wctype_t second = wctype("upper");

    // traverse each character and convert
    // lower case to upper and upper to lower
    for (int i = 0; i < wcslen(string); i++) {
        if (iswctype(string[i], first))
            string[i] = towctrans(string[i], wctrans("toupper"));
        else if (iswctype(string[i], second))
            string[i] = towctrans(string[i], wctrans("tolower"));
    }

    // print the string after transformation
    wcout << L"After transformation -> " << string << endl;

    return 0;
}
```

**Output:** 

```cpp
Initial string -> GeeksForGeeks
After transformation -> gEEKSfORgEEKS
```

**节目 2 :**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate
// towctrans() function

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialize the string
    wchar_t string[] = L"gfg";
    wcout << L"Initial string -> " << string << endl;

    wctype_t first = wctype("lower");
    wctype_t second = wctype("upper");

    // traverse each character and convert
    // lower case to upper and upper to lower
    for (int i = 0; i < wcslen(string); i++) {
        if (iswctype(string[i], first))
            string[i] = towctrans(string[i], wctrans("toupper"));
        else if (iswctype(string[i], second))
            string[i] = towctrans(string[i], wctrans("tolower"));
    }

    // print the string after transformation
    wcout << L"After transformation -> " << string << endl;

    return 0;
}
```

**Output:** 

```cpp
Initial string -> gfg
After transformation -> GFG
```