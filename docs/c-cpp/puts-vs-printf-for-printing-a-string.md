# puts() vs printf()用于打印字符串

> 原文:[https://www . geesforgeks . org/puts-vs-printf-for-printing-a-string/](https://www.geeksforgeeks.org/puts-vs-printf-for-printing-a-string/)

在 C 语言中，给定一个字符串变量 *str* ，下面两个应该选择哪个打印到 stdout？

```cpp
1) puts(str);
```

```cpp
2) printf(str);
```

puts()是打印字符串的首选方法，因为它通常比较便宜(puts()的实现通常比 printf()简单)，如果字符串包含像“%s”这样的格式化字符，那么 printf()会给出意想不到的结果。另外，如果 str 是用户输入字符串，那么使用 printf()可能会导致安全问题(详见[本](http://www.cis.syr.edu/~wedu/seed/Labs/Vulnerability/Format_String/files/formatstring-1.2.pdf))。
还要注意 puts()将光标移动到下一行。如果不希望光标移动到下一行，则可以使用以下 puts()变体。

```cpp
fputs(str, stdout)
```

您可以尝试以下程序来测试 puts()和 printf()之间的上述差异。

**程序 1**

## C

```cpp
// C program to show the use of puts
#include <stdio.h>
int main()
{
    puts("Geeksfor");
    puts("Geeks");

    getchar();
    return 0;
}
```

**程序 2**

## C

```cpp
// C program to show the use of fputs and getchar
#include <stdio.h>
int main()
{
    fputs("Geeksfor", stdout);
    fputs("Geeks", stdout);

    getchar();
    return 0;
}
```

**程序 3**

## C

```cpp
// C program to show  the side effect of using
// %s in printf
#include <stdio.h>
int main()
{
    // % is intentionally put here to show side effects of
    // using printf(str)
    printf("Geek%sforGeek%s");
    getchar();
    return 0;
}
```

**程序 4**

## C

```cpp
// C program to show the use of puts
#include <stdio.h>
int main()
{
    puts("Geek%sforGeek%s");
    getchar();
    return 0;
}
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。