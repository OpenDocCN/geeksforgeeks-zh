# C/c++

中的 to flow()函数

> 原文:[https://www.geeksforgeeks.org/towlower-function-in-c-c/](https://www.geeksforgeeks.org/towlower-function-in-c-c/)

**tow low()**是 C/C++ 中的一个内置函数，它将给定的宽字符转换成小写。在 C++ 的**cwcytpe**头文件中定义。

*   它是头文件<cwctype>中的一个函数，所以如果使用这个函数</cwctype>
*   就必须使用这个头文件，它是 tolower()函数的宽字符等价物。

**语法**:

```cpp
wint_t towlower( wint_t ch )
```

**参数**:函数接受单个强制参数 **ch** ，指定我们必须转换成小写的宽字符。

**返回值**:如果存在 c 值，函数返回小写的 c 值，否则返回 c 值(不变)。该值作为 wint_t 值返回，可以隐式转换为 wchar_t。

下面的程序说明了上面的功能。

**程序 1** :

```cpp
// Program to illustrate
// towlower() function
#include <cwchar>
#include <cwctype>
#include <iostream>
using namespace std;
int main()
{

    wchar_t str[] = L"GeeksforGeeks";
    wcout << L"The lowercase version of \""
          << str << L"\" is ";

    for (int i = 0; i < wcslen(str); i++)
        // Function to convert the character
        // into the lowercase version, if exists
        putwchar(towlower(str[i]));

    return 0;
}
```

**输出:**

```cpp
The lowercase version of "GeeksforGeeks" is geeksforgeeks

```

**程序 2** :

```cpp
// Program to illustrate
// towlower() function
#include <cwchar>
#include <cwctype>
#include <iostream>
using namespace std;
int main()
{

    wchar_t str[] = L"hello Ishwar 123!@#";
    wcout << L"The lowercase version of \""
          << str << L"\" is ";

    for (int i = 0; i < wcslen(str); i++)
        // Function to convert the character
        // into the lowercase version, if exists
        putwchar(towlower(str[i]));

    return 0;
}
```

**输出:**

```cpp
The lowercase version of "hello Ishwar 123!@#" is hello ishwar 123!@#

```