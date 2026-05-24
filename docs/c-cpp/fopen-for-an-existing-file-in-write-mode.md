# 写模式下现有文件的 fopen()

> 原文:[https://www . geesforgeks . org/fopen-for-a-existing-file-in-write-mode/](https://www.geeksforgeeks.org/fopen-for-an-existing-file-in-write-mode/)

在 C 语言中， [fopen()](http://www.cplusplus.com/reference/cstdio/fopen/) 用于以不同模式打开文件。要以写模式打开文件，需要指定“w”。当指定模式“w”时，它会为输出操作创建一个空文件。

**如果文件已经存在怎么办？**
如果同名文件已经存在，其内容将被丢弃，该文件将被视为新的空文件。例如，在下面的程序中，如果“test.txt”已经存在，它的内容将被删除，并且“GeeksforGeeks”将被写入其中。

```cpp
#include <stdio.h>
#include <stdlib.h>

int main()
{
    FILE *fp = fopen("test.txt", "w");
    if (fp == NULL)
    {
        puts("Couldn't open file");
        exit(0);
    }
    else
    {
        fputs("GeeksforGeeks", fp);
        puts("Done");
        fclose(fp);
    }
    return 0;
}
```

上述行为可能会导致意想不到的结果。如果程序员的意图是创建一个新文件，并且同名文件已经存在，那么现有文件的内容将被覆盖。

最新的 C 标准 [C11](http://en.wikipedia.org/wiki/C11_(C_standard_revision)) 提供了一个新的模式“x”，这是一个专属的创建和打开模式。模式“x”可以与任何“w”说明符一起使用，如“wx”、“wbx”。**当 x 与 w 一起使用时，如果文件已经存在或无法打开，fopen()将返回 NULL。**以下是修改后的 C11 程序，不会覆盖现有文件。

```cpp
#include <stdio.h>
#include <stdlib.h>

int main()
{
    FILE *fp = fopen("test.txt", "wx");
    if (fp == NULL)
    {
        puts("Couldn't open file or file already exists");
        exit(0);
    }
    else
    {
        fputs("GeeksforGeeks", fp);
        puts("Done");
        fclose(fp);
    }
    return 0;
}
```

**参考资料:**
[不要对 fopen()和文件创建](https://www.securecoding.cert.org/confluence/display/seccode/FIO03-C.+Do+not+make+assumptions+about+fopen%28%29+and+file+creation)
[做假设 http://en . Wikipedia . org/wiki/C11 _(C _ standard _ revision)](http://en.wikipedia.org/wiki/C11_(C_standard_revision))
[http://www.cplusplus.com/reference/cstdio/freopen/](http://www.cplusplus.com/reference/cstdio/freopen/)

本文由 **Abhay Rathi** 整理。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论