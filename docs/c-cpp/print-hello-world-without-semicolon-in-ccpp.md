# 用 C/C++ 打印不带分号的 Hello World】

> 原文:[https://www . geesforgeks . org/print-hello-world-不带分号的 in-ccpp/](https://www.geeksforgeeks.org/print-hello-world-without-semicolon-in-ccpp/)

根据基本原则，C++ 中的每条语句都必须以分号结尾。然而，与其他语言不同，C++ 中几乎所有的语句都可以被视为表达式。然而，我们很少能写出没有分号的运行程序。
如果我们用一对空括号将语句放在 if/switch/while/macro 语句中，就不必用分号结束。此外，调用返回 void 的函数在这里不起作用，因为 void 函数不是表达式。我们可以使用逗号运算符，运算符右侧的任何值。
**举例:**

1.  **Using [if statement](https://www.geeksforgeeks.org/decision-making-c-c-else-nested-else/):**

    ```cpp
    // CPP program to print
    // Hello World without semicolon
    // using if statement
    #include <iostream>
    int main()
    {
        if (std::cout << "Hello World ") 
        {
        }
    }
    ```

    输出:

    ```cpp
    Hello World
    ```

2.  **Using [switch statement](https://www.geeksforgeeks.org/switch-statement-cc/):**

    ```cpp
    // CPP program to print
    // Hello World without semicolon
    // using switch statement
    #include <stdio.h>
    int main()
    {
        switch (printf("Hello World ")) 
        {

        }
    }
    ```

    输出:

    ```cpp
    Hello World 
    ```

3.  **Using [macros](https://www.geeksforgeeks.org/cc-preprocessors/)**

    ```cpp
    // CPP program to print
    // Hello World without semicolon
    // using macros
    #include <stdio.h>
    #define GEEK printf("Hello World")
    int main()
    {
        if (GEEK)
        {
        }
    }
    ```

    输出:

    ```cpp
    Hello World 
    ```

4.  **使用[循环(while and for)](https://www.geeksforgeeks.org/loops-in-c/) :这里要注意的是使用！(不是运算符)在 while 循环中，以避免无限循环。

    ```cpp
    // CPP program to print 
    // Hello World without semicolon
    // using if statement
    #include<iostream>
    int main()
    {
        while (!(std::cout << "Hello World"))
        { }

        // for loop can also be used
        // where testing condition has cout statement
        // for (;!(std::cout << "Hello World");)
        // { }
    }
    ```

    ```cpp
    Hello World 
    ```** 

**相关文章:** [如何打印分号(；)在 C/C++ 中不使用分号？](https://www.geeksforgeeks.org/print-a-semicolon-without-using-semicolon-in-ccpp/)

本文由 **Avni Nargwani** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。