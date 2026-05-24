# 不使用任何头文件用 C/C++ 打印“Hello World”

> 原文:[https://www . geesforgeks . org/print-hello-world-c-不使用头文件/](https://www.geeksforgeeks.org/print-hello-world-c-without-using-header-file/)

写一个 C/C++ 程序，打印 **Hello World** 不包含任何头文件。

*从概念上来说，不使用“stdio.h”头文件，编写一个打印 **Hello World** 的 C/C++ 程序似乎是不切实际的。因为 printf()函数的声明包含在“stdio.h”头文件中。*

但是我们可以通过利用 C 预处理器指令来轻松实现这一点。事实上，在编译程序时，C 预处理的第一阶段将所有头文件扩展成一个文件，之后编译器自己编译扩展的文件。因此我们只需要从头文件中提取 printf()函数的声明，并在我们的主程序中像这样使用:-

*   **C language:** Just declare the printf () function from the "stdio.h" header file.

    ```cpp
    //Declare the printf() function
    int printf(const char *format, ...);

    int main()
    {
      printf( "Hello World" );
      return 0;
    }
    ```

    ```cpp
    Output: Hello World
    ```

*   **C++ language:** Because of the misuse of the name **in C++ with** , we can't put the declaration of printf () function directly as in the above example. See [this](https://www.geeksforgeeks.org/extern-c-in-c/) for details to learn more about name theft. Therefore, we only need to declare printf ():-

    ```cpp
    //Declare the printf() function inside
    //extern "C" for C++ compiler
    extern "C"
    {
    int printf(const char *format, ...);
    }

    int main()
    {
      printf( "Hello World" );
      return 0;
    }
    ```

    ```cpp
    Output: Hello World
    ```

    in the extern keyword like this

详见[本](https://www.geeksforgeeks.org/compiling-a-c-program-behind-the-scenes/)了解 C 程序编译的各个阶段。

本博客由 [Shubham Bansal](https://www.facebook.com/banalshubham) 投稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。