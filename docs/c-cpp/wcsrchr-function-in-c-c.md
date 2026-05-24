# wcsrchr()函数在 C/C++ 中

> 原文:[https://www.geeksforgeeks.org/wcsrchr-function-in-c-c/](https://www.geeksforgeeks.org/wcsrchr-function-in-c-c/)

**wcsrchr()** 函数是 C/C++ 中的一个内置函数，用于搜索宽字符串中最后出现的宽字符。它在 C++ 中的**cwcchar**头文件中定义。

**语法**:

```cpp
wcsrchr(str, ch)
```

**参数**:该功能接受两个参数，描述如下。

*   **字符串**:指定要搜索的空终止宽字符串。
*   **ch** :指定要搜索的宽字符。

**返回值**:函数返回值有两种类型:

*   如果找到 **ch** ，该函数返回一个指向 **str** 中 **ch** 最后位置的指针。
*   如果没有找到，则返回空指针。

下面的程序说明了上述功能。

**程序 1** :

```cpp
// C++ program to illustrate the
// wcsrchr() function
#include <cwchar>
#include <iostream>
using namespace std;

int main()
{
    wchar_t str[] = L"GeeksforGeeks";
    wchar_t ch = L'e';
    wchar_t* p = wcsrchr(str, ch);

    if (p)
        wcout << L"Last position of " << ch << L" in \""
              << str << "\" is " << (p - str);
    else
        wcout << ch << L" is not present in \"" << str << L"\"";

    return 0;
}
```

**Output:**

```cpp
Last position of e in "GeeksforGeeks" is 10

```

**程序 2** :

```cpp
// C++ program to illustrate the
// wcsrchr() function
#include <cwchar>
#include <iostream>
using namespace std;

int main()
{
    wchar_t str[] = L"Ishwar Gupta";
    wchar_t ch = L'o';
    wchar_t* p = wcsrchr(str, ch);

    if (p)
        wcout << L"Last position of " << ch << L" in \""
              << str << "\" is " << (p - str);
    else
        wcout << ch << L" is not present in \"" << str << L"\"";

    return 0;
}
```

**Output:**

```cpp
o is not present in "Ishwar Gupta"

```