# wcs scpn()函数在 C/C++ 中

> 原文:[https://www.geeksforgeeks.org/wcscspn-function-in-c-c/](https://www.geeksforgeeks.org/wcscspn-function-in-c-c/)

C/C++ 中的 **wcscspn()** 函数在给定的宽**字符串 _1** 中搜索第一个出现的宽字符**字符串 _2** 。它返回该宽字符第一次出现之前的宽字符数。搜索包括终止的空宽字符。因此，如果在**字符串 _1** 中没有找到**字符串 _2** 的字符，该函数将返回**字符串 _1** 的长度。

**语法:**

```cpp
size_t wcscspn( const wchar_t* string_1, const wchar_t* string_2 )
```

**参数:**该函数接受两个强制参数，如下所述:

*   **string_1 :** 指定要搜索的字符串
*   **string_2 :** 指定包含要搜索的字符的字符串

**返回值:**该函数返回如下两个值:

*   它返回 string_2 中第一次出现任何宽字符之前的宽字符数。
*   如果在 string_1 中找不到 string_2 中的宽字符，则返回 string_1 的长度

以下程序说明了上述功能:
**程序 1 :**

```cpp
// C++ program to illustrate
// wcscspn() function

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // string to be scanned
    wchar_t string_1[] = L"geeksforgeeks012345";

    // string containing the character to match
    wchar_t string_2[] = L"0123456789";

    // scanning the strings
    int last = wcscspn(string_1, string_2);

    // print the position of a matched character
    if (last > wcslen(string_1))
        wcout << string_1 << L" Didn't match any character";
    else
        wcout << L"Occurrence of a character in -> \n"
              << string_1 << " is at position : " << last;
    return 0;
}
```

**Output:**

```cpp
Occurrence of a character in ->
 geeksforgeeks012345 is at position : 13

```

**程序 2 :**

```cpp
// C++ program to illustrate
// wcscspn() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // string to be scanned
    wchar_t string_1[] = L"GFG";

    // string containing the character to match
    wchar_t string_2[] = L"909090909";

    // scanning the strings
    int last = wcscspn(string_1, string_2);

    // print the position of a matched character
    if (last > wcslen(string_1))
        wcout << string_1 << L" does not contain numbers";
    else
        wcout << L"Length of the string -> "
              << string_1 << " is : " << last;
    return 0;
}
```

**Output:**

```cpp
Length of the string -> GFG is : 3

```