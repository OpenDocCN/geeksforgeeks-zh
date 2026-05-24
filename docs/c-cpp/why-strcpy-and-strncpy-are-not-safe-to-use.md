# 为什么 strcpy 和 strncpy 使用不安全？

> 原文:[https://www . geesforgeks . org/why-strcpy-和-strncpy-使用不安全/](https://www.geeksforgeeks.org/why-strcpy-and-strncpy-are-not-safe-to-use/)

**strcpy()功能**

[strcpy()](https://www.geeksforgeeks.org/strcpy-in-c-cpp/) 函数用于将源字符串复制到目标字符串。如果目标字符串的缓冲区大小大于 src 字符串，则将 src 字符串复制到带有终止空字符的目标字符串。但是如果目的缓冲区较少，那么 src 将复制内容而不终止空字符。字符串不能重叠，目标字符串必须足够大才能接收副本。

**语法:**

```cpp
char *strcpy( char *dest, const char *src )
```

**参数:**该函数接受两个参数，如上所述，如下所述:

*   **src:** 将要复制的字符串。
*   **dest:** 指向要复制内容的目标数组的指针。

**返回值:**返回一个指向目标字符串的指针。

```cpp
// C Program  to illustrate the 
// strcpy() function in C/C++
#include <stdio.h>
#include <string.h>
int main()
{
    char src[] = "geeksforgeeks";

    // Here destination is large enough
    // to store the src with Null 
    // character at the end
    char dest[14];

    // copying src into dest.
    strcpy(dest, src);
    printf("Copied string: %s\n", dest);

    return 0;
}
```

**Output:**

```cpp
Copied string: geeksforgeeks

```

**strcpy()的问题:**strcpy()函数没有指定目标数组的大小，因此缓冲区溢出通常是一个风险。使用 strcpy()函数将一个大的字符数组复制到一个小的数组中是危险的，但是如果字符串适合，那么就不值得冒这个风险。如果目标字符串不足以存储源字符串，那么 strcpy()的行为是未指定或未定义的。

```cpp
// C Program  to illustrate the problem in 
// strcpy() function in C/C++
#include <stdio.h>
#include <string.h>
int main()
{
    char src[] = "geeksforgeeks";

    // Here destination is not large
    // enough to store the src. so the
    // behaviour of strcpy is unspecified.
    // program may crashed, but its
    // printing geeksforgeeks
    char dest[2];

    // copying src into dest.
    strcpy(dest, src);
    printf("Copied string: %s\n", dest);

    return 0;
}
```

**Output:**

```cpp
Copied string: geeksforgeeks

```

**strncpy()功能**

strncpy()函数类似于 strcpy()函数，只是最多复制 n 个字节的 src。如果 src 的前 n 个字符中没有空字符，则放置在 dest 中的字符串不会以空结尾。如果 src 的长度小于 n，strncpy()会向 dest 写入额外的空字符，以确保总共写入 n 个字符。

**语法:**

```cpp
char *strncpy( char *dest, const char *src, size_t n )
```

**参数:**该函数接受两个参数，如上所述，如下所述:

*   **src:** 将要复制的字符串。
*   **dest:** 指向要复制内容的目标数组的指针。
*   **n:** 从 src 复制到 dest 的前 n 个字符。

**返回值:**返回一个指向目标字符串的指针。

**示例:**

```cpp
// C Program  to illustrate the 
// strcpy() function in C/C++
#include <stdio.h>
#include <string.h>
int main()
{
    char src[] = "geeksforgeeks";

    // The destination string size is 14.
    char dest[14];

    // copying n bytes of src into dest.
    strncpy(dest, src, 14);
    printf("Copied string: %s\n", dest);

    return 0;
}
```

**Output:**

```cpp
Copied string: geeksforgeeks

```

【strncpy()的问题:如果 src 的前 n 个字符中没有空字符，则放置在 dest 中的字符串不会被空终止。因此 strncpy()不能保证目标字符串将被空终止。strlen()非终止字符串会导致 segfault。换句话说，C/C++ 中的非终止字符串是一个等待破坏代码的定时炸弹。

```cpp
// C Program  to illustrate the problem in 
// strcpy() function in C/C++
#include <stdio.h>
#include <string.h>
int main()
{
    char src[] = "geeksforgeeks";

    // The destination sting size is 8
    // which is less than length of src.
    char dest[8];

    // copying 8 bytes of src into dest.
    // dest is not NULL terminated.
    strncpy(dest, src, 8);

    // using strlen function on non terminated.
    // string which can cause segfault.
    int len = strlen(dest);

    printf("Copied string: %s\n", dest);
    printf("Length of destination string: %d\n", len);

    return 0;
}
```

**Output:**

```cpp
Copied string: geeksfor
Length of destination string: 8

```

现在，下一个问题是，任何保证目标字符串将被空终止并且没有缓冲区溢出机会的函数？

所以，上述问题的答案是“是”，在“stdio.h”库中有几个函数可以保证满足上述条件。

*   **[【snprintf】](https://www.geeksforgeeks.org/snprintf-c-library/)**
*   str lcpy

这两个函数都保证目标字符串将以空终止。类似地， [snprintf()函数](https://www.geeksforgeeks.org/snprintf-c-library/)，strlcpy 函数将最多 dest_size-1 个字符(dest_size 是目标字符串缓冲区的大小)从 src 复制到 dst，必要时截断 src。结果总是以 null 结尾。该函数返回 strlen(src)。可以按如下方式检查缓冲区溢出:

```cpp
 if (strlcpy(dst, src, dstsize) >= dest_size)
         return -1;

```

根据健全程度对功能进行排序:

```cpp
strcpy < strncpy < snprintf < strlcpy

```