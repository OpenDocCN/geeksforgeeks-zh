# wcstol()函数在 C/C++ 中

> 原文:[https://www.geeksforgeeks.org/wcstol-function-in-c-c/](https://www.geeksforgeeks.org/wcstol-function-in-c-c/)

C/C++ 中的 **wcstol()** 函数将给定的宽字符串转换为长整数。此函数设置一个指针指向宽字符串最后一个有效字符之后的第一个字符(如果有)，否则，指针设置为 null。该函数忽略所有前导空白字符，直到找到主要的非空白字符。

**语法:**

> 长 int wcstol( const wchar_t* str，wchar_t**末端环，int base)

**参数:**该功能接受三个强制参数，描述如下:

*   **字符串:**以整数形式开始的字符串。
*   **结束字符串:**这是由函数设置到**字符串**中最后一个有效字符之后的下一个字符。
*   **base:**base 的有效值集为{0，2，3，…，35，36}。

**返回值:**该函数返回如下两个值:

*   成功后，该函数将转换后的整数作为长整型值返回。
*   如果无法执行有效的转换，则返回零。
*   如果读取的值超出了长整型可表示值的范围，函数返回 *LONG_MAX* 或 *LONG_MIN* (在<climits>中定义)，errno 设置为 e range。</climits>

以下程序说明了上述功能:
**程序 1 :**

```cpp
// C++ program to illustrate
// wcstol() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialize the string
    wchar_t string[] = L"101GeeksForGeeks";

    // initialize the base
    int base = 3;
    wchar_t* endString;

    // print the long integer value with the end string
    long value = wcstol(string, &endString, base);
    wcout << L"String value --> " << string << "\n";
    wcout << L"Long integer value --> " << value << "\n";
    wcout << L"End String = " << endString << "\n";

    return 0;
}
```

**Output:**

```cpp
String value --> 101GeeksForGeeks
Long integer value --> 10
End String = GeeksForGeeks

```

不同基数的节目:
**节目 2 :**

```cpp
// C++ program to illustrate
// wcstol() function
// with different bases
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialize the string
    wchar_t string[] = L"101GFG";

    // initialize the base

    wchar_t* endString;

    // print the long integer value with the end string
    // with base 2
    long value = wcstol(string, &endString, 2);
    wcout << L"String value --> " << string << "\n";
    wcout << L"Long integer value --> " << value << "\n";
    wcout << L"End String = " << endString << "\n";

    // print the long integer value with the end string
    // with base 5
    value = wcstol(string, &endString, 5);
    wcout << L"String value --> " << string << "\n";
    wcout << L"Long integer value --> " << value << "\n";
    wcout << L"End String = " << endString << "\n";

    // print the long integer value with the end string
    // with base 12
    value = wcstol(string, &endString, 12);
    wcout << L"String value --> " << string << "\n";
    wcout << L"Long integer value --> " << value << "\n";
    wcout << L"End String = " << endString << "\n";

    return 0;
}
```

**Output:**

```cpp
String value --> 101GFG
Long integer value --> 5
End String = GFG
String value --> 101GFG
Long integer value --> 26
End String = GFG
String value --> 101GFG
Long integer value --> 145
End String = GFG

```