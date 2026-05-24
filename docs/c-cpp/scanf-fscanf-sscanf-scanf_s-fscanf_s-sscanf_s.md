# 用户输入的内置库函数| scanf，fscanf，sscanf，scanf_s，fscanf_s，sscanf_s

> 原文:[https://www . geesforgeks . org/scanf-fscanf-ss canf-scanf _ s-fscanf _ s-ss canf _ s/](https://www.geeksforgeeks.org/scanf-fscanf-sscanf-scanf_s-fscanf_s-sscanf_s/)

1.  **scanf() :** The C library function int scanf (const char *format, …) reads formatted input from stdin.

    ```cpp
    Syntax:
    int scanf(const char *format, ...)

    Return type: Integer

    Parameters:
    format: string that contains the type specifier(s) 
    "..." (ellipsis): indicates that the function accepts
    a variable number of arguments
    ```

    每个参数必须是一个内存地址，转换后的结果将被写入其中。成功后，函数返回填充的变量数。在输入失败的情况下，在能够成功读取任何数据之前，返回 e of。
    可用于扫描的类型说明符:

    ```cpp
    %c — Character
    %d — Signed integer
    %f — Floating point
    %s — String
    ```

    ```cpp
    //C program t illustrate scanf statement
    #include <stdio.h>
    #include <stdlib.h>

    int main()
    {
        char a[10]; 
        printf("Please enter your name : \n"); 

        //scanf statement
        scanf("%s", a);

        printf("You entered: \n%s", a);

       return 0;
    }
    ```

    **输入:**

    ```cpp
    Geek
    ```

    **输出:**

    ```cpp
    Please enter your name : 
    You entered: 
    Geek
    ```

2.  **sscanf():** sscanf() is used to read formatted input from the string.

    ```cpp
    Syntax:
    int sscanf ( const char * s, const char * format, ...);

    Return type: Integer

    Parameters:
    s: string used to retrieve data
    format: string that contains the type specifier(s)
    … : arguments contains pointers to allocate 
    storage with appropriate type. 

    There should be at least as many of these arguments as the 
    number of values stored by the format specifiers.
    ```

    成功后，函数返回填充的变量数。在输入失败的情况下，在能够成功读取任何数据之前，返回 e of。

    ```cpp
    // C program to illustrate sscanf statement
    #include <stdio.h>

    int main ()
    {
        // declaring array s
        char s [] = "3 red balls 2 blue balls"; 
        char str [10],str2 [10];
        int i;

        // %*s is used to skip a word
        sscanf (s,"%d %*s %*s %*s %s %s", &i, str, str2);

        printf ("%d %s %s \n", i, str, str2);

        return 0;
    }
    ```

    **输出:**

    ```cpp
    3 blue balls
    ```

3.  **fscanf()**: fscanf() reads formatted data from file and stores it into variables.

    ```cpp
    Syntax:
    int fscanf(FILE *stream, const char *format, ...)

    Parameters:
    Stream:  pointer to the File object that identifies the stream.
    format : is a string that contains the type specifier(s)

    ```

    成功后，函数返回填充的变量数。在输入失败的情况下，在能够成功读取任何数据之前，返回 e of。

    ```cpp
    // C program to illustrate sscanf statement
    // This program will run on system having the file file.txt
    #include <stdio.h>
    #include <stdlib.h>

    int main()
    {
        char s1[10], s2[10], s3[10];
        int year;

        // file pointer
        FILE * fp; 

        // opening/creation of file
        fp = fopen ("file.txt", "w+");     

        // storing string in the file
        fputs("Hello World its 2017", fp); 

        // sets the file position to the beginning of the file
        rewind(fp); 

        // taking input from file
        fscanf(fp, "%s %s %s %d", s1, s2, s3, &year); 

        printf("String1 |%s|\n", s1 );
        printf("String2 |%s|\n", s2 );
        printf("String3 |%s|\n", s3 );
        printf("Integer |%d|\n", year );

        // close file pointer
        fclose(fp);     

        return(0);
    }
    ```

    输出:

    ```cpp
    String1 |Hello|
    String2 |World|
    String3 |its|
    Integer |2017|

    ```

4.  **scanf_s() :** This function is specific to Microsoft compilers. It is the same as scanf, except it does not cause buffer overload.

    ```cpp
    Syntax:
    int scanf_s(const char *format [argument]...);

    argument(parameter): here you can specify the buffer size and actually control the limit
    of the input so you don't crash the whole application.
    ```

    成功后，函数返回填充的变量数。在输入失败的情况下，在能够成功读取任何数据之前，返回 e of。
    **为什么要用 scanf_s()？**
    scanf 只读取控制台提供的任何输入。c 不会检查用户输入是否适合您指定的变量。
    如果你有一个名为 color[3]的数组，并且你使用 scanf 表示“红色”，它会正常工作，但是如果用户输入超过 3 个字符，scanf 会开始写入不属于 color 的内存。c 不会捕捉到这一点或警告你，它可能会也可能不会使程序崩溃，这取决于是否有东西试图访问和写入不属于 color 的内存插槽。这就是 scanf_s 发挥作用的地方。scanf_s 检查用户输入是否适合给定的内存空间。

    ```cpp
    // C program to illustrate sscanf_s statement
    // scanf_s() will only work in Microsoft Visual Studio.
    #include <stdio.h>
    #include <stdlib.h>

    int main()
    {
        char a[5];

        // sizeof(a) is buffer size
        scanf_s("%s", a, sizeof(a)); 

            printf("\n%s ", a);

        return 0;
    }
    ```

    **输入:**

    ```cpp
    Red
    ```

    **输出:**

    ```cpp
    Red
    ```

    **输入:**

    ```cpp
    Yellow
    ```

    **输出:**

    ```cpp
    No Output
    ```

    **说明缓冲区大小和数组大小之间的关系。**

    ## C

    ```cpp
    // C program
    // consumes the Enter key 
    // (newline character) pressed after input
    #include<stdio.h>

    char ch[100000];
    printf("Enter characters: ");
    scanf_s("%s", ch, 99999);
    getchar();
    ```

    ## C++

    ```cpp
    // C++ program
    // consumes the Enter key 
    // (newline character) pressed after input

    #include "stdafx.h"

    int _tmain(int argc, _TCHAR* argv[])
    {
        // example
        char ch[100000];
        printf("Enter characters: ");
        scanf_s("%s", ch, 99999);
        getchar();
        return 0;
    }
    ```

    1.  如果缓冲区大小等于或小于数组的大小，那么输入大于或等于缓冲区大小将不起作用。
    2.  如果缓冲区的大小大于数组的大小，那么
        1.  inputting smaller than buffer size will work out but will give an error

            "运行时检查失败# 2–变量“变量名”周围的堆栈已损坏."

        2.  输入大于缓冲区大小的数据不会有任何作用，并且会产生同样的错误。

*   **fscanf_s() :** Difference between fscanf() and fscanf_s() is same as that of scanf() and scanf_s(). fscanf_s() is secure function and secure functions require the size of each c, C, s, S and [ type field to be passed as an argument immediately following the variable.

    ```cpp
    Syntax:
    int fscanf_s(   FILE *stream,  const char *format ,[argument ]... ); 

    fscanf_s has an extra argument(parameter) where you can 
    specify the buffer size and actually control the limit of the input.

    ```

    成功后，函数返回填充的变量数。在输入失败的情况下，在能够成功读取任何数据之前，返回 e of。

    ```cpp
    //C program to illustrate fscanf_s statement
    //This program will run on MS Visual studio
    #include <stdio.h>
    #include <stdlib.h>

    int main()
    {
        char s1[10], s2[10], s3[10];
        int year;

        // file pointer
        FILE * fp; 

        // Open file securely
        fopen_s(&fp,"file.txt", "w+"); 

        fputs("Hello World its 2017", fp); 

        rewind(fp);

        // Using fscanf_s
        fscanf_s(fp, "%s", s1, sizeof(s1));
        fscanf_s(fp, "%s", s2, sizeof(s2));
        fscanf_s(fp, "%s", s3, sizeof(s3));
        fscanf_s(fp, "%d", &year, sizeof(year));

        printf("String1 |%s|\n", s1);
        printf("String2 |%s|\n", s2);
        printf("String3 |%s|\n", s3);
        printf("Integer |%d|\n", year);

        fclose(fp);

        return(0);
    }
    ```

    **输出:**

    ```cpp
    String1 |Hello|
    String2 |World|
    String3 |its|
    Integer |2017|

    ```

    *   **sscanf_s() :** sscanf_s() is secure function of sscanf() and secure functions require the size of each c, C, s, S and [ type field to be passed as an argument immediately following the variable.

    ```cpp
    Syntax:
    int sscanf_s(const char *restrict buffer, const char *restrict format, ...);

    sscanf_s has an extra argument(parameter) where you can specify 
    the buffer size and actually control the limit of the input.

    ```

    成功后，函数返回填充的变量数。在输入失败的情况下，在能够成功读取任何数据之前，返回 e of。

    ```cpp
    //C program to illustrate sscanf_s statement
    //This program will run on MS Visual studio
    #include <stdio.h>

    int main()
    {
        char s[] = "3 red balls 2 blue balls";
        char str[10], str2[10];
        int i;

        // %*s is used to skip a word
        sscanf_s(s, "%d", &i, sizeof(i));
        sscanf_s(s, "%*d %*s %*s %*s %s", str, sizeof(str));
        sscanf_s(s, "%*d %*s %*s %*s %*s %s", str2, sizeof(str2));

        printf("%d %s %s \n", i, str, str2);

        return 0;
    }
    ```

    **输出:**

    ```cpp
    3 blue balls 

    ```

    **注意:** sscanf_s()只会在 Microsoft Visual Studio 中工作。

本文由 **Kartik Ahuja** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。