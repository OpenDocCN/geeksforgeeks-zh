# C/c++ 中的 putwchar()函数

> 原文:[https://www.geeksforgeeks.org/putwchar-function-in-c-c/](https://www.geeksforgeeks.org/putwchar-function-in-c-c/)

C/C++ 中的 **putwchar()** 函数将一个宽字符写入 stdout(标准输出)。在**<cwchar.h></cwchar.h>**CPP 库中定义。

**语法:**

```cpp
wint_t putwchar(wchar_t ch)
```

**参数:**函数接受一个强制参数 **ch** ，指定要写入的宽字符。

**返回值:**该函数返回如下两个值:

*   成功时，此函数返回由 ch 表示的宽字符
*   它返回 WEOF，如果出现写入错误，则设置错误指示器

以下程序说明了上述功能:
**程序 1 :**

```cpp
// C++ program to illustrate
// putwchar() function

#include <bits/stdc++.h>
using namespace std;

int main()
{
    setlocale(LC_ALL, "en_US.UTF-8");

    // initiate the starting and
    // the last alphabet
    wchar_t first = L'\u05d0', last = L'\u05ea';

    wcout << L"All Hebrew Alphabets : ";

    // print all the alphabets
    for (wchar_t i = first; i <= last; i++) {
        putwchar(i);
        putwchar(' ');
    }

    return 0;
}
```

**Output:**

```cpp
All Hebrew Alphabets : × ×? ×? ×? ×? ×? ×? ×? ×? ×? ×? ×? ×? × ×? ×? ×  ×¡ ×¢ ×£ ×¤ ×¥ ×¦ ×§ ×¨ ×© ×ª

```

**程序 2 :**

```cpp
// C++ program to illustrate the
// putwchar() function

#include <bits/stdc++.h>
using namespace std;

int main()
{
    wchar_t wc;

    // initializing the first
    // and last alphabets
    wchar_t first = 'A', last = 'Z';

    wcout << L"All English Alphabets : ";

    // print all the alphabets from
    // first to the last
    for (wc = first; wc <= last; ++ wc) {
        putwchar(wc);
        putwchar(' ');
    }

    return 0;
}
```

**Output:**

```cpp
All English Alphabets : A B C D E F G H I J K L M N O P Q R S T U V W X Y Z

```