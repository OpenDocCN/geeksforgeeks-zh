# wmemchr()函数在 C/C++ 中

> 原文:[https://www.geeksforgeeks.org/wmemchr-function-in-c-c/](https://www.geeksforgeeks.org/wmemchr-function-in-c-c/)

C/C++ 中的 **wmemchr()** 函数在宽字符块中定位字符。该函数在由 **ptr** 指向的块的第一个**数字**宽字符中搜索第一个出现的 **ch** ，并返回一个指向它的指针。

**语法:**

> const wchar _ t * wmemchr(const wchar _ t * ptr，wchar_t ch，size_t num )
> 或
> wchar_t* wmemchr( wchar_t* ptr，wchar_t ch，size_t num )

**参数:**该功能接受三个强制参数，描述如下:

*   **ptr:** 指定要搜索的字符数组的指针。
*   **ch:** 指定要定位的字符。
*   **num:** 指定要比较的 wchar_t 类型的元素数量。

**返回值:**该函数返回如下两个值:

*   成功后，它返回一个指向字符数组位置的指针。
*   否则，返回空指针。

以下程序说明了上述功能:

**程序-1 :**

## C++

```cpp
// C++ program to illustrate
// wmemchr() function

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialize the string to be scanned
    wchar_t ptr[] = L"GeeksForGeeks";

    // character to be searched for
    wchar_t ch = L'o';

    // length, till the character to be search for is 8
    // run the function to check if the character is present
    bool look = wmemchr(ptr, ch, 8);
    if (look)
        wcout << "'" << ch << "'" << L" is present in first "
              << 8 << L" characters of \"" << ptr << "\"";
    else
        wcout << "'" << ch << "'" << L" is not present in first "
              << 8 << L" characters of \"" << ptr << "\"";

    return 0;
}
```

**Output:** 

```cpp
'o' is present in first 8 characters of "GeeksForGeeks"
```

**程序 2 :**

## C++

```cpp
// C++ program to illustrate
// wmemchr() function

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialize the string to be scanned
    wchar_t ptr[] = L"GFG";

    // character to be searched for
    wchar_t ch = L'p';

    // length, till the character to be search for is 3
    // run the function to check if the character is present
    bool look = wmemchr(ptr, ch, 3);
    if (look)
        wcout << "'" << ch << "'" << L" is present in first "
              << 3 << L" characters of \"" << ptr << "\"";
    else
        wcout << "'" << ch << "'" << L" is not present in first "
              << 3 << L" characters of \"" << ptr << "\"";

    return 0;
}
```

**Output:** 

```cpp
'p' is not present in first 3 characters of "GFG"
```