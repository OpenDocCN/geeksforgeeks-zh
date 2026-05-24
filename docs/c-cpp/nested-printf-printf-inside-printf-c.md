# 嵌套在 C

中的 printf (printf 内部的 printf)

> 原文:[https://www . geesforgeks . org/nested-printf-printf-inside-printf-c/](https://www.geeksforgeeks.org/nested-printf-printf-inside-printf-c/)

用 printf 中的 printf 预测下面 C 程序的输出。

```cpp
#include<stdio.h>

int main()
{
   int x = 1987;
   printf("%d", printf("%d", printf("%d", x)));
   return(0);
}
```

**输出**:

```cpp
198741

```

**解说** :
1。首先，执行最里面的打印，导致 1987 年打印

2.此 **printf** 返回 1987 年的总位数，即 4。printf()返回屏幕上成功打印的字符数。整句话可以归纳为:

```cpp
printf("%d", printf("%d", 4));
```

3.第二次**打印**然后打印 4 并返回 4 中的总位数，即 1 (4 是一位数)。

4.最后，整个陈述简单地归纳为:

```cpp
printf("%d", 1);
```

5.它只打印 1，输出将是:

输出:

```cpp
198741

```

因此，当多个 **printf 的**出现在另一个 **printf 的**中时，内部的 **printf** 打印其输出，并将屏幕上打印的字符串长度返回给外部的 **printf** 。

本文由**里沙夫·拉吉**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。