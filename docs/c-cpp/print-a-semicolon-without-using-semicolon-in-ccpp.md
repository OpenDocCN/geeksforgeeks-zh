# 如何打印分号(；)在 C/C++ 中不使用分号？

> 原文:[https://www . geesforgeks . org/print-a-分号-不使用分号-in-ccpp/](https://www.geeksforgeeks.org/print-a-semicolon-without-using-semicolon-in-ccpp/)

另一个有趣的问题是，如何在程序中不使用任何分号的情况下打印分号。下面是打印“；”的方法:

1.  **在 [if 语句中使用 printf/putchar](https://www.geeksforgeeks.org/decision-making-c-c-else-nested-else/):**

    ```cpp
    // CPP program to print 
    // ; without using ;
    // using if statement
    #include <stdio.h>
    int main()
    {
        // ASCII value of semicolon = 59
        if (printf("%c\n", 59))
        if (putchar(59))
        {
        }
        return 0;
    }
    ```

    输出:

    ```cpp
    ;
    ;

    ```

    我们也可以使用 switch/ while / for 来打印分号，如[这篇](https://www.geeksforgeeks.org/print-hello-world-without-semicolon-in-ccpp/)文章所示。

2.  **使用[宏:](https://www.geeksforgeeks.org/cc-preprocessors/)**

    ```cpp
    // CPP program to print 
    // ; without using ;
    // using macros
    #include <stdio.h>
    #define GEEK printf("%c",59)
    int main()
    {
        if (GEEK)
        {
        }
    }
    ```

    输出:

    ```cpp
    ;

    ```

**相关文章:**[C/c++ ](https://www.geeksforgeeks.org/print-hello-world-without-semicolon-in-ccpp/)无分号打印 Hello World

如果你喜欢 GeeksforGeeks 并想投稿，你也可以用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。