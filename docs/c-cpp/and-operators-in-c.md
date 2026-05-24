# #和# #中的操作员

> 原文:[https://www.geeksforgeeks.org/and-operators-in-c/](https://www.geeksforgeeks.org/and-operators-in-c/)

**字符串化运算符(#)**

此运算符导致相应的实际参数用双引号括起来。#运算符通常被称为*字符串*运算符，它将它前面的参数转换为带引号的字符串。有关预处理器指令的更多信息，请参考[本](https://www.geeksforgeeks.org/cc-preprocessors/)
T5】示例:

1.  The following preprocessor turns the line printf(mkstr(geeksforgeeks)); into printf(“geeksforgeeks”);

    ```cpp
    // CPP program to illustrate (#) operator
    #include <stdio.h>
    #define mkstr(s) #s
    int main(void)
    {
        printf(mkstr(geeksforgeeks));
        return 0;
    }
    ```

    输出:

    ```cpp
    geeksforgeeks

    ```

2.  In this program, value of a is replaced by macro.

    ```cpp
    // CPP program to illustrate (#) operator
    #include <iostream>
    using namespace std;

    #define a 8.3297

    int main()
    {
        cout << "Value of a is " << a << endl;

        return 0;
    }
    ```

    输出:

    ```cpp
    Value of a is 8.3297

    ```

3.  This program finds out maximum out of two numbers using macro

    ```cpp
    // CPP program to illustrate (#) operator
    #include <iostream>
    using namespace std;

    #define MAX(i, j) (((i) > (j)) ? i : j)

    int main()
    {
        int a, b;

        a = 250;
        b = 25;

        cout << "The maximum is " << MAX(a, b) << endl;

        return 0;
    }
    ```

    输出:

    ```cpp
    The maximum is 250

    ```

**令牌粘贴操作符(##)**

允许用作实际参数的标记连接起来形成其他标记。扩展宏时，将两个标记合并成一个标记通常很有用。这称为标记粘贴或标记连接。“##”预处理运算符执行标记粘贴。扩展宏时，每个“##”运算符两侧的两个标记组合成一个标记，然后替换宏扩展中的“##”和两个原始标记。
**例:**

1.  The preprocessor transforms printf(“%d”, concat(x, y)); into printf(“%d”, xy);

    ```cpp
    // CPP program to illustrate (##) operator
    #include <stdio.h>
    #define concat(a, b) a##b
    int main(void)
    {
        int xy = 30;
        printf("%d", concat(x, y));
        return 0;
    }
    ```

    输出:

    ```cpp
    30

    ```

**应用:**在宏扩展期间，##提供了一种连接实际参数的方法。如果替换文本中的参数与##相邻，则该参数将被实际参数替换，并删除##和周围的空白，然后重新扫描结果。

本文由**Shivani ghishial**供稿。如果你喜欢极客博客并想投稿，你也可以用 contribute.geeksforgeeks.org 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。