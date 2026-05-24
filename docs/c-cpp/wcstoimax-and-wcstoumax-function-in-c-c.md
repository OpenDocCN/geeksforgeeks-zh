# wcstoimax()和 wcstomax()函数在 C/C++ 中

> 原文:[https://www . geeksforgeeks . org/wcstoimax-and-wcstoumax-function-in-c-c/](https://www.geeksforgeeks.org/wcstoimax-and-wcstoumax-function-in-c-c/)

C/C++ 中的 **wcstoimax()** 和**wcstomax()**函数的工作原理与 C++ 中的 [strtoimax()](https://www.geeksforgeeks.org/strtoimax-function-in-c/) 和 [strtoumax()](https://www.geeksforgeeks.org/strtoumax-function-in-c/) 函数完全相同，但用于将**宽字符串(wstring)** 的内容转换为指定基数的整数。该功能在 **cinttypes** 头文件中定义。

**语法:**

```cpp
uintmax_t wcstoumax(const wchar* wstr, wchar** end, int base);
intmax_t wcstoimax(const wchar* wstr, wchar** end, int base);

```

**参数:**该功能接受三个强制参数，如下所述:

*   **wstr:** 指定由整数组成宽字符串。
*   **end:** 指定对 wchar*类型对象的引用。end 的值由函数设置为 wstr 中最后一个有效数字字符之后的下一个字符。如果没有使用，这个参数也可以是空指针。
*   **基数:**指定决定字符串中有效字符及其解释的数字基数(基数)

**返回类型:**函数返回两个值，如下所示:

*   如果发生了有效的转换，则该函数将转换后的整数作为整数值返回。
*   如果无法执行有效转换，则返回零值(0)

以下程序说明了上述功能:
**程序 1 :**

```cpp
// C++ program to illustrate the
// wstoimax() function
#include <bits/stdc++.h>
using namespace std;

// Driver code
int main()
{
    wstring str = L"geeksforgeeks";

    intmax_t val = wcstoimax(str.c_str(), nullptr, 36);

    wcout << str << " in base 36 is " << val << " in base 10\n\n";

    wchar_t* end;

    val = wcstoimax(str.c_str(), &end, 30);

    // 'w' does not lies in base 30 so string
    // beyond this cannot be converted
    wcout << "Given String = " << str << endl;

    wcout << "Number with base 30 in string " << val << " in base 10" << endl;

    wcout << "End String points to " << end << endl;

    return 0;
}
```

**Output:**

```cpp
geeksforgeeks in base 36 is 9223372036854775807 in base 10

Given String = geeksforgeeks
Number with base 30 in string 8759741037015451228 in base 10
End String points to

```

**程序 2 :**

```cpp
// C++ program to illustrate the
// wcstoumax() function
#include <bits/stdc++.h>
using namespace std;

// Driver code
int main()
{
    int base = 10;

    // L is a wide string literal
    wstring str = L"12345abcd";
    wchar_t* end;
    uintmax_t num;

    num = wcstoumax(str.c_str(), &end, base);

    wcout << "Given String = " << str << endl;

    wcout << "Value stored in num " << num << endl;

    if (*end) {
        wcout << "End string points to " << end << endl
              << endl;
    }
    else {
        wcout << "Null pointer" << endl
              << endl;
    }

    // in this case no numeric character is there
    // so the function returns 0
    base = 10;

    wstring str2 = L"abcd";

    wcout << "Given String = " << str2 << endl;

    num = wcstoumax(str2.c_str(), &end, base);

    wcout << "Number with base 10 in string " << num << endl;
    if (*end) {
        wcout << "End String points to " << end;
    }
    else {
        wcout << "Null pointer";
    }
    return 0;
}
```

**Output:**

```cpp
Given String = 12345abcd
Value stored in num 12345
End string points to abcd

Given String = abcd
Number with base 10 in string 0
End String points to abcd

```