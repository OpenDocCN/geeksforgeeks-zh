# C/c++

中的 towupper()函数

> 原文:[https://www.geeksforgeeks.org/towupper-function-in-c-c/](https://www.geeksforgeeks.org/towupper-function-in-c-c/)

**to upper()**是 C/C++ 中的一个内置函数，它将给定的宽字符转换为大写。在 C++ 的**cwcytpe**头文件中定义。

**语法**:

```cpp
wint_t towupper( wint_t ch )
```

**参数**:函数接受单个强制参数 **ch** ，指定我们必须转换成大写的宽字符。

**返回值**:函数返回两个值，如下图所示。

*   如果 ch 有大写版本，那么它就被转换成大写。
*   如果不是，则不会发生修改。

下面的程序说明了上面的功能。

**程序 1** :

```cpp
// Program to illustrate
// towupper() function
#include <cwchar>
#include <cwctype>
#include <iostream>
using namespace std;
int main()
{

    wchar_t str[] = L"GeeksforGeeks";
    wcout << L"The uppercase version of \"" 
          << str << L"\" is ";

    for (int i = 0; i < wcslen(str); i++)
        // Function to convert the character
        // into the uppercase version, if exists
        putwchar(towupper(str[i]));

    return 0;
}
```

**Output:**

```cpp
The uppercase version of "GeeksforGeeks" is GEEKSFORGEEKS

```

**程序 2** :

```cpp
// Program to illustrate
// towupper() function
#include <cwchar>
#include <cwctype>
#include <iostream>
using namespace std;
int main()
{

    wchar_t str[] = L"hello Ishwar 123!@#";
    wcout << L"The uppercase version of \"" 
          << str << L"\" is ";

    for (int i = 0; i < wcslen(str); i++)
        // Function to convert the character
        // into the uppercase version, if exists
        putwchar(towupper(str[i]));

    return 0;
}
```

**Output:**

```cpp
The uppercase version of "hello Ishwar 123!@#" is HELLO ISHWAR 123!@#

```