# 实现自己的尾部(读取一个巨大文件的最后 n 行)

> 原文:[https://www . geesforgeks . org/implement-your-your-tail-read-last-n-line-of-a-great-file/](https://www.geeksforgeeks.org/implement-your-own-tail-read-last-n-lines-of-a-huge-file/)

给定一个包含动态数据的巨大文件，编写一个程序在任何时候从文件中读取最后 n 行，而不读取整个文件。这个问题类似于 linux 中显示文件最后几行的 tail 命令。它主要用于查看日志文件更新，因为这些更新会附加到日志文件中。

来源:[微软访谈](https://www.geeksforgeeks.org/microsoft-interview-experience-set-90/)

**我们强烈建议你尽量减少浏览器，先自己试试这个。**

问题主要集中在以下几个方面

1.程序不应读取整个文件。
2。程序应该处理传入的动态数据，并在任何时候返回最后 n 行。
3。在读取最后 n 行之前，程序不应关闭输入流。

下面是它的 C++ 实现

```cpp
// C++ program to implement your own tail
#include <bits/stdc++.h>
using namespace std;

#define SIZE 100

// Utility function to sleep for n seconds
void sleep(unsigned int n)
{
    clock_t goal = n * 1000 + clock();
    while (goal > clock());
}

// function to read last n lines from the file
// at any point without reading the entire file
void tail(FILE* in, int n)
{
    int count = 0;  // To count '\n' characters

    // unsigned long long pos (stores upto 2^64 – 1
    // chars) assuming that long long int takes 8 
    // bytes
    unsigned long long pos;
    char str[2*SIZE];

    // Go to End of file
    if (fseek(in, 0, SEEK_END))
        perror("fseek() failed");
    else
    {
        // pos will contain no. of chars in
        // input file.
        pos = ftell(in);

        // search for '\n' characters
        while (pos)
        {
            // Move 'pos' away from end of file.
            if (!fseek(in, --pos, SEEK_SET))
            {
                if (fgetc(in) == '\n')

                    // stop reading when n newlines
                    // is found
                    if (count++ == n)
                        break;
            }
            else
                perror("fseek() failed");
        }

        // print last n lines
        printf("Printing last %d lines -\n", n);
        while (fgets(str, sizeof(str), in))
            printf("%s", str);
    }
    printf("\n\n");
}

// Creates a file and prints and calls tail() for 
// 10 different values of n (from 1 to 10)
int main()
{
    FILE* fp;
    char buffer[SIZE];
    // Open file in binary mode
    // wb+ mode for reading and writing simultaneously
    fp = fopen("input.txt", "wb+");
    if (fp == NULL)
    {
        printf("Error while opening file");
        exit(EXIT_FAILURE);
    }
    srand(time(NULL));

    // Dynamically add lines to input file
    // and call tail() each time
    for (int index = 1; index <= 10; index++)
    {
        /* generate random logs to print in input file*/
        for (int i = 0; i < SIZE - 1; i++)
            buffer[i] = rand() % 26 + 65; // A-Z
        buffer[SIZE] = '\0';

        /* code to print timestamp in logs */
        // get current calendar time
        time_t ltime = time(NULL);

        // asctime() returns a pointer to a string
        // which represents the day and time
        char* date = asctime(localtime(<ime));

        // replace the '\n' character in the date string
        // with '\0' to print on the same line.
        date[strlen(date)-1] = '\0';

        /* Note in text mode '\n' appends two characters,
        so we have opened file in binary mode */
        fprintf(fp, "\nLine #%d [%s] - %s", index,
                                    date, buffer);

        // flush the input stream before calling tail
        fflush(fp);

        // read last index lines from the file
        tail(fp, index);

        // sleep for 3 seconds
        // note difference in timestamps in logs
        sleep(3);
    }

    /* close the file before ending program */
    fclose(fp);

    return 0;
}
```

**需要注意的几点–**
1。这段代码在联机编译器上不起作用，因为它需要文件创建权限。当运行本地机器时，它产生样本输入文件“input.txt”，并向其中动态写入数据 10 次，每次调用 tail()函数。

2.我们应该避免对大型文件(以 GBs 为单位)使用 fseek()和 ftell()，因为它们对 long int 类型的文件位置进行操作。请改用 _fseeki64()、_ftelli64()。

3.无符号长整型的最大允许值为 2<sup>32</sup>–1(假设无符号长整型需要 4 个字节)。它可以用于文件大小小于 4 GB 的文件。

4.无符号长 long 的最大允许值为 2<sup>64</sup>–1(假设无符号长 long 需要 8 个字节)。它可以用于大小超过 4 GB 的文件。

本文由**阿迪蒂亚·戈尔**供稿。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论