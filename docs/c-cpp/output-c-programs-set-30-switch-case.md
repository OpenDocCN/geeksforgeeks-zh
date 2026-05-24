# C 程序输出|设置 30(切换情况)

> 原文:[https://www . geesforgeks . org/output-c-programs-set-30-switch-case/](https://www.geeksforgeeks.org/output-c-programs-set-30-switch-case/)

先决条件–[C/c++ ](https://www.geeksforgeeks.org/switch-statement-cc/)中的开关情况

 **C/c++ 中 Switch 语句的有趣问题**

1.  **Program 1**

    ```cpp
    #include <stdio.h>
    int main()
    {
        int num = 2;
        switch (num + 2)
        {
        case 1:
            printf("Case 1: ");
        case 2:
            printf("Case 2: ");
        case 3:
            printf("Case 3: ");
        default:
            printf("Default: ");
        }
        return 0;
    }
    ```

    输出:

    ```cpp
    Default: 
    ```

    **说明:**在 switch 中，表达式“num+2”，其中 num 值为 2，相加后表达式结果为 4。因为没有用值 4 定义的案例，所以执行了默认案例。

2.  **程序 2**

    ```cpp
    #include<stdio.h>
    void main()
    {
        int movie = 1;
        switch (movie << (2 + movie))
        {
        default:
            printf(" Traffic");
        case 4:
            printf(" Sultan");
        case 5:
            printf(" Dangal");
        case 8:
            printf(" Bahubali");
        }
    }
    ```

    输出:

    ```cpp
    Bahubali
    ```

    **说明:**我们可以写任何顺序的 case 语句，包括默认的 case。在 switch case 语句中，默认案例可以是第一个案例、最后一个案例或介于两者之间的任何案例。表情“电影< < (2 +电影)”的值是 8。

3.  **Program 3**

    ```cpp
    #include<stdio.h>
    #define L 10
    void main()
    {
        auto a = 10;
        switch (a, a*2)
        {
        case L:
            printf("ABC");
            break;

        case L*2:
            printf("XYZ");
            break;

        case L*3:
            printf("PQR");
            break;

        default:
            printf("MNO");

        case L*4:
            printf("www");
            break;
        }
    }
    ```

    输出:

    ```cpp
    XYZ
    ```

    **说明:**在 C 中，逗号也是优先级最低的运算符。所以如果
    x = (a，b)；
    那么 x = b
    注意:Case 表达式可以是宏常量。

4.  **Program 4**

    ```cpp
    #include<stdio.h>
    void main()
    {
        switch(2)
        {
        case 1L:
            printf("No");

        case 2L:
            printf("%s","GEEKS");
            goto Love;

        case 3L:
            printf("Please");

        case 4L:Love:
            printf("FOR");
        }
    }
    ```

    输出:

    ```cpp
    GEEKSFOR
    ```

    **说明:**switch case 语句的情况下可以写 goto 语句的标签。

本文由 Somesh Awasthi 先生供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。