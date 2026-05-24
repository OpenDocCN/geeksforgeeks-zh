# C/c++

中的 memmove()

> 原文:[https://www.geeksforgeeks.org/memmove-in-cc/](https://www.geeksforgeeks.org/memmove-in-cc/)

memmove()用于将内存块从一个位置复制到另一个位置。在**字符串中声明**

```cpp
// Copies "numBytes" bytes from address "from" to address "to"
void * memmove(void *to, const void *from, size_t numBytes);

```

下面是一个演示 memmove()工作原理的 C 程序示例。

## C

```cpp
/* A C program to demonstrate working of memmove */
#include <stdio.h>
#include <string.h>

int main()
{
    char str1[] = "Geeks"; // Array of size 100
    char str2[] = "Quiz"; // Array of size 5

    puts("str1 before memmove ");
    puts(str1);

    /* Copies contents of str2 to sr1 */
    memmove(str1, str2, sizeof(str2));

    puts("\nstr1 after memmove ");
    puts(str1);

    return 0;
}
```

**Output**

```cpp
str1 before memmove 
Geeks

str1 after memmove 
Quiz

```

**与** [**memcpy()**](https://www.geeksforgeeks.org/memcpy-in-cc/) **有何不同？**

memcpy()只是将数据一个接一个地从一个位置复制到另一个位置。另一方面，memmove()首先将数据复制到中间缓冲区，然后从缓冲区复制到目的地。
memcpy()在字符串重叠时会导致问题。

例如，考虑下面的程序。

## C

```cpp
// Sample program to show that memcpy() can lose data.
#include <stdio.h>
#include <string.h>
int main()
{
    char csrc[100] = "Geeksfor";
    memcpy(csrc + 5, csrc, strlen(csrc) + 1);
    printf("%s", csrc);
    return 0;
}
```

**Output**

```cpp
GeeksGeeksfor
```

由于输入地址重叠，上述程序会覆盖原始字符串并导致数据丢失。

考虑下面的程序，了解 memcpy 和 memmove 函数在发生重叠时的区别。

## C

```cpp
// Sample program to show that memmove() is better than
// memcpy() when addresses overlap.
#include <stdio.h>
#include <string.h>
int main()
{
    char str[100] = "Learningisfun";
    char *first, *second;
    first = str;
    second = str;
    printf("Original string :%s\n ", str);

    // when overlap happens then it just ignore it
    memcpy(first + 8, first, 10);
    printf("memcpy overlap : %s\n ", str);

    // when overlap it start from first position
    memmove(second + 8, first, 10);
    printf("memmove overlap : %s\n ", str);

    return 0;
}
```

**Output**

```cpp
Original string :Learningisfun
 memcpy overlap : LearningLearningis
 memmove overlap : LearningLearningLe

```

使用 memmove 函数可以清楚地看到，每当发生重叠时(即当第一个指针移动到字符‘I’时)，第一个指针将从开头开始打印(输出 Le)，但是使用 memcpy 函数，它只是忽略是否有重叠，并继续向前移动。

[自己写 memcpy()和 memmove()？](https://www.geeksforgeeks.org/write-memcpy/)
如果发现有不正确的地方，请写评论，或者想分享更多关于以上讨论话题的信息