# wcsspn()函数在 C/C++ 中的应用举例

> 原文:[https://www . geesforgeks . org/wcsspn-function-in-c-c-with-examples/](https://www.geeksforgeeks.org/wcsspn-function-in-c-c-with-examples/)

**wcsspn()** 是 C/C++ 中的内置函数，它返回宽字符串的最大初始段长度，该长度由另一个宽字符串中存在的字符组成。在 C++ 的**cwcchar**头文件中定义。

**语法**:

```cpp
wcsspn(des, src)
```

**参数**:该功能接受如下所述的两个强制参数。

*   **des** :指定要搜索的空终止宽字符串。
*   **src** :指定为包含要搜索的字符的空终止宽字符串。

**返回值**:该函数返回 **des** 的最大初始段长度，该长度只包含 **src** 指向的宽字符串中的宽字符。

下面的程序说明了上述功能。

**程序 1** :

```cpp
// C++ program to illustrate the
// wcsspn() function
#include <cwchar>
#include <iostream>
using namespace std;

int main()
{
    wchar_t src[] = L"161106010";
    wchar_t des[] = L"6010IshwarGupta";
    int length = wcsspn(des, src);

    if (length > 0)
        wcout << des << L" contains " << 
                 length << L" initial numbers";
    else
        wcout << des << L" doesn't start with numbers";

    return 0;
}
```

**Output:**

```cpp
6010IshwarGupta contains 4 initial numbers

```

**程序 2** :

```cpp
// C++ program to illustrate the
// wcsspn() function
#include <cwchar>
#include <iostream>
using namespace std;

int main()
{
    wchar_t src[] = L"2018";
    wchar_t des[] = L"GeeksforGeeks";
    int length = wcsspn(des, src);

    if (length > 0)
        wcout << des << L" contains " << 
                 length << L" initial numbers";
    else
        wcout << des << L" doesn't start with numbers";

    return 0;
}
```

**Output:**

```cpp
GeeksforGeeks doesn't start with numbers

```