# C/c++

中的 iswxdigit()函数

> 原文:[https://www.geeksforgeeks.org/iswxdigit-function-in-c-c/](https://www.geeksforgeeks.org/iswxdigit-function-in-c-c/)

**iswxdigit()** 是 C/C++ 中的一个内置函数，它检查给定的宽字符是否是十六进制数字字符。在 C++ 的**cwcytpe**头文件中定义。可用的十六进制数字字符有:

*   **Number** (0 to 9)
*   **lowercase letters** from a to f
*   **Capital letters** from A to F

**语法:**

```cpp
int iswxdigit(ch)
```

**参数**:该函数接受一个强制参数 **ch** ，指定宽字符，我们必须检查它是否是十六进制。

**返回值**:函数返回两个值，如下图所示。

*   如果 ch 是六进制数，则返回非零值。
*   如果不是六进制，则返回 0。

下面的程序说明了上面的功能。

**程序 1** :

```cpp
// C++ program to illustrate
// iswxdigit() function
#include <cwchar>
#include <cwctype>
#include <iostream>
using namespace std;

// function to check if
// the wide character is hexadecimal or not
void ishexadecimal(wchar_t* str)
{
    bool flag = false;
    for (int i = 0; i < wcslen(str); i++) {
        if (!iswxdigit(str[i])) {
            flag = true;
            break;
        }
    }

    if (flag)
        wcout << str << L" is not a valid"
              << " hexadecimal number" << endl;
    else
        wcout << str << L" is a valid"
              << " hexadecimal number" << endl;
}

// Driver Code
int main()
{
    wchar_t str[] = L"a3lz";
    ishexadecimal(str);

    wchar_t str1[] = L"10dbe";
    ishexadecimal(str1);

    return 0;
}
```

**输出:**

```cpp
a3lz is not a valid hexadecimal number
10dbe is a valid hexadecimal number

```

**程序二** :

```cpp
// C++ program to illustrate
// iswxdigit() function
#include <cwchar>
#include <cwctype>
#include <iostream>
using namespace std;

// function to check if
// the wide character is hexadecimal or not
void ishexadecimal(wchar_t* str)
{
    bool flag = false;
    for (int i = 0; i < wcslen(str); i++) {
        if (!iswxdigit(str[i])) {
            flag = true;
            break;
        }
    }

    if (flag)
        wcout << str << L" is not a valid"
              << " hexadecimal number" << endl;
    else
        wcout << str << L" is a valid"
              << " hexadecimal number" << endl;
}

// Driver Code
int main()
{
    wchar_t str[] = L"1441a";
    ishexadecimal(str);

    wchar_t str1[] = L"xyz2";
    ishexadecimal(str1);

    return 0;
}
```

**输出:**

```cpp
1441a is a valid hexadecimal number
xyz2 is not a valid hexadecimal number

```

**类似函数:** [isalpha()和 isdigit()函数在 C/C++ 中，示例](https://www.geeksforgeeks.org/isalpha-isdigit-functions-c-example/)