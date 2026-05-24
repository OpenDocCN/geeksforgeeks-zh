# wcsncmp()函数在 C/C++ 中

> 原文:[https://www.geeksforgeeks.org/wcsncmp-function-in-c-c/](https://www.geeksforgeeks.org/wcsncmp-function-in-c-c/)

C/C++ 中的 **wcsncmp()** 函数比较两个宽字符串的字符。比较是按字典顺序进行的。该函数接受三个参数 **lhs** 、 **rhs** 和 **count** 。它将 **lhs** 和 **rhs** 的内容按字典顺序进行比较，最大计数为宽字符。

**注意:**如果 **lhs** 或 **rhs** 没有指向空终止的宽字符串，则 **wcsncmp()** 的行为未定义。

**语法:**

```cpp
int wcsncmp( const wchar_t* lhs, const wchar_t* rhs, size_t count )
```

**参数:**该功能接受三个强制参数，如下所述:

*   **lhs :** 要比较的字符串
*   **rhs :** 要比较的字符串
*   **计数:**要比较的最大字符数

**返回值:**该函数返回如下三个值:

*   **正值:**如果 lhs 中的第一个不同字符大于 rhs 中的相应字符。
*   **负值:**如果 lhs 中的第一个不同字符小于 rhs 中的相应字符。
*   **零:**如果两个字符串中比较的字符构成相同的字符串。

以下程序说明了上述功能:
**程序 1 :**

```cpp
// C++ program to illustrate the
// wcsncmp() function
#include <bits/stdc++.h>
using namespace std;

// function to compare two strings
void check(wchar_t* lhs, wchar_t* rhs, int count)
{
    int result;
    // compare lhs and rhs by wcsncmp
    result = wcsncmp(lhs, rhs, count);

    // print, as per result
    if (result < 0)
        wcout << lhs << " precedes " << rhs << "\n";
    else if (result > 0)
        wcout << rhs << " precedes " << lhs << "\n";
    else
        wcout << L"First " << count << L" characters of "
              << L" are same"
              << "\n";
}

// Driver code
int main()
{
    // initialize two strings lhs and rhs to compare
    wchar_t lhs[] = L"geekforgeeks";
    wchar_t rhs[] = L"geekGgeek";

    // check till 4th characters and till 7th characters
    check(lhs, rhs, 4);
    check(lhs, rhs, 7);

    return 0;
}
```

**Output:**

```cpp
First 4 characters of  are same
geekGgeek precedes geekforgeeks

```

**程序 2 :**

```cpp
// C++ program to illustrate the
// wcsncmp() function
#include <bits/stdc++.h>
using namespace std;

// function to compare two strings
void check(wchar_t* lhs, wchar_t* rhs, int count)
{
    int result;
    // compare lhs and rhs by wcsncmp
    result = wcsncmp(lhs, rhs, count);

    // print, as per result
    if (result < 0)
        wcout << lhs << " precedes " << rhs << "\n";
    else if (result > 0)
        wcout << rhs << " precedes " << lhs << "\n";
    else
        wcout << L"First " << count << L" characters of "
              << L" are same"
              << "\n";
}

// Driver code
int main()
{
    // initialize two strings lhs and rhs to compare
    wchar_t lhs[] = L"01234GFG";
    wchar_t rhs[] = L"01234GFG";

    // check till 5th character
    // and again till 8th character
    check(lhs, rhs, 5);
    check(lhs, rhs, 8);

    return 0;
}
```

**Output:**

```cpp
First 5 characters of  are same
First 8 characters of  are same

```