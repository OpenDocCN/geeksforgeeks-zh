# C/c++ 中的 vswscanf()函数

> 原文:[https://www.geeksforgeeks.org/vswscanf-function-in-c-c/](https://www.geeksforgeeks.org/vswscanf-function-in-c-c/)

C++ 中的 **vfwscanf()** 函数用于将格式化数据从宽字符串读入变量参数列表。它还从宽字符串缓冲区读取宽字符串。该函数从 **ws** 读取数据，并根据**格式**将其存储到由 **arg** 标识的变量参数列表中的元素所指向的位置。
在 **<cwchar.h></cwchar.h>**库文件中定义。

**语法:**

```cpp
int vswscanf( const wchar_t* ws, const wchar_t* format, va_list arg )
```

**参数:**该功能接受三个强制参数，描述如下:

*   **ws :** 指向空终止宽字符串的指针，用于读取数据
*   **格式:**指向指定如何读取输入的空终止宽字符串的指针
*   **arg :** 标识用 va_start 初始化的变量参数列表的值。

**返回值:**该函数返回如下两个值:

*   成功时，它返回成功读取的参数数。
*   失败时，返回**电渗流**

以下程序说明了上述功能:
**程序 1 :**

```cpp
// C++ program to illustrate the
// vswscanf() function
#include <bits/stdc++.h>
using namespace std;

// ws : pointer to the wide string
// format : to read the input
void wideMatch(const wchar_t* ws, const wchar_t* format, ...)
{
    va_list arg;

    // A function that invokes va_start
    // shall also invoke va_end before it returns.
    va_start(arg, format);

    // vswscanf() reads formatted data from wide
    // string into variable argument list
    vswscanf(ws, format, arg);
    va_end(arg);
}

// Driver code
int main()
{
    setlocale(LC_ALL, "en_US.UTF-8");

    // initialize the buffer
    wchar_t wideS[] = L"GFG";
    wchar_t string[20];

    wideMatch(wideS, L"%ls", string);
    wprintf(L"Random Symbols are :\n");

    // print all the symbols
    for (int i = 0; i < wcslen(string); i++) {
        putwchar(string[i]);
        putwchar(' ');
    }

    return 0;
}
```

**Output:**

```cpp
Random Symbols are :
G F G

```

**程序 2 :**

```cpp
// C++ program to illustrate the
// vswscanf() function

#include <bits/stdc++.h>
using namespace std;

void WideString(const wchar_t* ws, const wchar_t* format, ...)
{
    va_list arg;
    // A function that invokes va_start
    // shall also invoke va_end before it returns.
    va_start(arg, format);

    // vswscanf() reads formatted data from wide
    // string into variable argument list
    vswscanf(ws, format, arg);
    va_end(arg);
}

// Driver code
int main()
{
    int value;

    // initialize the buffer
    wchar_t wideS[] = L"100 websites of GeekforGeeks";

    WideString(wideS, L" %d %ls ", &value, wideS);

    // print all the symbols
    wprintf(L"Best: %ls\nQuantity: %d\n", wideS, value);

    return 0;
}
```

**Output:**

```cpp
Best: websites
Quantity: 100

```