# C/c++

中的 vwprintf()函数

> 原文:[https://www.geeksforgeeks.org/vwprintf-function-in-c-c/](https://www.geeksforgeeks.org/vwprintf-function-in-c-c/)

C++ 中的 **vwprintf()** 函数用于将格式化的宽字符串写入 **stdout** 。它将变量参数列表中的格式化数据打印到 stdout。在内部，该函数从由 **arg** 标识的列表中检索参数，就像在其上使用了 **va_arg** 一样，因此 **arg** 的状态可能会被调用改变。宽字符串格式可能包含以 **%** 开头的格式说明符，这些说明符被作为列表 **vlist** 传递的变量值替换。
在头文件 **<中定义>**
**语法:**

```cpp
int vwprintf( const wchar_t* format, va_list vlist )
```

**参数:**该功能接受四个强制参数，描述如下:

*   **格式:**指定写入 stdout 的空终止宽字符串的指针
*   **arg:** 指定一个值，该值标识用 **va_start** 初始化的变量参数列表

**返回值:**该函数返回如下两个值:

*   成功后，返回写入的字符总数。
*   如果出现错误，则返回负数。

以下程序说明了上述功能:
**程序 1 :**

```cpp
// C++ program to illustrate the
// vwprintf() function
// for some english letter

#include <bits/stdc++.h>
using namespace std;

// function to print formatted
// data from variable argument list to stdout
void write(const wchar_t* format, ...)
{
    // hold the variable argument
    va_list arg;

    // A function that invokes va_start
    // shall also invoke va_end before it returns.
    va_start(arg, format);

    vwprintf(format, arg);
    va_end(arg);
}

// Driver code
int main()
{
    setlocale(LC_ALL, "en_US.UTF-8");

    wchar_t buffer[5][10] = { L"First", L"Second", L"Third",
                              L"Fourth", L"Fifth" };
    int k = 0;

    // print letters by calling write function
    wprintf(L"Some English Letters\n");
    for (wchar_t i = L'A'; i <= L'E'; i++) {
        write(L"%ls : %lc\n", buffer[k], i);
        k++ ;
    }

    return 0;
}
```

**Output:**

```cpp
Some English Letters
First : A
Second : B
Third : C
Fourth : D
Fifth : E

```

```cpp
// C++ program to illustrate the
// vwprintf() function
// for some Latin letters
#include <bits/stdc++.h>
using namespace std;

// function to print formatted
// data from variable argument list to stdout
void write(const wchar_t* format, ...)
{
    // hold the variable argument
    va_list arg;

    // A function that invokes va_start
    // shall also invoke va_end before it returns.
    va_start(arg, format);

    vwprintf(format, arg);
    va_end(arg);
}

// Driver code
int main()
{
    setlocale(LC_ALL, "en_US.UTF-8");

    wchar_t buffer[5][10] = { L"First", L"Second", L"Third",
                              L"Fourth", L"Fifth" };
    int k = 0;

    // print letters by calling write function
    wprintf(L"Some Latin Letters\n");
    for (wchar_t i = L'\u0021'; i <= L'\u0025'; i++) {
        write(L"%ls : %lc\n", buffer[k], i);
        k++ ;
    }

    return 0;
}
```

**Output:**

```cpp
Some Latin Letters
First : !
Second : "
Third : #
Fourth : $
Fifth : %

```