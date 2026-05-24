# wcstoll()函数在 C/C++ 中

> 原文:[https://www.geeksforgeeks.org/wcstoll-function-in-c-c/](https://www.geeksforgeeks.org/wcstoll-function-in-c-c/)

C/C++ 中的 **wcstoll()** 函数将宽字符串转换为长整数。它设置指针指向最后一个字符之后的第一个字符。

**语法:**

```cpp
long long wcstoll( const wchar_t* str, wchar_t** str_end, int base )
```

**参数:**该功能接受三个强制参数，描述如下:

*   **字符串:**它指定了一个以**整数**开头的宽字符串。
*   **str _ end:**str _ end 值由函数设置为下一个字符，在最后一个有效字符之后(如果有)，否则它将指向 NULL。
*   **base:** 指定 base，base 的值可以是{0，2，3，…，35，36}。

**返回值:**函数返回转换后的长整型。它返回 0，如果字符指向空。

以下程序说明了上述功能:

**程序 1 :**

```cpp
// C++ program to illustrate
// the function wcstoll()
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // wide-character type array string starting
    // with integral 'L'
    wchar_t string1[] = L"888geekforgeeks";
    wchar_t string2[] = L"999gfg";

    // End pointer will point to the characters
    // after integer, according to the base
    wchar_t* End;

    // Initializing base
    int b = 10; 
    int value;

    value = wcstoll(string1, &End, b);
    value = wcstoll(string2, &End, b);

    // prints the whole input string
    wcout << "String Value = " << string1 << "\n";
    wcout << "Long Long Int value = " << value << "\n";

    // prints the end string after the integer
    wcout << "End String = " << End << "\n";

    wcout << "String Value = " << string2 << "\n";
    wcout << "Long Long Int Value = " << value << "\n";
    wcout << "End String = " << End << "\n";
    return 0;
}
```

**Output:**

```cpp
String Value = 888geekforgeeks
Long Long Int value = 999
End String = gfg
String Value = 999gfg
Long Long Int Value = 999
End String = gfg

```

**注意:**碱基的值可以是{0，2，3，…，35，36}。基数 2 的一组有效数字是{0，1}，基数 3 的有效数字是{0，1，2}，依此类推。对于从 11 到 36 开始的基数，有效数字包括字母。基数 11 的有效位数是{0，1，…，9，A，a}，基数 12 的有效位数是{0，1，…，9，A，A，B，b}等等。

**程序 2 :** 功能不同碱基

```cpp
// C++ program to illustrate the function wcstoll()
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // End pointer, will point to the characters
    // after integer, according to the base
    wchar_t* End;

    // wide-character type array string
    wchar_t string[] = L"1356geekforgeeks";

    // Prints the long long integer provided with base 5
    wcout << "Long Long Int with base5 = "
    << wcstoll(string, &End, 5) << "\n";

    wcout << "End String = " << End << "\n";

    // Prints the long long integer provided with base 12
    wcout << "Long Long Int with base12 = " 
    << wcstoll(string, &End, 12) << "\n";

    wcout << "End String = " << End << "\n";

    // Prints the long long integer provided with base 36
    wcout << "Long Long Int with base36 = "
    << wcstoll(string, &End, 36) << "\n";

    wcout << "End String = " << End << "\n";

    return 0;
}
```

**Output:**

```cpp
Long Long Int with base5 = 8
End String = 56geekforgeeks
Long Long Int with base12 = 2226
End String = geekforgeeks
Long Long Int with base36 = 9223372036854775807
End String =

```