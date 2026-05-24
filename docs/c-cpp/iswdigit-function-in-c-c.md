# 是 C/C++

中的 iswdigit()函数

> 原文:[https://www.geeksforgeeks.org/iswdigit-function-in-c-c/](https://www.geeksforgeeks.org/iswdigit-function-in-c-c/)

**iswdigit()** 是 C++ STL 中的内置函数，它检查给定的宽字符是否是十进制数字字符。在 C++ 的**cwcytpe**头文件中定义。从 0 到 9 的字符，即 0、1、2、3、4、5、6、7、8、9 被归类为十进制数字。

**语法**:

```cpp
int iswdigit(ch)
```

**参数**:该函数接受单个强制参数 ***ch*** ，指定宽字符，我们必须检查它是否是数字。

**返回值**:函数返回两个值，如下图所示。

*   如果 ch 是数字，则返回非零值。
*   如果不是，则返回 0。

下面的程序说明了上面的功能。

**程序 1** :

```cpp
// C++ program to illustrate
// iswdigit() function
#include <cwctype>
#include <iostream>
using namespace std;

int main()
{

    wchar_t ch1 = '?';
    wchar_t ch2 = '3';

    // Function to check if the character
    // is a digit or not
    if (iswdigit(ch1))
        wcout << ch1 << " is a digit ";
    else
        wcout << ch1 << " is not a digit ";
    wcout << endl;

    if (iswdigit(ch2))
        wcout << ch2 << " is a digit ";
    else
        wcout << ch2 << " is not a digit ";

    return 0;
}
```

**Output:**

```cpp
? is not a digit 
3 is a digit

```

**程序 2** :

```cpp
// C++ program to illustrate
// iswdigit() function
#include <cwctype>
#include <iostream>
using namespace std;

int main()
{

    wchar_t ch1 = '1';
    wchar_t ch2 = 'q';

    // Function to check if the character
    // is a digit or not
    if (iswdigit(ch1))
        wcout << ch1 << " is a digit ";
    else
        wcout << ch1 << " is not a digit ";
    wcout << endl;

    if (iswdigit(ch2))
        wcout << ch2 << " is a digit ";
    else
        wcout << ch2 << " is not a digit ";

    return 0;
}
```

**Output:**

```cpp
1 is a digit 
q is not a digit

```