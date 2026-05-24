# wcsrgrams()在 C/C++ 中的功能

> 原文:[https://www.geeksforgeeks.org/wcsrtombs-function-in-c-c/](https://www.geeksforgeeks.org/wcsrtombs-function-in-c-c/)

**wcsrgrams()**函数将宽字符转换为多字节字符串。该函数将 ***src** 表示的宽字符串转换为对应的多字节字符串，如果 **dest** 不为空，则存储在 **dest** 指向的字符数组中。最多将**个字符写入**目的地**。
**语法:**** 

> size _ t wcs rrums(char * dest，const wchar_t** src，size_t len，mbstate_t* ps)

**参数:**该功能接受四个强制参数，描述如下:

*   **dest :** 指向字符元素数组的指针，该数组的长度足以存储最大字节串
*   **src :** 指向要翻译的宽字符串的指针
*   **len:**dest 数组中可用的最大字节数
*   **ps :** 指向转换状态对象的指针

**返回值:**该函数返回如下两个值:

*   成功后，它返回写入 dest 的字节数(不包括最终终止的空字符)
*   如果出现一些错误，则返回-1，并将 errno 设置为 **EILSEQ** 。

以下程序说明了上述功能:
**程序 1:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate
// wcsrtombs() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize the string
    const wchar_t* src = L"Geekforgeeks";

    // maximum length of the dest
    char dest[20];

    // initial state
    mbstate_t ps = mbstate_t();

    // maximum length of multibyte character
    int len = 12;

    // function to convert wide-character
    // to multibyte string
    int value = wcsrtombs(dest, &src, len, &ps);

    cout << "Number of multibyte characters = " << value << endl;

    cout << "Multibyte characters written = " << dest << endl;

    return 0;
}
```

**Output:** 

```cpp
Number of multibyte characters = 12
Multibyte characters written = Geekforgeeks
```

**节目 2:**

## 卡片打印处理机（Card Print Processor 的缩写）

```cpp
// C++ program to illustrate
// wcsrtombs() function
#include <bits/stdc++.h>
using namespace std;

int main()
{

    // initialize the string
    const wchar_t* src = L"This website is the best";

    // maximum length of the dest
    char dest[20];

    // initial state
    mbstate_t ps = mbstate_t();

    // maximum length of multibyte character
    int len = 14;

    // function to convert wide-character
    // to multibyte string
    int value = wcsrtombs(dest, &src, len, &ps);

    cout << "Number of multibyte characters = " << value << endl;

    cout << "Multibyte characters written = " << dest << endl;

    return 0;
}
```

**Output:** 

```cpp
Number of multibyte characters = 14
Multibyte characters written = This website i
```