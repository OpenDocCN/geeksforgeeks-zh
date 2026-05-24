# wcstod()函数在 C/C++ 中

> 原文:[https://www.geeksforgeeks.org/wcstod-function-in-c-c/](https://www.geeksforgeeks.org/wcstod-function-in-c-c/)

**wcstod()** 函数将宽字符串转换为**双**。该函数将宽字符串的内容解释为浮点数。如果**结束字符串**不是空指针，该函数还将**结束字符串**的值设置为指向数字后的第一个字符。

**语法:**

```cpp
double wcstod( const wchar_t* str, wchar_t** str_end )
```

**参数:**该功能接受两个强制参数，如下所述:

*   **字符串:**指定以浮点数的表示形式开始的字符串
*   **结束字符串:**指定指向宽字符的指针

**返回值:**该函数返回如下两个值:

*   成功后，该函数将转换后的浮点数作为 double 类型的值返回。
*   如果无法执行有效转换，则返回 0.0。
*   如果正确的值超出了该类型的可表示值的范围，则返回一个正的或负的 HUGE _ VAL，并将 errno 设置为 e range。
*   如果正确的值会导致下溢，该函数将返回一个值，该值的大小不大于最小的规范化正数(在这种情况下，一些库实现也可能将 errno 设置为 ERANGE)。

以下程序说明了上述功能:
**程序 1 :**

```cpp
// C++ program to illustrate
// wcstod() function

#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialize the wide string
    // beginning with the floating point number
    wchar_t string[] = L"95.6Geek";

    // Pointer to a pointer to a wide character
    wchar_t* endString;

    // Convert wide string to double
    double value = wcstod(string, &endString);

    // print the string, starting double value
    // and its endstring
    wcout << L"String -> " << string << "\n";
    wcout << L"Double value -> " << value << "\n";
    wcout << L"End String is : " << endString << "\n";

    return 0;
}
```

**Output:**

```cpp
String -> 95.6Geek
Double value -> 95.6
End String is : Geek

```

**程序 2 :**

```cpp
// C++ program to illustrate
// wcstod() function
// with no endString characters
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialize the wide string
    // beginning with the floating point number
    wchar_t string[] = L"10.6464";

    // Pointer to a pointer to a wide character
    wchar_t* endString;

    // Convert wide string to double
    double value = wcstod(string, &endString);

    // print the string, starting double value
    // and its endstring
    wcout << L"String -> " << string << "\n";
    wcout << L"Double value -> " << value << "\n";
    wcout << L"End String is : " << endString << "\n";

    return 0;
}
```

**Output:**

```cpp
String -> 10.6464
Double value -> 10.6464
End String is :

```

**程序 3 :**

```cpp
// C++ program to illustrate
// wcstod() function
// with whitespace present at the beginning
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // initialize the wide string
    // beginning with the floating point number
    wchar_t string[] = L"            99.999Geek";

    // Pointer to a pointer to a wide character
    wchar_t* endString;

    // Convert wide string to double
    double value = wcstod(string, &endString);

    // print the string, starting double value
    // and its endstring
    wcout << L"String -> " << string << "\n";
    wcout << L"Double value -> " << value << "\n";
    wcout << L"End String is : " << endString << "\n";

    return 0;
}
```

**Output:**

```cpp
String ->             99.999Geek
Double value -> 99.999
End String is : Geek

```