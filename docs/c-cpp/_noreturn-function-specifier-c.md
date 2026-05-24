# _ C 中的 Noreturn 函数说明符

> 原文:[https://www . geeksforgeeks . org/_ nore turn-function-说明符-c/](https://www.geeksforgeeks.org/_noreturn-function-specifier-c/)

在去掉“noreturn”关键字后，C 编程语言的 C11 标准(称为最终稿)引入了一个新的“_Noreturn”函数说明符，该说明符指定函数不返回调用它的函数。如果程序员试图从声明为 _Noreturn 类型的函数中返回任何值，那么编译器会自动生成编译时错误。

```cpp
// C program to show how _Noreturn type 
// function behave if it has return statement.
#include <stdio.h>
#include <stdlib.h>

// With return value
_Noreturn void view()
{
    return 10;
}
int main(void)
{
    printf("Ready to begin...\n");
    view();

    printf("NOT over till now\n");
    return 0;
}
```

输出:

```cpp
Ready to begin...
After that abnormal termination of program.
compiler error:[Warning] function declared 'noreturn' has a 'return' statement

```

```cpp
// C program to illustrate the working 
// of _Noreturn type function.
#include <stdio.h>
#include <stdlib.h>

// Nothing to return
_Noreturn void show()
{
    printf("BYE BYE");
}
int main(void)
{
    printf("Ready to begin...\n");
    show();

    printf("NOT over till now\n");
    return 0;
}
```

输出:

```cpp
Ready to begin...
BYE BYE

```

参考:[http://en.cppreference.com/w/c/language/_Noreturn](http://en.cppreference.com/w/c/language/_Noreturn)

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。