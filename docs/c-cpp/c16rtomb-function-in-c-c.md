# C/c++ 中的 c16rtomb()函数

> 原文:[https://www.geeksforgeeks.org/c16rtomb-function-in-c-c/](https://www.geeksforgeeks.org/c16rtomb-function-in-c-c/)

**c16rtomb()** 是 C/C++ 中的内置函数，它将 16 位字符表示转换为窄多字节字符表示。在 C++ 的 **uchar.h** 头文件中定义。

**语法** :

```cpp
size_t c16rtomb(char* s, char16_t c16, mbstate_t* p)
```

**参数**:该函数接受如下所示的三个强制参数:

*   **: Specifies a string that stores multibyte characters.**
***   **C16** : Specify the 16-bit character to be converted.*   **p** : a pointer to the mbstate_t object used to interpret multibyte strings.**

****返回值**:函数返回两个值，如下图:**

*   **程序成功后，函数返回写入 s 指向的字符数组的字节数。**
*   **失败时，返回-1，将 **EILSEQ** 存储在错误号中。**

**下面的程序说明了上面的功能。**

****程序 1** :**

```cpp
// C++ program to illustrate the
// c16rtomb () function on it's success
#include <iostream>
#include <uchar.h>
#include <wchar.h>
using namespace std;

int main()
{
    const char16_t str[] = u"Ishwar Gupta";
    char s[50];
    mbstate_t p{};
    size_t length;
    int j = 0;

    while (str[j]) {
        // initializing the function
        length = c16rtomb(s, str[j], &p);
        if ((length == 0) || (length > 50))
            break;
        for (int i = 0; i < length; ++ i)
            cout << s[i];
        ++ j;
    }

    return 0;
}
```

****输出:**

```cpp
Ishwar Gupta

```

**程序二** :

```cpp
// C++ program to illustrate the
// c16rtomb () function on it's failure
#include <iostream>
#include <uchar.h>
#include <wchar.h>
using namespace std;

int main()
{
    const char16_t str[] = u"";
    char s[50];
    mbstate_t p{};
    size_t length;
    int j = 0;

    while (str[j]) {
        // initializing the function
        length = c16rtomb(s, str[j], &p);
        if ((length == 0) || (length > 50))
            break;
        for (int i = 0; i < length; ++ i)
            cout << s[i];
        ++ j;
    }

    return 0;
}
```

**输出:**

**注**:由于是故障情况，上面的程序没有输出。**