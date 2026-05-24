# C/c++

中的 strcspn()函数

> 原文:[https://www.geeksforgeeks.org/strcspn-function-in-c-c/](https://www.geeksforgeeks.org/strcspn-function-in-c-c/)

C/C++ 中的**strcpn()**函数将两个字符串作为输入， **string_1** 和 **string_2** 作为参数，并通过遍历字符串 _2 中的任何字符来搜索字符串 _1。如果在 string_1 中找不到 string_2 的任何字符，该函数将返回 string_1 的长度。该功能在 **cstring** 头文件中定义。

**语法:**

```cpp
size_t strcspn ( const char *string_1, const char *string_2 ) 

```

**参数:**该功能接受两个强制参数，如下所述:

*   **string_1:** 指定要搜索的字符串
*   **string_2:** 指定包含要匹配的字符的字符串

**返回值:**该函数返回字符串 _1 中在字符串 _2 中匹配的任何字符之前遍历的字符数。

以下程序说明了上述功能:

**程序 1:**

```cpp
// C++ program to illustrate the
// strcspn() function
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // String to be travered
    char string_1[] = "geekforgeeks456";

    // Search these characters in string_1
    char string_2[] = "123456789";

    // function strcspn() traverse the string_1
    // and search the characters of string_2
    size_t match = strcspn(string_1, string_2);

    // if matched return the position number
    if (match < strlen(string_1))
        cout << "The number of characters before"
             << "the matched character are " << match;

    else
        cout << string_1 << 
        " didn't matched any character from string_2 ";
    return 0;
}
```

**Output:**

```cpp
The number of characters beforethe matched character are 12

```

**程序 2:**

```cpp
// C++ program to illustrate the
// strcspn() function When the string
// containing the character to be
// matched is empty
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // String to be travered
    char string_1[] = "geekforgeeks456";

    // Search these characters in string_1
    char string_2[] = ""; // Empty

    // function strcspn() traverse the string_1
    // and search the characters of string_2
    size_t match = strcspn(string_1, string_2);

    // if matched return the position number
    if (match < strlen(string_1))
        cout << "The number of character before"
             << "the matched character are " << match;
    else
        cout << string_1 << 
        " didn't matched any character from string_2  ";
    return 0;
}
```

**Output:**

```cpp
geekforgeeks456 didn't matched any character from string_2

```