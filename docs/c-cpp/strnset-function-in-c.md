# 在 C

中设置(功能)

> 原文:[https://www.geeksforgeeks.org/strnset-function-in-c/](https://www.geeksforgeeks.org/strnset-function-in-c/)

**strnet()**函数是 C 语言中的一个内置函数，它将字符串的前 n 个字符设置为一个给定的字符。如果 n 大于字符串的长度，则使用字符串的长度来代替 n。

**语法:**

```cpp
char *strnset(const char *str, char ch, int n);

```

**参数:**

*   **字符串:**这是给定字符替换某些字符的原始字符串。
*   **ch:** ch 代表给定的字符。
*   **n:** n 表示被给定字符替换的字符数。

**返回值**:返回替换给定字符串的第一个![n](img/42ce0a847b20a2f8a781c8a50bdab975.png "Rendered by QuickLaTeX.com")字符后得到的修改后的字符串。

下面的程序说明了 C 语言中的 strnset()函数:

**程序 1:**

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

```cpp
Original String: GeeksforGeeks
Modified String: *****forGeeks

```

**程序 2:**

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

```cpp
Original String: Computer Science
Modified String: *****ter Science

```

**注意**:str set()函数不是标准 C 库的一部分，因此可能无法在在线编译器上运行。