# std::strncmp()在 C++ 中

> 原文: [https://www.geeksforgeeks.org/stdstrncmp-in-c/](https://www.geeksforgeeks.org/stdstrncmp-in-c/)

`std::strncmp()` 函数按字典顺序比较两个以 null 结尾的字符串中不超过计数的字符，并根据结果返回一个整数。

*   此函数接受两个字符串和一个数字 `num` 作为参数，最多比较两个字符串的前 `num` 个字节。
*   `num` 应最多等于最长字符串的长度。如果 `number` 被定义为大于字符串的长度，则比较会持续到任一字符串遇到空字符（'\0'）。
*   此函数按字典顺序比较两个字符串。它从每个字符串的第一个字符开始比较。如果它们相等，则继续比较每个字符串的下一个字符，依此类推。
*   比较过程直到遇到任一字符串的结尾 null 字符或两个字符串的前 `number` 个字符匹配时停止。

## 语法

```cpp
int strncmp(const char *str1, const char *str2, size_t count);
```

**参数:**
`str1` 和 `str2`: 要比较的 C 字符串。
`count`: 要比较的最大字符数。
`size_t` 是一种无符号整数类型。

**返回值:**
| 值 | 含义 |
| --- | --- |
| 小于零 | `str1` 小于 `str2`。 |
| 零 | `str1` 等于 `str2`。 |
| 大于零 | `str1` 大于 `str2`。 |

如果任一字符串中的字符少于 `count`，则当遇到第一个 null 时，比较结束。

## strcmp()返回什么？

`strncmp()` 函数在比较的基础上返回三种不同类型的整数值:

### 1. 大于零(> 0)
如果 `str1` 和 `str2` 的字符在 `num` 个字符之前不匹配，并且 `str1` 字符的 ASCII 值大于 `str2` 字符的 ASCII 值，则返回正值。因此，我们可以说 `str1` 在词汇上大于 `str2`。

```cpp
// C, C++ program to demonstrate
// functionality of strncmp()

#include <stdio.h>
#include <string.h>

int main()
{
    // Take any two strings
    char str1[10] = "aksh";
    char str2[10] = "akash";

    // Compare strings using strncmp()
    int result = strncmp(str1, str2, 4);

    if (result == 0) {
        // num is the 3rd parameter of strncmp() function
        printf("str1 is equal to str2 upto num characters\n");
    }
    else if (result > 0)
        printf("str1 is greater than str2\n");
    else
        printf("str2 is greater than str1\n");

    printf("Value returned by strncmp() is: %d", result);

    return 0;
}
```

输出:

```cpp
str1 is greater than str2
Value returned by strncmp() is: 18
```

### 2. 小于零(< 0)
如果 `str1` 和 `str2` 的字符在 `num` 个字符之前不匹配，并且 `str1` 字符的 ASCII 值小于 `str2` 字符的 ASCII 值，则返回负值。因此，我们可以说 `str2` 在词汇上大于 `str1`。

```cpp
// C, C++ program to demonstrate
// functionality of strncmp()

#include <stdio.h>
#include <string.h>

int main()
{
    // Take any two strings
    char str1[10] = "akash";
    char str2[10] = "aksh";

    // Compare strings using strncmp()
    int result = strncmp(str1, str2, 4);

    if (result == 0) {
        // num is the 3rd parameter of strncmp() function
        printf("str1 is equal to str2 upto num characters\n");
    }
    else if (result > 0)
        printf("str1 is greater than str2\n");
    else
        printf("str2 is greater than str1\n");

    printf("Value returned by strncmp() is: %d", result);

    return 0;
}
```

输出:

```cpp
str2 is greater than str1
Value returned by strncmp() is: -18
```

### 3. 等于零(0)
如果 `str1` 的字符与 `str2` 的前 `num` 个字符匹配，则该函数返回零。因此，我们不能说 `str1` 等于 `str2`，除非 `num` 等于任一字符串的长度。

```cpp
// C, C++ program to demonstrate
// functionality of strncmp()

#include <stdio.h>
#include <string.h>

int main()
{
    // Take any two strings
    char str1[10] = "akash";
    char str2[10] = "akas";

    // Compare strings using strncmp()
    int result = strncmp(str1, str2, 4);

    if (result == 0) {
        // num is the 3rd parameter of strncmp() function
        printf("str1 is equal to str2 upto num characters\n");
    }
    else if (result > 0)
        printf("str1 is greater than str2\n");
    else
        printf("str2 is greater than str1\n");

    printf("Value returned by strncmp() is: %d", result);

    return 0;
}
```

输出:

```cpp
str1 is equal to str2 upto num characters
Value returned by strncmp() is: 0
```

**注意:** 当字符串不同时，您会发现 `strncmp()` 函数返回的值是两种情况下 `str1` 和 `str2` 中第一个不匹配字符的 ASCII 值之差。

## 更多示例

### 例 1

```cpp
// CPP program to illustrate strncmp()
#include <cstring>
#include <iostream>

void display(char* abc, char* xyz, int res, int count)
{
    if (res > 0)
        std::cout << xyz << " come-before " << abc;
    else if (res < 0)
        std::cout << abc << " come-before " << xyz;
    else
        std::cout << "First " << count << " characters of string "
        << abc << " and " << xyz << " are same";
}

int main()
{
    char abc[] = "GeeksforGeeks";
    char xyz[] = "Geeks";
    int res;
    res = std::strncmp(abc, xyz, 4);
    display(abc, xyz, res, 4);
    return 0;
}
```

输出:

```cpp
First 4 characters of string GeeksforGeeks and Geeks are same
```

### 例 2

```cpp
// CPP program to illustrate strncmp()
#include <cstring>
#include <iostream>

void display(char* abc, char* xyz, int res, int count)
{
    if (res > 0)
        std::cout << xyz << " come-before " << abc;
    else if (res < 0)
        std::cout << abc << " come-before " << xyz;
    else
        std::cout << "First " << count << " characters of string " <<
        abc << " and " << xyz << " are same";
    ;
}

int main()
{
    char abc[] = "GeeksforGeeks";
    char xyz[] = "Geeks";
    int res;
    res = std::strncmp(abc, xyz, 6);
    display(abc, xyz, res, 6);
    return 0;
}
```

输出:

```cpp
Geeks come-before GeeksforGeeks
```

本文由**阿卡什·古普塔**和**希瓦尼·格什蒂亚尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。