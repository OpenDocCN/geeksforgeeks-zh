# wcspbrk()函数在 C/C++ 中

> 原文:[https://www.geeksforgeeks.org/wcspbrk-function-in-c-c/](https://www.geeksforgeeks.org/wcspbrk-function-in-c-c/)

**wcspbrk()** 是 C/C++ 中的内置函数，它在另一个宽字符串中搜索宽字符串中的一组宽字符。在 C++ 的**cwcchar**头文件中定义。

**语法**:

```cpp
wcspbrk(dest, src)
```

**参数**:该功能有两个参数，如下图所示。

*   **dest** :指定要搜索的空终止宽字符串。
*   **src** :指定包含要搜索字符的空终止宽字符串。

**返回值**:该函数返回如下两个值:

*   如果在 **dest** 和 **src** 中有一个或多个常用宽字符，该函数将指针返回到 dest 中也在 src 中的第一个宽字符。
*   如果 src & dest 中没有常见的宽字符，则返回空指针。

下面的程序说明了上述功能。

**程序 1** :

```cpp
// C++ program to illustrate the
// wcspbrk() function
#include <cwchar>
#include <iostream>
using namespace std;

int main()
{

    wchar_t src[] = L"Ishwar Gupta";
    wchar_t dest[] = L"GeeksforGeeks";
    wchar_t* s = wcspbrk(dest, src);
    int pos;

    if (s) {
        pos = s - dest;
        wcout << L"First occurrence in \"" << dest 
        << L"\" is at position " << pos << endl;
    }
    else
        wcout << L"No number found in \"" << dest << "\"";

    return 0;
}
```

**Output:**

```cpp
First occurrence in "GeeksforGeeks" is at position 0

```

**程序 2** :

```cpp
// C++ program to illustrate the
// wcspbrk() function
#include <cwchar>
#include <iostream>
using namespace std;

int main()
{

    wchar_t src[] = L"123";
    wchar_t dest[] = L"Hello World";
    wchar_t* s = wcspbrk(dest, src);
    int pos;

    if (s) {
        pos = s - dest;
        wcout << L"First occurrence in \"" << dest 
        << L"\" is at position " << pos << endl;
    }
    else
        wcout << L"No common wide character";

    return 0;
}
```

**Output:**

```cpp
No common wide character

```