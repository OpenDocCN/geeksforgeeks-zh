# iswalnum()函数在 C++ STL 中

> 原文:[https://www.geeksforgeeks.org/iswalnum-function-in-c-stl/](https://www.geeksforgeeks.org/iswalnum-function-in-c-stl/)

**iswalnum()** 是 C++ STL 中的一个内置函数，它检查给定的宽字符是否是字母数字字符。在 C++ 的**cwcytpe**头文件中定义。
以下字符为字母数字:

*   **大写字母** : A 到 Z
*   **小写字母** : a 到 z
*   **数字** : 0 到 9

**语法**:

```cpp
int iswalnum(ch)
```

**参数**:该函数接受单个强制参数 **ch** ，该参数指定了我们必须检查是否为字母数字的宽字符。

**返回值**:函数返回两个值，如下图所示。

*   如果 ch 是字母数字字符，则返回非零值。
*   如果不是，则返回 0。

下面的程序说明了上面的功能。

**程序 1** :

```cpp
// Program to illustrate
// iswalnum() function
#include <cwctype>
#include <iostream>
using namespace std;

int main()
{

    wchar_t ch1 = '?';
    wchar_t ch2 = 'g';

    // Function to check if the character
    // is alphanumeric or not
    if (iswalnum(ch1))
        wcout << ch1 << " is alphanumeric ";
    else
        wcout << ch1 << " is not alphanumeric ";
    wcout << endl;

    if (iswalnum(ch2))
        wcout << ch2 << " is alphanumeric ";
    else
        wcout << ch2 << " is not alphanumeric ";

    return 0;
}
```

**Output:**

```cpp
? is not alphanumeric 
g is alphanumeric

```

**程序 2** :

```cpp
// Program to illustrate
// iswalnum() function
#include <cwctype>
#include <iostream>
using namespace std;

int main()
{

    wchar_t ch1 = '3';
    wchar_t ch2 = '&';

    // Function to check if the character
    // is alphanumeric or not
    if (iswalnum(ch1))
        wcout << ch1 << " is alphanumeric ";
    else
        wcout << ch1 << " is not alphanumeric ";
    wcout << endl;

    if (iswalnum(ch2))
        wcout << ch2 << " is alphanumeric ";
    else
        wcout << ch2 << " is not alphanumeric ";

    return 0;
}
```

**Output:**

```cpp
3 is alphanumeric 
& is not alphanumeric

```