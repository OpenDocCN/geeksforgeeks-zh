# C/c++

中的 strdup()和 strndup()函数

> 原文:[https://www.geeksforgeeks.org/strdup-strdndup-functions-c/](https://www.geeksforgeeks.org/strdup-strdndup-functions-c/)

**strdup()** 和 **strndup()** 函数用于复制字符串。
**strdup() :**
<u>语法:</u>*char * strdup(const char * s)；*
该函数返回一个指向空终止字节字符串的指针，该字符串与 ***s*** 指向的字符串重复。获得的内存使用 [malloc](https://www.geeksforgeeks.org/calloc-versus-malloc/) 动态完成，因此可以使用 [free()](https://www.geeksforgeeks.org/g-fact-30/) 释放。
它返回一个指向重复字符串 ***s*** 的指针。
下面是 C 实现，展示了 strdup()函数在 C 中的使用:

## C

```cpp
// C program to demonstrate strdup()
#include<stdio.h>
#include<string.h>

int main()
{
    char source[] = "GeeksForGeeks";

    // A copy of source is created dynamically
    // and pointer to copy is returned.
    char* target = strdup(source);

    printf("%s", target);
    return 0;
}
```

输出:

```cpp
GeeksForGeeks
```

**strndup() :**
<u>语法</u>:*char * strn dup(const char * s，size _ t n)；*
该功能与 strdup()类似，但最多复制 **n** 个字节。
**注**:如果 s 大于 n，则只复制 n 个字节，末尾加一个 NULL(' 0 ')。
下面是 C 实现，展示了 strndup()函数在 C 中的使用:

## C

```cpp
// C program to demonstrate strndup()
#include<stdio.h>
#include<string.h>

int main()
{
    char source[] = "GeeksForGeeks";

    // 5 bytes of source are copied to a new memory
    // allocated dynamically and pointer to copied
    // memory is returned.
    char* target = strndup(source, 5);

    printf("%s", target);
    return 0;
}
```

输出:

```cpp
Geeks
```

参考: [Linux 人(7)](http://man7.org/linux/man-pages/man3/strdupa.3.html)
本文由 **MAZHAR IMAM KHAN** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。