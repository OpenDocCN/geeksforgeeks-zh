# c++ STL 中的 wcstombs()函数

> 原文:[https://www.geeksforgeeks.org/wcstombs-function-in-c-stl/](https://www.geeksforgeeks.org/wcstombs-function-in-c-stl/)

**wcstombs()** 是 C++ STL 中的一个内置函数，它将宽字符串转换为其等效的多字节序列。它是在 C++ 的**csdlib**头文件中定义的。

**语法**

```cpp
wcstombs(d, s, n)
```

**参数**:

*   **d** :是指定指向至少 n 字节长的字符数组的指针的参数。
*   **s** :是指定要转换的宽字符串的参数。
*   **n** :是指定最大转换宽字符数的参数。

**返回值**:

*   如果转换成功，则函数返回转换并写入字符串的字节数(不是字符数)，不包括终止的空字符(' \0 ')。
*   如果出现任何错误，则返回-1。

**程序 1** :

```cpp
// Program to illustrate
// wcstombs function in C++
#include <cstdlib>
#include <iostream>
using namespace std;

int main()
{
    wchar_t s[] = L"GeeksforGeeks";
    char d[100];
    int n;

    n = wcstombs(d, s, 100);
    cout << "Number of wide character converted = "
         << n << endl;
    cout << "Multibyte Character String = "
         << d << endl;

    return 0;
}
```

**Output:**

```cpp
Number of wide character converted = 13
Multibyte Character String = GeeksforGeeks

```

**程序 2** :

```cpp
// Program to illustrate
// wcstombs function in C++
#include <cstdlib>
#include <iostream>
using namespace std;

int main()
{
    wchar_t s[] = L"10@Hello World!";
    char d[100];
    int n;

    n = wcstombs(d, s, 100);
    cout << "Number of wide character converted = "
         << n << endl;
    cout << "Multibyte Character String = "
         << d << endl;

    return 0;
}
```

**Output:**

```cpp
Number of wide character converted = 15
Multibyte Character String = 10@Hello World!

```