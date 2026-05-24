# 如何用 C 语言编写自己的头文件？

> 原文:[https://www.geeksforgeeks.org/write-header-file-c/](https://www.geeksforgeeks.org/write-header-file-c/)

众所周知。这些头文件通常包含我们可以在我们的主 C 程序中使用的函数声明，例如，需要在我们的 C 程序中包含 stdio.h 才能在程序中使用函数 printf()。所以问题来了，有没有可能创建自己的头文件？

以上答案是**是**。头文件只是一些文件，您可以在其中声明自己的函数，这些函数可以在主程序中使用，也可以在编写大型 C 程序时使用。
**注:**头文件一般包含数据类型、函数原型和 C 预处理器命令的定义。

**下面是创建自己的头文件并相应使用它的简短示例。**

1.  **创建 myhead.h :** 写下面的代码，然后将文件保存为 **myhead.h** 或者你可以给任何名字，但扩展名应该是。h 表示它是一个头文件。

    ```cpp
    // It is not recommended to put function definitions 
    // in a header file. Ideally there should be only
    // function declarations. Purpose of this code is
    // to only demonstrate working of header files.
    void add(int a, int b)
    {
        printf("Added value=%d\n", a + b);
    }
    void multiply(int a, int b)
    {
        printf("Multiplied value=%d\n", a * b);
    }
    ```

2.  **包括。其他程序中的 h 文件:**现在因为我们需要包含 stdio.h 作为#include 以便使用 printf()函数。我们还需要将上面的头文件 myhead.h 作为**#包括“my head . h”**。此处的“”用于指示[预处理器](https://www.geeksforgeeks.org/cc-preprocessors/)查找当前文件夹，如果在当前文件夹中没有找到，则查找所有头文件的标准文件夹。因此，如果您希望使用尖括号而不是" "来包含您的头文件，您可以将其保存在头文件的标准文件夹中，否则。如果您正在使用“”，您需要确保您创建的头文件保存在您将使用此头文件保存 C 文件的同一文件夹中。
3.  **Using the created header file :**

    ```cpp
    // C program to use the above created header file
    #include <stdio.h>
    #include "myhead.h"
    int main()
    {
        add(4, 6);

        /*This calls add function written in myhead.h  
          and therefore no compilation error.*/
        multiply(5, 5);

        // Same for the multiply function in myhead.h
        printf("BYE!See you Soon");
        return 0;
    }
    ```

    输出:

    ```cpp
    Added value:10
    Multiplied value:25
    BYE!See you Soon

    ```

    **注意:**上面的代码编译成功，只有在创建了头文件并将其保存在与上面的 c 文件相同的文件夹中时，才会打印上面的输出。

**要点:**
在编写大型 C 程序时，一般需要创建头文件，这样模块就可以共享函数定义、原型等。

*   函数和类型声明、全局变量、结构声明以及在某些情况下的内联函数；需要集中在一个文件中的定义。
*   在头文件中，不要使用冗余或其他头文件；只有最少的语句集。
*   不要将函数定义放在标题中。把这些东西放在一个单独的。c 文件。
*   包含函数和变量的声明，这些函数和变量的定义对链接器是可见的。此外，在多个源文件之间共享的数据结构和枚举的定义。
*   简而言之，只放必要的东西，保持头文件简洁。

这篇文章只是给你关于头文件的创建和使用的想法，但这并不是你写一个大型 C 程序时实际发生的事情。编写大型 C 程序时，通常需要创建头文件，以便模块可以共享函数定义、原型等。

本文由 [**迪皮·瓦什尼**](https://auth.geeksforgeeks.org/profile.php?user=Dimpy Varshni) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。