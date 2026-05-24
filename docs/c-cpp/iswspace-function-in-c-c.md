# C/c++ 中的 iswspace()函数

> 原文:[https://www.geeksforgeeks.org/iswspace-function-in-c-c/](https://www.geeksforgeeks.org/iswspace-function-in-c-c/)

**iswspace()** 是 C/C++ 中的内置函数，它检查给定的宽字符是否是宽空白字符。在 C++ 的**cwcytpe**头文件中定义。

**语法**:

```cpp
int iswspace(ch)
```

**参数**:该函数接受一个强制参数 **ch** ，该参数指定要检查是否有宽空白字符的宽字符。

**返回值**:函数返回两个值，如下图所示。

*   如果参数 ch 是一个宽空格，它将返回一个非零值。
*   如果不是小写字符，则返回 0。

下面的程序说明了上面的功能。

**程序 1** :

```cpp
// C++ program to illustrate
// iswspace() function
#include <cwctype>
#include <iostream>
using namespace std;

int main()
{
    wchar_t c;
    int i = 0;
    wchar_t str[] = L"Geeks For Geeks\n";

    // Check for every character
    // in th string
    while (str[i]) {
        c = str[i];

        // Function to check the character
        // is a wide whitespace or not
        if (iswspace(c))
            c = L'\n';
        putwchar(c);
        i++ ;
    }
    return 0;
}
```

**Output:**

```cpp
Geeks
For
Geeks

```

**程序 2** :

```cpp
// C++ program to illustrate
// iswspace() function
#include <cwctype>
#include <iostream>
using namespace std;

int main()
{
    wchar_t c;
    int i = 0;
    wchar_t str[] = L"Hello Ishwar Gupta\n";

    // Check for every character
    // in th string
    while (str[i]) {
        c = str[i];
        // Function to check the character
        // is a wide whitespace or not
        if (iswspace(c))
            c = L'\n';
        putwchar(c);
        i++ ;
    }
    return 0;
}
```

**Output:**

```cpp
Hello
Ishwar
Gupta

```