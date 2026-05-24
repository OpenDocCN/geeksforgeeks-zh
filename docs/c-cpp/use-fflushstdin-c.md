# 在 C

中使用 fflush(stdin)

> [https://www.geeksforgeeks.org/use-fflushstdin-c/](https://www.geeksforgeeks.org/use-fflushstdin-c/)

fflush()通常仅用于输出流。其目的是清除(或刷新)输出缓冲区，并将缓冲的数据移动到控制台(如果是 stdout)或磁盘(如果是文件输出流)。下面是它的语法。

```cpp
fflush(FILE *ostream);

ostream points to an output stream 
or an update stream in which the 
most recent operation was not input, 
the fflush function causes any 
unwritten data for that stream to 
be delivered to the host environment 
to be written to the file; otherwise, 
the behavior is undefined.
```

**我们可以像 stdin 一样用于输入流吗？**
按照 C 标准，使用 fflush(stdin)是未定义的行为。然而一些编译器，像微软的 visual studio 允许它。它在这些编译器中是如何使用的？在获取带有空格的输入字符串时，缓冲区不会为下一个输入清除，而是考虑前一个输入。要解决这个问题，fflush(stdin)是。用于清除流/缓冲区。

## C

```cpp
// C program to illustrate situation
// where flush(stdin) is required only
// in certain compilers.
#include <stdio.h>
#include<stdlib.h>
int main()
{
    char str[20];
    int i;
    for (i=0; i<2; i++)
    {
        scanf("%[^\n]s", str);
        printf("%s\n", str);
        // fflush(stdin);
    }
    return 0;
}
```

**输入:**

```cpp
geeks   
geeksforgeeks
```

**输出:**

```cpp
geeks 
geeks 
```

上面的代码只接受一个输入，对于第二个输入给出相同的结果。原因是因为字符串已经存储在缓冲区中，即流还没有被清除，因为它需要有空格或新行的字符串。因此，为了处理这种情况，使用了 fflush(stdin)。

## C

```cpp
// C program to illustrate flush(stdin)
// This program works as expected only
// in certain compilers like Microsoft
// visual studio.
#include <stdio.h>
#include<stdlib.h>
int main()
{
    char str[20];
    int i;
    for (i = 0; i<2; i++)
    {
        scanf("%[^\n]s", str);
        printf("%s\n", str);

        // used to clear the buffer
        // and accept the next string
        fflush(stdin);
    }
    return 0;
}
```

**输入:**

```cpp
geeks
geeksforgeeks
```

**输出:**

```cpp
geeks 
geeksforgeeks
```

**用 fflush(stdin)好不好？**

虽然在“scanf()”语句后使用“fflush(stdin)”也会清除某些编译器中的输入缓冲区，但不建议使用它，因为根据语言标准，这是未定义的行为。在 C 和 C++ 中，我们有不同的方法来清除这个 [**帖子**](https://www.geeksforgeeks.org/clearing-the-input-buffer-in-cc/) 中讨论的缓冲区。

**参考:**
[https://stackoverflow . com/questions/2979209/using-fflushtdin](https://stackoverflow.com/questions/2979209/using-fflushstdin)

本文由 [**萨哈布拉**](https://www.facebook.com/sahil.chhabra.965) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。