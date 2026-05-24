# 是 C/C++ 中的 iswprint()，带有示例

> 原文:[https://www . geeksforgeeks . org/isw print-in-c-c-with-examples/](https://www.geeksforgeeks.org/iswprint-in-c-c-with-examples/)

**isw print()**是 C/C++ 中的一个内置函数，用于检查给定的宽字符是否可以打印。在 C++ 的**cwcytpe**头文件中定义。默认情况下，以下字符是可打印的:

*   **数字** (0 至 9)
*   **大写字母** (A 至 Z)
*   **小写字母** (a 至 z)
*   **标点符号**(！" #$% & '()*+，-。/:;？@[\]^_`{|}~)
*   **空间**

**语法**:

```cpp
int iswprint(ch)
```

**参数**:该功能接受单个强制参数 **ch** ，指定是否可打印需要检查的宽字符。

**返回值**:函数返回两个值，如下图所示。

*   如果参数 ch 是可打印的，则返回非零值。
*   如果不是可打印字符，则返回 0。

下面的程序说明了上面的功能。

**程序 1** :

```cpp
// Program to illustrate
// towprint() function
#include <cwchar>
#include <cwctype>
#include <iostream>
using namespace std;
int main()
{

    wchar_t str[] = L"Geeks\tfor\tGeeks";
    for (int i = 0; i < wcslen(str); i++) {

        // Function to check if the characters are
        // printable or not. If not, then replace
        // all non printable character by comma
        if (!iswprint(str[i]))
            str[i] = ', ';
    }
    wcout << "Printing, if the given wide 
    character cannot be printed\n";
    wcout << str;
    return 0;
}
```

**Output:**

```cpp
Printing , if the given wide character cannot be printed
Geeks, for, Geeks

```

**程序 2** :

```cpp
// Program to illustrate
// towprint() function
#include <cwchar>
#include <cwctype>
#include <iostream>
using namespace std;
int main()
{

    wchar_t str[] = L"Ishwar Gupta\t123\t!@#";
    for (int i = 0; i < wcslen(str); i++) {

        // Function to check if the characters are
        // printable or not. If not, then replace
        // all non printable character by comma
        if (!iswprint(str[i]))
            str[i] = ', ';
    }
    wcout << "Printing, if the given wide 
    character cannot be printed\n";
    wcout << str;
    return 0;
}
```

**Output:**

```cpp
Printing , if the given wide character cannot be printed
Ishwar Gupta, 123, !@#

```