# 写一个 C 程序反复打印“GfG”，不使用循环、递归和任何控制结构？

> 原文:[https://www . geesforgeks . org/write-c-program-print-gfg-repeat-not-use-loop-recursion-control-structure/](https://www.geeksforgeeks.org/write-c-program-print-gfg-repeatedly-without-using-loop-recursion-control-structure/)

众所周知，使用各种循环(for 循环、while 循环)、递归和一些控制结构重复打印给定字符串的概念。但问题是，我们将如何重复打印给定的字符串，即无限打印，而不使用任何循环、递归和任何控制结构？

示例:

```cpp
Input  : GFG
Output : GFGGFGGFGGFG...(It will print GFG infinitely).

```

想法是用[系统()](https://www.geeksforgeeks.org/system-call-in-c/)调用程序本身。编译时，我们通过可执行文件名“test”。我们称之为系统(test)，它将重复执行同一个程序，因为系统是一个执行外部命令或可执行文件的函数。

```cpp
// The program is compiled using -O option
// to produce output executable file name
// as "test"
#include<stdio.h>
#include<stdlib.h>
int main()
{
    printf("GFG");
    system("test");
    return 0;
}
```

输出:无限打印 GFG。

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。