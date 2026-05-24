# wmemcmp()函数在 C/C++ 中

> 原文:[https://www.geeksforgeeks.org/wmemcmp-function-in-c-c/](https://www.geeksforgeeks.org/wmemcmp-function-in-c-c/)

C/C++ 中的 **wmemcmp()** 函数比较两个宽字符。该函数比较由 **str1** 和 **str2** 指向的两个宽字符的第一个**数字**宽字符，如果两个字符串的值相等或不相等，则返回零。

**语法:**

> int wmemcmp (const wchar_t* str1，const wchar_t* str2，size _ t num)；

**参数:**

*   **str1:** 指定指向第一个字符串的指针。
*   **str2:** 指定指向第二个字符串的指针。
*   **num:** 指定要比较的字符数。

**返回值:**这个函数返回三个不同的值，定义了两个字符串之间的关系:

*   *零*:两串相等时。
*   *正值*:当两个字符串中不匹配的第一个宽字符在 str1 中的出现频率大于 str2 中的出现频率时。
*   *负值*:当两个字符串中不匹配的第一个宽字符在 str1 中的出现频率低于 str2 时

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate
// wmemcmp() function

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialize two strings
    wchar_t str1[] = L"geekforgeeks";
    ;
    wchar_t str2[] = L"geekforgeeks";

    // this function will compare these two strings
    // till 12 characters, if there would have been
    // more than 12 characters, it will compare
    // even more than the length of the strings
    int print = wmemcmp(str1, str2, 12);

    // print if it's equal or not equal( greater or smaller)
    wprintf(L"wmemcmp comparison: %ls\n",
            print ? L"not equal" : L"equal");

    return 0;
}
```

**Output:**

```cpp
wmemcmp comparison: equal

```

**程序 2:**

```cpp
// C++ program to illustrate
// wmemcmp() function
// Comparing two strings with the same type of function
// wcsncmp() and wmemcmp()
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialize two strings
    wchar_t str1[] = L"geekforgeeks";
    ;
    wchar_t str2[] = L"geekforgeeks";

    // wcsncmp() function compare characters
    // until the null character is encountered ('\0')
    int first = wcsncmp(str1, str2, 20);

    // but wmemcmp() function compares 20 characters
    // even after encountering null character
    int second = wmemcmp(str1, str2, 20);

    // print if it's equal or not equal( greater or smaller)
    wprintf(L"wcsncmp comparison: %ls\n",
            first ? L"not equal" : L"equal");
    wprintf(L"wmemcmp comparison: %ls\n",
            second ? L"not equal" : L"equal");

    return 0;
}
```

**Output:**

```cpp
wcsncmp comparison: equal
wmemcmp comparison: not equal

```