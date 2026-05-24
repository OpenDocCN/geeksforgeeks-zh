# 在 C++ 中用空的或者空白的主页面打印“Hello World”

> 原文:[https://www . geesforgeks . org/print-hello-world-empty-blank-main-c/](https://www.geeksforgeeks.org/print-hello-world-empty-blank-main-c/)

用 C++ 写一个打印“Hello World”的程序，它有一个主函数，主函数体是空的。

以下是两种不同的解决方案。

*   我们可以创建一个全局变量，并为其分配 printf()的返回值，该返回值打印“Hello World”

    ```cpp
    // C++ program to print something with empty main()
    #include <bits/stdc++.h>

    int x = printf("Hello World");

    int main()
    {
        // Blank
    }
    ```

*   我们可以在 C++ 中使用[构造函数](https://www.geeksforgeeks.org/constructors-c/)。在下面的程序中，我们在主函数的外部创建了一个类“A”的对象，这样对象声明的时候就可以调用构造函数，这样就可以打印“Hello World”了。

    ```cpp
    // C++ program to print something with empty main()
    #include <iostream>
    using namespace std;

    class A {
    public:
        A() // Constructor
        {
            cout << "Hello World";
        }
    };

    A obj; // Create Object of class A

    int main()
    {
        // Blank
    }
    ```

**相关文章:**
[如何在 C、C++ 和 Java 中用空 main()打印“GeeksforGeeks”？](https://www.geeksforgeeks.org/print-geeksforgeeks-empty-main-c/)

本文由**德万舒·阿加瓦尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。