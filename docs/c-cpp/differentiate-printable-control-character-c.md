# 用 C 区分可打印字符和控制字符？

> 原文:[https://www . geesforgeks . org/different-printable-control-character-c/](https://www.geeksforgeeks.org/differentiate-printable-control-character-c/)

给定一个字符，我们需要找到它是否可打印。我们还需要找到它是否是控制字符。如果字符占用打印空间，则称为可打印字符。
对于标准 ASCII 字符集(由“C”语言环境使用)，控制字符是介于 ASCII 码 0x00 (NUL)和 0x1f(美国)之间的字符，加上 0x7f (DEL)。

示例:

```cpp
Input : a
Output :a is printable character
        a is not control character

Input :\r
Output : is not printable character
         is control character

```

为了找出可打印字符和控制字符之间的区别，我们可以使用一些预定义的函数，这些函数在“ctype.h”头文件中声明。

i **sprint()** 函数检查一个字符是否是可打印字符。isprint()函数接受整数形式的单个参数，并返回 int 类型的值。我们可以在内部传递一个字符类型参数，它们通过指定 ASCII 值来充当 int。

**is centrl()**功能用于检查字符是否为控制字符。iscntrl()函数也接受一个参数并返回一个整数。

```cpp
// C program to illustrate isprint() and iscntrl() functions.
#include <stdio.h>
#include <ctype.h>
int main(void)
{
    char ch = 'a';
    if (isprint(ch)) {
        printf("%c is printable character\n", ch);
    } else {
        printf("%c is not printable character\n", ch);
    }

    if (iscntrl(ch)) {
        printf("%c is control character\n", ch);
    } else {
        printf("%c is not control character", ch);
    }
    return (0);
}
```

输出:

```cpp
a is printable character
a is not control character

```

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。