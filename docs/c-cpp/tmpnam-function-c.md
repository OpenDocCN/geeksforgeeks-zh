# tmpnam()函数在 C

中

> 原文:[https://www.geeksforgeeks.org/tmpnam-function-c/](https://www.geeksforgeeks.org/tmpnam-function-c/)

tmpnam()函数是一个特殊的函数，在“stdio.h”头文件中声明。每次至少调用一次 TMP_MAX 名称时，它都会生成一个不同的临时文件名。这里 TMP_MAX 表示 tmpnam()函数可以产生的不同文件名的最大数量。如果它被调用的次数超过了 TMP_MAX，则该行为依赖于实现。这里，L_tmpnam 定义了一个字符数组保存 tmpnam 结果所需的大小。

**语法:**

```cpp
char *tmpnam(char *str)
s : The character array to copy the file name.
It generates and returns a valid temporary 
filename which does not exist. 
If str is null then it simply returns the tmp file name.
```

```cpp
// C program to generate random temporary file names.
#include <stdio.h>
int main(void)
{
    // L_tmpnam declared in the stdio.h file.
    // L_tmpnam define length of the generated file name.
    char generate[L_tmpnam + 1]; // Add +1 for the null character.
    tmpnam(generate);
    puts(generate);
    return 0;
}
```

输出:

```cpp
The file names are dependent on running machine, which can be anything.
Example: /tmp/fileRTOA0m
         \s260.
         \s3ok.
         \s5gg. etc

```

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。