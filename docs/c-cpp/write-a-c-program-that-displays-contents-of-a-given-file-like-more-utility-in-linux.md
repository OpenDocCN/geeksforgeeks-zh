# 编写一个 C 程序，显示给定文件的内容，就像 Linux 中的‘more’实用程序一样

> 原文:[https://www . geesforgeks . org/write-a-c-program-显示给定文件的内容-类似于 linux 中的更多实用程序/](https://www.geeksforgeeks.org/write-a-c-program-that-displays-contents-of-a-given-file-like-more-utility-in-linux/)

编写一个 C 程序，逐页显示给定行的内容。给定一次显示为“n”的行数和文件名，程序应该首先显示 n 行，然后等待用户按键后再显示下 n 行，以此类推。

**强烈建议尽量减少浏览器，先自己试试这个。**

我们可以打开给定的文件并打印文件内容。打印时，我们可以记录换行符的数量。如果换行符的数量变成 n，我们等待用户按下一个键，然后显示下 n 行。

下面是必选的 C 程序。

```cpp
// C program to show contents of a file with breaks
#include <stdio.h>

// This function displays a given file with breaks of
// given line numbers.
void show(char *fname, int n)
{
    // Open given file
    FILE *fp = fopen(fname, "r");
    int curr_lines = 0, ch;

    // If not able to open file
    if (fp == NULL)
    {
        printf("File doesn't exist\n");
        return;
    }

    // Read contents of file
    while ((ch = fgetc(fp)) != EOF)
    {
        // print current character
        putchar(ch);

        // If current character is a new line character,
        // then increment count of current lines
        if (ch == '\n')
        {
            curr_lines++ ;

            // If count of current lines reaches limit, then
            // wait for user to enter a key
            if (curr_lines == n)
            {
                curr_lines = 0;
                getchar();
            }
        }
    }

    fclose(fp);
}

// Driver program to test above function
int main()
{
    char fname[] = "A.CPP";
    int n = 25;
    show(fname, n);
    return 0;
}
```

本文由 **Ajay Jain** 供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。