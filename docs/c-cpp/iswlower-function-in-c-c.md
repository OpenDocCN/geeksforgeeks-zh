# 是 C/C++

中的 iswlower()函数

> 原文:[https://www.geeksforgeeks.org/iswlower-function-in-c-c/](https://www.geeksforgeeks.org/iswlower-function-in-c-c/)

**isw low()**是 C/C++ 中的一个内置函数，它检查给定的宽字符是否是小写字符。在 C++ 的**cwcytpe**头文件中定义。

**语法**:

```cpp
int iswlower(ch)
```

**参数**:该函数接受单个强制参数 ***ch*** ，指定宽字符，我们必须检查它是否是小写字符。

**返回值**:函数返回两个值，如下图所示。

*   如果参数 ch 是小写字符，则返回非零值。
*   如果不是小写字符，则返回 0。

下面的程序说明了上面的功能。

**程序 1** :

```cpp
// C++ program to illustrate
// iswlower() function
#include <cwctype>
#include <iostream>
using namespace std;

int main()
{

    wchar_t ch1 = 'a';
    wchar_t ch2 = 'A';

    // Function to check if the character
    // is a lowercase character or not
    if (iswlower(ch1))
        wcout << ch1 << " is a lowercase character ";
    else
        wcout << ch1 << " is not a lowercase character ";
    wcout << endl;

    if (iswlower(ch2))
        wcout << ch2 << " is a lowercase character ";
    else
        wcout << ch2 << " is not a lowercase character ";

    return 0;
}
```

**Output:**

```cpp
a is a lowercase character 
A is not a lowercase character

```

**程序 2** :

```cpp
// C++ program to illustrate
// iswlower() function
#include <cwctype>
#include <iostream>
using namespace std;

int main()
{

    wchar_t ch1 = 'q';
    wchar_t ch2 = '?';

    // Function to check if the character
    // is a lowercase character or not
    if (iswlower(ch1))
        wcout << ch1 << " is a lowercase character ";
    else
        wcout << ch1 << " is not a lowercase character ";
    wcout << endl;

    if (iswlower(ch2))
        wcout << ch2 << " is a lowercase character ";
    else
        wcout << ch2 << " is not a lowercase character ";

    return 0;
}
```

**Output:**

```cpp
q is a lowercase character 
? is not a lowercase character

```