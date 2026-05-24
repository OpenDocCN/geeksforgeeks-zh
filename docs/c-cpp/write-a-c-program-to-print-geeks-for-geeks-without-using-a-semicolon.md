# 写一个 C 程序，不用分号

打印“极客为极客”

> 原文:[https://www . geesforgeks . org/write-a-c-program-to-print-geeks-for-geeks-不使用分号/](https://www.geeksforgeeks.org/write-a-c-program-to-print-geeks-for-geeks-without-using-a-semicolon/)

首先我们要了解 printf()函数是如何工作的。
printf()函数的原型是:

```cpp
int printf( const char *format , ...)

```

**参数**

*   **格式:**这是一个包含要写入 stdout 的文本的字符串。
*   **附加参数:**……(三个点称为省略号)，根据格式字符串指示可变的参数数量。

**printf()返回写入 stdout 的字符总数。因此，它可以用作 if 条件、while 条件、开关大小写和宏中的条件检查。**

让我们逐一看看这些条件。

1.  **使用 if 条件:**T0】
2.  **使用同时条件:**

    ```cpp
    #include<stdio.h>
    int main(){
        while (!printf( "Geeks for Geeks" ))
        {   }
    }
    ```

3.  **使用开关情况:**

    ```cpp
    #include<stdio.h>
    int main(){
        switch (printf("Geeks for Geeks" ))
        {   }
    }
    ```

4.  **使用宏:**

    ```cpp
    #include<stdio.h>
    #define PRINT printf("Geeks for Geeks")
    int main()
    {
        if (PRINT)
        {    }
    }
    ```

```cpp
Output: Geeks for Geeks

```

**上述问题的一个微不足道的扩展:**写一个 C 程序打印“；”不使用分号

```cpp
#include<stdio.h>
int main()
{   
   // ASCII value of ; is 59
   if (printf("%c", 59))
   {
   }
}
```

```cpp
Output: ;

```

本博客由 [Shubham Bansal](https://www.facebook.com/banalshubham) 投稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。