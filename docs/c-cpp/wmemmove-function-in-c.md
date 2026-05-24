# wme move()函数在 c++ 中

> 原文:[https://www.geeksforgeeks.org/wmemmove-function-in-c/](https://www.geeksforgeeks.org/wmemmove-function-in-c/)

**wmemmove()** 函数在 **cwchar.h** 头文件中定义。wmemmove()函数将指定数量的宽字符从源复制到目标。
**语法:**

```cpp
wchar_t* wmemmove(wchar_t* dest, const wchar_t* src, size_t n);

```

**参数:**该方法接受以下参数:

*   **dest:** 指定指向目标数组的指针。
*   **src** 指定指向源数组的指针。
*   **n:** 要从 src 复制到 dest 的宽字符数。

**返回:**wmemmove()函数返回修改后的**目的地。**
下面的程序说明了上面的功能:-
**示例:-**

## C++ 14

```cpp
// c++ program to demonstrate
// example of wmemmove() function.
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // Maximum length of the destination string
    wchar_t* dest_buf=L"A computer
                     science portal for geeks";
    wchar_t dest[wcslen(dest_buf)+1];

    // Maximum length of the source string
    wchar_t* src_buf=L"geeksforgeeks";
    wchar_t src[wcslen(src_buf)+1];

    // Initialize the destination string
    wcscpy(dest,dest_buf);

    wprintf(L"Destination: %ls\n", dest);

    // Initialize the source string
    wcscpy(src,src_buf );

    wprintf(L"Source: %ls\n", src);
    wmemmove(dest+2, src+3, 5);
    wprintf(L"After modication, destinstion:
                                   %ls\n", dest);
    return 0;
}
```

**Output:** 

```cpp
Destination: A computer science portal for geeks
Source: geeksforgeeks
After modication, destinstion: A ksforter science portal for geeks

```