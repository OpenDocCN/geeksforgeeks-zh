# wcstoul()函数在 C/C++ 中

> 原文:[https://www.geeksforgeeks.org/wcstoul-function-in-c-c/](https://www.geeksforgeeks.org/wcstoul-function-in-c-c/)

C/C++ 中的 **wcstoul()** 函数将宽字符串转换为**无符号长整数**。
这个函数设置一个指针指向宽字符串最后一个有效字符之后的第一个字符(如果有)，否则，指针设置为空。该函数忽略所有前导空白字符，直到找到主要的非空白字符。

**语法:**

> 无符号长 wcstoul( const wchar_t* string，wchar _ t * * endstring，int base)

**参数:**该功能接受三个强制参数，描述如下:

*   **字符串:**指定包含整数表示的字符串。
*   **endString:** 指定 endString 的值由函数设置为字符串中最后一个有效字符之后的下一个字符。
*   **base:** 指定 base 的有效值集为{0，2，3，…，35，36}。

**返回值:**该函数返回如下两个值:

*   成功后，该函数将转换后的整数作为**无符号长整型值**返回。
*   如果没有发生有效的转换，则返回零。

以下程序说明了上述功能:

**程序 1:**

## C++

```cpp
// C++ program to illustrate
// wcstoul() function
// with base equal to 36

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialize the wide string
    wchar_t string[] = L"999gfg";

    // set a pointer pointing
    // the string at the end
    wchar_t* endString;

    // print the unsigned long integer value
    // with the end string
    // initialize the base as 36
    unsigned long value = wcstoul(string, &endString, 36);
    wcout << L"String value given is -> "
          << string << endl;

    wcout << L"Unsigned Long Int value will be -> "
          << value << endl;

    wcout << L"End String will be-> "
          << endString << endl;

    return 0;
}
```

**Output:** 

```cpp
String value given is -> 999gfg
Unsigned Long Int value will be -> 559753324
End String will be->
```

**程序 2:**

## C++

```cpp
// C++ program to illustrate
// wcstoul() function
// with different bases

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialize the wide string
    wchar_t string[] = L"99999999999gfg";

    // set a pointer pointing
    // the string at the end
    wchar_t* endString;

    // print the unsigned long integer value with
    // the end string with base 36
    long value = wcstol(string, &endString, 35);
    wcout << L"String value --> " << string << "\n";

    wcout << L"Long integer value --> " << value << "\n";

    wcout << L"End String = " << endString << "\n";

    // print the unsigned long integer value with
    // the end string with base 16
    value = wcstol(string, &endString, 16);
    wcout << L"String value --> " << string << "\n";

    wcout << L"Long integer value --> " << value << "\n";

    wcout << L"End String = " << endString << "\n";

    // print the unsigned long integer value with
    // the end string with base 12
    value = wcstol(string, &endString, 12);
    wcout << L"String value --> " << string << "\n";

    wcout << L"Long integer value --> " << value << "\n";

    wcout << L"End String = " << endString << "\n";

    return 0;
}
```

**Output:** 

```cpp
String value --> 99999999999gfg
Long integer value --> 9223372036854775807
End String = 
String value --> 99999999999gfg
Long integer value --> 10555311626649
End String = gfg
String value --> 99999999999gfg
Long integer value --> 607915939653
End String = gfg
```