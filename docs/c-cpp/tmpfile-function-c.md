# tmpfile()函数在 C

中

> 原文:[https://www.geeksforgeeks.org/tmpfile-function-c/](https://www.geeksforgeeks.org/tmpfile-function-c/)

在 [C 编程语言](https://www.geeksforgeeks.org/c/)中，tmpfile()函数用于生成/创建临时文件。

*   The tmpfile () function is defined in the "stdio.h" header file.
*   After the program is terminated, the temporary files created will be automatically deleted.
*   Open files in binary update mode, that is, wb+ mode.
*   The syntax of tmp file () function is:

    ```cpp
    FILE *tmpfile(void) 
    ```

*   The tmp file () function always returns a pointer to the temporary file after creating the file. If the temporary file cannot be created by chance, the tmpfile () function returns a null pointer.

```cpp
// C program to demonstrate working of tmpfile()
#include <stdio.h>
int main()
{
    char str[] = "Hello GeeksforGeeks";
    int i = 0;

    FILE* tmp = tmpfile();
    if (tmp == NULL)
    {
        puts("Unable to create temp file");
        return 0;
    }

    puts("Temporary file is created\n");
    while (str[i] != '\0')
    {
        fputc(str[i], tmp);
        i++ ;
    }

    // rewind() function sets the file pointer
    // at the beginning of the stream.
    rewind(tmp);

    while (!feof(tmp))
        putchar(fgetc(tmp));
}
```

输出:

```cpp
Temporary file is created
Hello GeeksforGeeks

```

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。