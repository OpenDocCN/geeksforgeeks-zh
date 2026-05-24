# 在C中设置(功能)

> 原文:[https://www.geeksforgeeks.org/strnset-function-in-c/](https://www.geeksforgeeks.org/strnset-function-in-c/)

`strnset()`函数是C语言中的一个内置函数，它将字符串的前n个字符设置为一个给定的字符。如果n大于字符串的长度，则使用字符串的长度来代替n。

**语法:**

```cpp
char *strnset(const char *str, char ch, int n);
```

**参数:**

*   `str`: 这是给定字符替换某些字符的原始字符串。
*   `ch`: `ch`代表给定的字符。
*   `n`: `n`表示被给定字符替换的字符数。

**返回值**: 返回替换给定字符串的前`n`个字符后得到的修改后的字符串。

下面的程序说明了C语言中的`strnset()`函数:

**程序1:**

```cpp
// C program to illustrate 
// the strnset() function

#include <stdio.h>
#include <string.h>

int main()
{
    char str[] = "GeeksforGeeks";

    printf("Original String: %s\n", str);

    // First 5 character of string str
    // replaced by character '*'
    printf("Modified String: %s\n", strnset(str, '*', 5));

    return 0;
}
```

**输出:**

```
Original String: GeeksforGeeks
Modified String: *****forGeeks
```

**程序2:**

```cpp
// C program to illustrate 
// the strnset() function

#include <stdio.h>
#include <string.h>

int main()
{
    char str[] = "Computer Science";

    printf("Original String: %s\n", str);

    // First 5 character of string str
    // replaced by character '*'
    printf("Modified String: %s\n", strnset(str, '*', 5));

    return 0;
}
```

**输出:**

```
Original String: Computer Science
Modified String: *****ter Science
```

**注意**: `strnset()`函数不是标准C库的一部分，因此可能无法在在线编译器上运行。