# C 程序比较两个文件并报告不匹配

> 原文：[https://www.geeksforgeeks.org/c-program-compare-two-files-report-mismatch/](https://www.geeksforgeeks.org/c-program-compare-two-files-report-mismatch/)

我们得到了几乎两份相同的文件。但是有些字符被破坏了。我们需要找到这些损坏的字符所在的行号及其位置，以及损坏（错误）字符的总数。

## 示例

输入：
`file1.txt` 包含
```
it is
fun
```
`file2.txt` 包含
```
it is
run
```

输出：
```
Line Number : 2         Error Position : 1
Total Errors : 1
```

## 步骤

1.  在只读模式下使用文件指针打开两个文件。
2.  逐个获取两个字符变量中的文件数据，直到文件结束。
3.  如果变量遇到换行符，则增加行号并将位置重置为零。
4.  如果变量不相等，则增加错误计数，打印错误行和错误位置。

## 代码实现

```cpp
// C program to compare two files and report
// mismatches by displaying line number and
// position of line.
#include<stdio.h>
#include<string.h>
#include<stdlib.h>

void compareFiles(FILE *fp1, FILE *fp2)
{
    // fetching character of two file
    // in two variable ch1 and ch2
    char ch1 = getc(fp1);
    char ch2 = getc(fp2);

    // error keeps track of number of errors
    // pos keeps track of position of errors
    // line keeps track of error line
    int error = 0, pos = 0, line = 1;

    // iterate loop till end of file
    while (ch1 != EOF && ch2 != EOF)
    {
        pos++ ;

        // if both variable encounters new
        // line then line variable is incremented
        // and pos variable is set to 0
        if (ch1 == '\n' && ch2 == '\n')
        {
            line++ ;
            pos = 0;
        }

        // if fetched data is not equal then
        // error is incremented
        if (ch1 != ch2)
        {
            error++ ;
            printf("Line Number : %d \tError"
               " Position : %d \n", line, pos);
        }

        // fetching character until end of file
        ch1 = getc(fp1);
        ch2 = getc(fp2);
    }

    printf("Total Errors : %d\t", error);
}

// Driver code
int main()
{
    // opening both file in read only mode
    FILE *fp1 = fopen("file1.txt", "r");
    FILE *fp2 = fopen("file2.txt", "r");

    if (fp1 == NULL || fp2 == NULL)
    {
       printf("Error : Files not open");
       exit(0);
    }

    compareFiles(fp1, fp2);

    // closing both file
    fclose(fp1);
    fclose(fp2);
    return 0;
}
```

## 输出

```
Line Number : 2         Error Position : 1
Total Errors : 1
```

## 投稿与反馈

本文由[阿迪蒂亚·库马尔](https://www.linkedin.com/in/aditya-kumar-837315100/)供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。