# scanf()函数中的字符串为什么不用“&”？

> 原文:[https://www . geesforgeks . org/未使用字符串-scanf-function/](https://www.geeksforgeeks.org/not-used-strings-scanf-function/)

下面是 Scanf 的语法。它需要两个参数:

```cpp
scanf("Format Specifier", Variable Address);

Format Specifier: Type of value to expect while input
Variable Address: &variable returns the variable's memory address.

```

在字符串(字符数组)的情况下，变量本身指向有问题的数组的第一个元素。因此，不需要使用' & '运算符来传递地址。

```cpp
// C program to illustrate  not using "&"
// in scanf statement
#include<stdio.h>
int main()
{
    char name[25];

    // Syntax to scan a String
    scanf("%s", name);

    // Comparing base address of String with adrress
    // of first element of array which must return
    // true as both must be same
    printf("(Is Base address = address of first element)? \n %d",
           (name == &name[0]));

}
```

输出:

```cpp
(Is Base address = address of first element)?
1

```

**要点**

1.  “&”用于获取变量的地址。c 没有字符串类型，字符串只是一个字符数组，数组变量存储第一个索引位置的地址。
2.  默认情况下，变量本身指向基地址，因此要访问字符串的基地址，不需要添加额外的' & '

本文由 **Ajeet** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。