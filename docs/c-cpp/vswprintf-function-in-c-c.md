# C/c++ 中的 vswprintf()函数

> 原文:[https://www.geeksforgeeks.org/vswprintf-function-in-c-c/](https://www.geeksforgeeks.org/vswprintf-function-in-c-c/)

此 **vswprintf()** 函数将宽字符串写入宽字符串缓冲区。最大 **(len-1)** 宽字符被写入缓冲区，缓冲区后面是空宽字符。

**语法:**

> int vswprintf( wchar_t* ws，size_t len，const wchar_t* format，va_list arg)

**参数:**该功能接受四个强制参数，描述如下:

*   **ws:** 指定指向给定宽字符串缓冲区的指针，该缓冲区将存储结果
*   **len:** 指定写回缓冲区的宽字符的最大长度，包括终止的空字符
*   **格式:**指定指向空终止宽字符串的指针
*   **arg:** 指定标识变量参数列表的值

**注:**所有格式说明符的含义与 **printf** 相同，因此 **%lc** 用于写宽字符(而非 **%c** )，宽字符串使用 **%ls** (而非 **%s** )。

**返回值:**该函数返回如下两个值:

*   成功后，vswprintf()函数返回写入的宽字符数，不包括终止的空宽字符。
*   失败时返回负数，包括写入 ws 的结果字符串将超过 n 个字符。

以下程序说明了上述功能:
**程序 1 :**

```cpp
// C++ program to illustrate the
// vswprintf() function
#include <bits/stdc++.h>
using namespace std;

// function to check the number
// of wide characters written
void find ( wchar_t* ws, size_t len, const wchar_t *format, ... )
{
    // hold the variable argument
    va_list arg;

    // A function that invokes va_start
    // shall also invoke va_end before it returns.
    va_start ( arg, format );

    vswprintf ( ws, len, format, arg );

    va_end ( arg );
}

// Driver code
int main ()
{
    // buffer with size 60 
    wchar_t ws[60];

    // initializing the string as latin characters
    wchar_t str[] = L"\u0025 \u0026 \u0027 \u0028 \u0029";

    // print the letters
    find(ws, 60, L"Some Latin letters : %ls\n", str);
    wprintf(L" %ls ", ws);

    return 0;
}
```

**Output:**

```cpp
Some Latin letters : % & ' ( )

```

**程序 2 :**

```cpp
// C++ program to illustrate the
// vswprintf() function
// When the size of the buffer is smaller
// than the total length of the string written 
#include <bits/stdc++.h>
using namespace std;

// function to check the number
// of wide characters written
void find ( wchar_t* ws, size_t len, const wchar_t *format, ... )
{
    // hold the variable argument
    va_list arg;

    // A function that invokes va_start
    // shall also invoke va_end before it returns.
    va_start ( arg, format );

    vswprintf ( ws, len, format, arg );

    va_end ( arg );
}

// Driver code
int main ()
{
    // initializing the string as english characters
    wchar_t str[] = L"Geek for geeks";

    // buffer with size 20 
    wchar_t ws[20];

        find(ws, 20, L"GFG is : %ls\n", str);
    wprintf(L"%ls", ws);

    return 0;
}
```

**Output:**

```cpp
GFG is : Geek for g

```

**注意:**如果生成的字符串长度超过 n-1 个字符，剩余的字符将被丢弃并且不被存储。