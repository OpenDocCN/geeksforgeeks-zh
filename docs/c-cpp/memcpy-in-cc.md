# C/c++

中的 memcpy()

> 原文:[https://www.geeksforgeeks.org/memcpy-in-cc/](https://www.geeksforgeeks.org/memcpy-in-cc/)

memcpy()用于将一个内存块从一个位置复制到另一个位置。在**字符串中声明**

```cpp
// Copies "numBytes" bytes from address "from" to address "to"
void * memcpy(void *to, const void *from, size_t numBytes);
```

下面是一个展示 memcpy()工作原理的 C 程序示例。

## C

```cpp
/* A C program to demonstrate working of memcpy */
#include <stdio.h>
#include <string.h>

int main ()
{
  char str1[] = "Geeks"; 
  char str2[] = "Quiz"; 

  puts("str1 before memcpy ");
  puts(str1);

  /* Copies contents of str2 to str1 */
  memcpy (str1, str2, sizeof(str2));

  puts("\nstr1 after memcpy ");
  puts(str1);

  return 0;
}
```

输出:

```cpp
str1 before memcpy 
Geeks

str1 after memcpy 
Quiz
```

**注意:**
1) memcpy()不检查溢出或\0
2) memcpy()在源地址和目的地址重叠时导致问题。

[**memmove()**](https://www.geeksforgeeks.org/memmove-in-cc/) 是另一个很好处理重叠的库函数。
[自己写 memcpy()和 memmove()](https://www.geeksforgeeks.org/write-memcpy/)
发现有不正确的地方请写评论，或者想分享更多以上讨论话题的信息