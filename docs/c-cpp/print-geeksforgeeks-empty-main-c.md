# 如何在 C、C++ 和 Java 中用空 main()打印“GeeksforGeeks”？

> 原文:[https://www . geesforgeks . org/print-geesforgeks-empty-main-c/](https://www.geeksforgeeks.org/print-geeksforgeeks-empty-main-c/)

写一个程序，用空 main()函数打印“**geeks forgeeks”**。你不能用 main()写任何东西。

**C 语言**

1.  One way of doing this is to apply GCC constructor attribute to a function so that it executes before main() (See [this](https://www.geeksforgeeks.org/functions-that-are-executed-before-and-after-main-in-c/) for details).

    ```cpp
    #include <stdio.h>

    /* Apply the constructor attribute to myStartupFun() 
       so that it is executed before main() */
    void myStartupFun(void) __attribute__((constructor));

    /* implementation of myStartupFun */
    void myStartupFun(void)
    {
        printf("GeeksforGeeks");
    }

    int main()
    {
    }
    ```

    输出:

    ```cpp
    GeeksforGeeks
    ```

2.  In linux, just override the default definition of **_start()** function so that it would work as a custom startup code. See [this](https://www.geeksforgeeks.org/executing-main-in-c-behind-the-scene/) article to understand more.

    ```cpp
    #include <stdio.h>
    #include <stdlib.h>

    int main(void)
    {
    }

    // _start() function
    void _start(void)
    {
        printf("GeeeksforGeeks");

        // Call main() function
        int var = main();
        exit(var);
    }
    ```

    现在通过以下命令编译它

    ```cpp
    gcc -nostartfiles -o file file.c
    ```

    输出:

    ```cpp
    GeeksforGeeks
    ```

**C++ 语言**

1.  The idea is to create a **class**, have a cout statement in constructor and create a global object of the class. When the object is created, constructor is called and “GeeksforGeeks” is printed.

    ```cpp
    #include <iostream>

    class MyClass {
    public:
        MyClass()
        {
            std::cout << "GeeksforGeeks";
        }
    } m;

    int main()
    {
    }
    ```

    输出:

    ```cpp
    GeeksforGeeks
    ```

2.  The idea is to create **struct** and use the same logic which is discussed in above. The reason is that **struct** and **class** in C++ are exactly the same data structure except **struct** default to public visibility while **class** defaults to private visibility

    ```cpp
    #include <iostream>

    struct Mystruct {

        Mystruct()
        {
            std::cout << "GeeksforGeeks";
        }
    } obj;

    int main() {}
    ```

    输出:

    ```cpp
    GeeksforGeeks
    ```

3.  By using global variable, idea is to initialise **printf()** function to global variable, but it will work only in C++ language as in C language we can’t initialise variable or expression like this to global variable.

    ```cpp
    #include <cstdio>

    int var = printf("GeeksforGeeks");

    int main()
    {
    }
    ```

    输出:

    ```cpp
    GeeksforGeeks
    ```

**Java 语言**

其思想是使用静态块进行打印，实际上 java 中 main()方法之外声明的任何静态块都是在 main 方法之前执行的。

```cpp
class Myjava {
    static
    {
        System.out.println("GeeksforGeeks");
    }
    public static void main(String args[])
    {
    }
}
```

输出:

```cpp
GeeksforGeeks
```

本文由**维基**供稿，[舒巴姆·班萨尔](https://www.quora.com/profile/Shubham-Bansal-209)改进。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。