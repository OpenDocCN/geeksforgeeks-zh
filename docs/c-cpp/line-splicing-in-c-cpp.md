# C/c++

中的线拼接

> 原文:[https://www.geeksforgeeks.org/line-splicing-in-c-cpp/](https://www.geeksforgeeks.org/line-splicing-in-c-cpp/)

在编写程序时，有时我们会借助单/双注释行在注释部分给出关于代码工作的注释。但是我们从来没有想过，如果在这个注释行的末尾使用\(反斜杠)字符，会发生什么？
以上问题的答案是线拼接。以 a \结尾的行在翻译过程中很早就与下一行拼接在一起。 [2.2 翻译阶段](http://en.cppreference.com/w/cpp/language/translation_phases)。
实际上，无论何时在注释行的末尾，如果我们使用\(反斜杠)字符，它都会将下一行与当前行合并，这使得**也可以将新行作为编译器的注释。**为避免此问题可采用多行注释。

## C

```cpp
// C program to illustrate the concept of Line splicing.
#include <stdio.h>
int main()
{
    // Line Splicing\
    printf("Hello GFG\n");
    printf("welcome\n");
    /* Example 2 - both of the below lines will be printed*/ \
    printf("Hello\t");
    printf("World");
    return (0);
}
```

## **输出:**

欢迎

你好世界

说明:在上面的程序中，我们可以看到当我们在注释行的末尾使用\(反斜杠)字符时。然后，下一行代码在程序中被视为注释，输出是受欢迎的。当我们使用多行注释时，这个问题得到解决，下面两行多行注释都将被打印出来。
本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。