# wcs HR()函数在 C++ 中

> 原文:[https://www.geeksforgeeks.org/wcschr-function-in-c/](https://www.geeksforgeeks.org/wcschr-function-in-c/)

**wcschr()** 函数在 C++ 中搜索宽字符串中第一次出现的宽字符。终止的空宽字符被认为是字符串的一部分。因此，也可以定位它，以便检索指向宽字符串末尾的指针。

**语法:**

```cpp
const wchar_t* wcschr (const wchar_t* ws, wchar_t wc)
      wchar_t* wcschr (      wchar_t* ws, wchar_t wc)

```

**参数:**该功能接受两个强制参数，如下所述:

1.  **ws:** 指向要搜索的空终止宽字符串的指针
2.  **wc:** 待定位的宽字符

**返回值:**该函数返回如下两个值:

1.  指向字符串中第一个字符的指针。
2.  如果找不到字符，函数将返回空指针。

以下程序说明了上述功能:
**程序 1 :**

```cpp
// C++ program to illustrate
// wcschr() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialize wide string
    wchar_t ws[] = L"This is some good coding";

    wchar_t* point;
    wprintf(L"Looking for the 'o' character in \"%ls\"...\n", ws);

    // initialize the search character
    point = wcschr(ws, L'o');

    // search the place and print
    while (point != NULL) {
        wprintf(L"found at %d\n", point - ws + 1);
        point = wcschr(point + 1, L'o');
    }

    return 0;
}
```

**Output:**

```cpp
Looking for the 'o' character in "This is some good coding"...
found at 10
found at 15
found at 16
found at 20

```

**程序 2 :**

```cpp
// C++ program to illustrate
// wcschr() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialize wide string
    wchar_t ws[] = L"geekforgeeks";

    wchar_t* point;
    wprintf(L"Looking for the 'g' character in \"%ls\"...\n", ws);

    // initialize the search character
    point = wcschr(ws, L'g');

    // search the place and print
    while (point != NULL) {
        wprintf(L"found at %d\n", point - ws + 1);
        point = wcschr(point + 1, L'g');
    }

    return 0;
}
```

**Output:**

```cpp
Looking for the 'g' character in "geekforgeeks"...
found at 1
found at 8

```