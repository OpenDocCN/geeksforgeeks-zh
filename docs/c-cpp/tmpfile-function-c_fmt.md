# tmpfile()函数在C中

## 参考来源
> 原文: [https://www.geeksforgeeks.org/tmpfile-function-c/](https://www.geeksforgeeks.org/tmpfile-function-c/)

## 简介
在 [C 编程语言](https://www.geeksforgeeks.org/c/)中，`tmpfile()`函数用于生成/创建临时文件。

*   `tmpfile()`函数在`stdio.h`头文件中定义。
*   程序终止后，创建的临时文件将被自动删除。
*   以二进制更新模式打开文件，即`wb+`模式。
*   `tmpfile()`函数的语法是：

```cpp
FILE *tmpfile(void) 
```

*   `tmpfile()`函数在创建文件后总是返回一个指向临时文件的指针。如果临时文件无法创建，`tmpfile()`函数返回一个空指针。

## 示例代码
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

## 输出
```
Temporary file is created
Hello GeeksforGeeks
```

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。