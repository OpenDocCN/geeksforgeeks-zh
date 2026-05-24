# C/c++

中的 mbrlen()函数

> 原文:[https://www.geeksforgeeks.org/mbrlen-function-in-c-c/](https://www.geeksforgeeks.org/mbrlen-function-in-c-c/)

给定当前转换状态 ps，C/C++ 中的 **mbrlen()** 函数确定字符串指向的多字节字符剩余部分的字节大小。该函数的行为取决于所选 C 语言环境的 LC_CTYPE 类别。

**语法:**

```cpp
size_t mbrlen( const char* str, size_t n, mbstate_t* ps)
```

**参数:**该功能接受三个强制参数，描述如下:

*   **字符串:**指定要检查的多字节字符串的第一个字节的指针
*   **n:** 指定要检查的最大字节数(s)
*   **ps:** 指定定义转换状态的 mbstate_t 对象的指针

**返回值:**该函数返回如下四个值:

1.  完成一个有效多字节字符的字节数
2.  -1 如果发生编码错误
3.  如果 s 指向空字符，则为 0
4.  -2 如果接下来的 n 个字节是可能有效的多字节字符的一部分，则在检查所有 n 个字节后仍然不完整

以下程序说明了上述功能:
**程序 1 :**

```cpp
// C++ program to illustrate
// mbrlen() function
#include <bits/stdc++.h>
using namespace std;

// Function to find the size of
// the multibyte character
void check_(const char* str, size_t n)
{
    // Multibyte conversion state
    mbstate_t ps = mbstate_t();

    // number of byte to be saved in returnV
    int returnV = mbrlen(str, n, &ps);

    if (returnV == -2)
        cout << "Next " << n << " byte(s) doesn't"
             << " represent a complete"
             << " multibyte character" << endl;

    else if (returnV == -1)
        cout << "Next " << n << " byte(s) doesn't "
             << "represent a valid multibyte character" << endl;
    else
        cout << "Next " << n << " byte(s) of "
             << str << "holds " << returnV << " byte"
             << " multibyte character" << endl;
}

// Driver code
int main()
{
    setlocale(LC_ALL, "en_US.utf8");
    char str[] = "\u10000b5";

    // test for first 1 byte
    check_(str, 1);

    // test for first 6 byte
    check_(str, 6);

    return 0;
}
```

**Output:**

```cpp
Next 1 byte(s) doesn't represent a complete multibyte character
Next 6 byte(s) of á??0b5holds 3 byte multibyte character

```

**程序 2:**

```cpp
// C++ program to illustrate
// mbrlen() function
// with empty string
#include <bits/stdc++.h>
using namespace std;

// Function to find the size of the multibyte character
void check_(const char* str, size_t n)
{
    // Multibyte conversion state
    mbstate_t ps = mbstate_t();

    // number of byte to be saved in returnV
    int returnV = mbrlen(str, n, &ps);

    if (returnV == -2)
        cout << "Next " << n << " byte(s) doesn't"
             << " represent a complete"
             << " multibyte character" << endl;

    else if (returnV == -1)
        cout << "Next " << n << " byte(s) doesn't "
             << "represent a valid multibyte character" << endl;
    else
        cout << "Next " << n << " byte(s) of "
             << str << "holds " << returnV << " byte"
             << " multibyte character" << endl;
}

// Driver code
int main()
{
    setlocale(LC_ALL, "en_US.utf8");
    char str[] = "";

    // test for first 1 byte
    check_(str, 1);

    // test for first 3 byte
    check_(str, 3);

    return 0;
}
```

**Output:**

```cpp
Next 1 byte(s) of holds 0 byte multibyte character
Next 3 byte(s) of holds 0 byte multibyte character

```