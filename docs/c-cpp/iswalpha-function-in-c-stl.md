# c++ STL 中的 iswalpha()函数

> 原文:[https://www.geeksforgeeks.org/iswalpha-function-in-c-stl/](https://www.geeksforgeeks.org/iswalpha-function-in-c-stl/)

**iswalpha()** 是 C++ STL 中的一个内置函数，它检查给定的宽字符是否是字母表。在 C++ 的**cwcytpe**头文件中定义。

以下字符是字母数字:

*   **大写字母** : A 到 Z
*   **小写字母** : a 到 z

**语法**:

```cpp
int iswalpha(ch)
```

**参数**:该函数接受单个强制参数 *ch* ，该参数指定了宽字符，我们必须检查它是否是字母表。

**返回值**:该函数返回两个值:

*   如果 ch 是字母数字字符，则返回非零值。
*   如果不是字母数字字符，则返回 0。

下面的程序说明了上述功能。

**程序 1** :

```cpp
// Program to illustrate
// iswalpha() function
#include <cwctype>
#include <iostream>
using namespace std;

int main()
{

    wchar_t ch1 = 'Q';
    wchar_t ch2 = 'g';

    iswalpha(ch1) ? wcout << ch1 
    << "is alphabet " : wcout << ch1
    << " is not alphabet ";

    wcout << endl;
    iswalpha(ch2) ? wcout << ch2 
    << " is an alphabet " : wcout << ch2
    << " is not an alphabet ";

    return 0;
}
```

**Output:**

```cpp
Q is an alphabet 
g is an alphabet

```

**程序 2** :

```cpp
// Program to illustrate
// iswalpha() function
#include <cwctype>
#include <iostream>
using namespace std;

int main()
{

    wchar_t ch1 = 'w';
    wchar_t ch2 = '2';

    iswalpha(ch1) ? wcout << ch1 << 
    " is alphabet " : wcout << ch1 
    << " is not alphabet ";

    wcout << endl;
    iswalpha(ch2) ? wcout << ch2 << 
    " is an alphabet " : wcout << ch2 
    << " is not an alphabet ";

    return 0;
}
```

**Output:**

```cpp
w is an alphabet 
2 is not an alphabet

```