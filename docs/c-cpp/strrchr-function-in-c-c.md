# C/c++

中的 strrchr()函数

> 原文:[https://www.geeksforgeeks.org/strrchr-function-in-c-c/](https://www.geeksforgeeks.org/strrchr-function-in-c-c/)

C/C++ 中的**strchr()**函数定位字符串中最后一个出现的字符。它返回一个指向字符串中最后一个匹配项的指针。终止的空字符被认为是 C 字符串的一部分。因此，也可以定位它来检索指向字符串末尾的指针。在 **cstring** 头文件中定义。
**语法:**

```cpp
const char* strrchr( const char* str, int ch )
            or
char* strrchr( char* str, int ch )

```

**参数:**该函数采用两个强制参数，描述如下:

*   **字符串:**指定要搜索的空终止字符串的指针。
*   **ch:** 指定要搜索的字符。

**返回值:**如果找到了 **ch** ，该函数返回一个指向字符串中 **ch** 最后位置的指针。如果没有找到，它将返回一个空指针。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate
// the strrchr() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Storing it in string array
    char string[] = "Geeks for Geeks";

    // The character we've to search for
    char character = 'k';

    // Storing in a pointer ptr
    char* ptr = strrchr(string, character);

    // ptr-string gives the index location
    if (ptr)
        cout << "Last position of " << character
             << " in " << string << " is " << ptr - string;

    // If the character we're searching is not present in the array
    else
        cout << character << " is not present "
             << string << endl;
    return 0;
}
```

**Output:**

```cpp
Last position of k in Geeks for Geeks is 13

```

**程序 2:**

```cpp
// C++ program to illustrate 
// the strrchr() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Storing it in string array
    char string[] = "Geeks for Geeks";
    char* ptr;

    // The character we've to search for
    char character = 'z';

    // Storing in a pointer ptr
    ptr = strrchr(string, character);

    // ptr-string gives the index location
    if (ptr)
        cout << "Last position of " << character
             << " in " << string << " is " << ptr - string;

    // If the character we're searching
    // is not present in the array
    else
        cout << character << " is not present in "
             << string << endl;
    return 0;
}
```

**Output:**

```cpp
z is not present in Geeks for Geeks

```