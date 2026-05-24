# mbsrtowcs()函数在 C/C++ 中

> 原文:[https://www.geeksforgeeks.org/mbsrtowcs-function-in-c-c/](https://www.geeksforgeeks.org/mbsrtowcs-function-in-c-c/)

C/C++ 中的 **mbsrtowcs(** )函数将窄的多字节字符序列转换为宽的字符序列。它将第一个字节由 ***src** 表示的多字节字符串转换为相应的宽字符表示，并存储在由 **dest** 指向的宽字符数组中。最大 **len** 宽字符被写入 **dest** 。

**语法:**

```cpp
size_t mbsrtowcs( wchar_t* dest, const char** src, size_t len, mbstate_t* ps )
```

**参数:**该功能接受四个强制参数，描述如下:

*   **dest :** 指定指向存储转换后宽字符的数组的指针
*   **ps :** 指定转换状态对象的指针
*   **src :** 指定指向要转换的第一个多字节字符的指针
*   **len :** 指定要存储的最大字符宽度

**返回值:**该函数返回如下两个值:

*   mbsrtowcs()函数返回写入 dest 的宽字符数，成功时不包括终止的宽 null 字符。
*   如果 dest 是一个空指针，它将返回考虑到无限长时应该写入的宽字符数。
*   on conversion error, -1 is returned and errno is set to **EILSEQ**

    。

**注意:**该函数将 src 指针移动到转换后的多字节字符串的末尾。如果**dst = =空**，这不会发生

以下程序说明了上述功能:
**程序 1 :**

```cpp
// C++ program to illustrate 
// mbsrtowcs function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    setlocale(LC_ALL, "en_US.utf8");

    // initializing the string
    // narrow multibyte character sequence
    const char* src = "\u0763\u0757";
    wchar_t dest[20];

    // initial state
    mbstate_t ps = mbstate_t();

    // maximum number of wide character
    int max = 10;

    int retVal = mbsrtowcs ( dest, &src, max, &ps );
    wcout << L"Number of wide characters written = "
          << retVal << endl;

    wcout << L"Wide character = " << dest << endl;

    return 0;
} 
```

**Output:**

```cpp
Number of wide characters written = 2
Wide character = Ý£Ý?

```

**程序 2 :**

```cpp
// C++ program to illustrate 
// mbsrtowcs function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // set locale
    setlocale(LC_ALL, "en_US.utf8");

    // initializing the string
    // narrow multibyte character sequence
    const char* src = u8"z\u00df\u6c34\U0001f34c";
    wchar_t dest[20];

    // initial state
    mbstate_t ps = mbstate_t();

    // maximum number of wide character
    int max = 10;

    int retVal = mbsrtowcs ( dest, &src, max, &ps );
    wcout << L"Number of wide characters written  = "
          << retVal << endl;

    wcout << L"Wide character = " << dest << endl;

    return 0;
}
```

**Output:**

```cpp
Number of wide characters written  = 4
Wide character = zÃ?æ°´ð??

```