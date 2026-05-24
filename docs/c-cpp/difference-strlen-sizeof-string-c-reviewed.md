# C 中字符串的 strlen()和 sizeof()之间的差异

> 原文:[https://www . geesforgeks . org/difference-strlen-sizeof-string-c-reviewed/](https://www.geeksforgeeks.org/difference-strlen-sizeof-string-c-reviewed/)

**[【sizeof()](https://www.geeksforgeeks.org/sizeof-operator-c/)**

Sizeof 运算符是一个编译时一元运算符，可用于计算其操作数的大小。

*   sizeof 的结果是无符号整数类型，通常用 size_t 表示。
*   sizeof 可以应用于任何数据类型，包括整型和浮点型等基元类型、指针类型，或者 Structure、union 等复合数据类型。

**strlen()**

strlen()是 C 语言中的一个预定义函数，其定义包含在头文件“string.h”中。

*   strlen()接受一个指向数组的指针作为参数，并在运行时从我们给它的地址遍历内存，寻找一个 **NULL** 字符，并在找到一个之前计算它经过了多少个内存位置。
*   The main task of strlen() is to count the length of an array or string.

    **sizeof vs strlen()**

    1.  **类型:** Sizeof 运算符是一元运算符，而 strlen()是 C 语言中的预定义函数
    2.  **支持的数据类型:** Sizeof 以字节(包括空值)给出任何类型数据(分配的)的实际大小，而获取字符/字符串数组的长度。
    3.  **求值大小:** sizeof()是一个编译时表达式，它给出了一个类型或变量的类型的大小。它不关心变量的值。
        另一方面，Strlen 给你一个 C 风格的空终止字符串的长度。
    4.  **小结:**两者几乎是不同的概念，用途也不同。
    5.  **在 C++ 的上下文中:**在 C++ 中，你不需要它们中的任何一个。
        C 风格字符串中的 **strlen()** 可以替换为 **C++ std::strings** 。C 中的
        **sizeof()是作为 malloc()、memcpy()或 memset()等函数的参数，可以用 **C++(使用 new、std::copy()、std::fill()或构造函数)**代替。**

    ```cpp
    // C program to demonstrate difference 
    // between strlen() and sizeof()
    #include<stdio.h>
    #include<string.h>

    int main()
    {
        char str[] = "November";
        printf("Length of String is %lu\n", strlen(str));
        printf("Size of String is %lu\n", sizeof(str));
    }
    ```

    输出:

    ```cpp
    Length of String is 8
    Size of String is 9

    ```

    因为 C 中字符的大小是 1 字节，但是我们发现 strlen()给出的值比 size of()少一个。

    **解释:**我们知道，每个字符串都以空字符(“\0”)结束。
    **strlen()** 搜索该空字符，并计算传递的内存地址数量，因此它实际上计算了空字符之前的字符串中存在的元素数量，这里是 8。
    **sizeof()** 运算符返回为传递给它的操作数分配的实际内存量。这里的操作数是一个字符数组，包含 9 个字符，包括空字符，1 个字符的大小是 1 个字节。所以，这里的总大小是 9 字节。
    **试猜以下程序的输出:**

    ```cpp
    #include <iostream>
    #include <string.h>
    using namespace std;

    int main()
    {
            char a[] = {"Geeks for"};
            char b[] = {'G','e','e','k','s',' ','f','o','r'};
            cout << "sizeof(a) = " << sizeof(a);
            cout << "\nstrlen(a) = "<< strlen(a);
            cout<<  "\nsizeof(b) = " << sizeof(b);
            cout<<  "\nstrlen(b) = " << strlen(b);

            return 0;
    }
    ```

    strlen 函数寻找一个空字符，如果找不到，就会表现异常。
    输出:

    ```cpp
    sizeof(a) = 10
    strlen(a) = 9
    sizeof(b) = 9
    strlen(b) = 11

    ```

    本文由[阿迪蒂亚·库马尔](https://www.linkedin.com/in/aditya-kumar-837315100/)供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。