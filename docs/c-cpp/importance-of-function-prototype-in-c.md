# 功能原型在 C 中的重要性

> 原文:[https://www . geesforgeks . org/function-prototype-in-c/](https://www.geeksforgeeks.org/importance-of-function-prototype-in-c/)

函数原型告诉编译器一些参数函数接受参数的数据类型，并返回函数的类型。通过使用这些信息，编译器用函数定义和函数调用来交叉检查函数参数及其数据类型。如果我们忽略函数原型，程序编译时可能会发出警告，并可能正常工作。但是有时候，它会给出奇怪的输出，很难找到这样的编程错误。让我们用例子来看看

## C

```cpp
#include <errno.h>
#include <stdio.h>

int main(int argc, char *argv[])
{
    FILE *fp;

    fp = fopen(argv[1], "r");
    if (fp == NULL) {
        fprintf(stderr, "%s\n", strerror(errno));
        return errno;
    }

    printf("file exist\n");

    fclose(fp);

    return 0;
}
```

上面的程序检查从命令行提供的文件是否存在，如果给定的文件存在，那么程序打印“文件存在”，否则它打印一个适当的错误消息。让我们提供一个文件系统中不存在的文件名，并在 x86_64 架构上检查程序的输出。

```cpp
[narendra@/media/partition/GFG]$ ./file_existence hello.c
Segmentation fault (core dumped)
```

为什么这个程序崩溃了，相反它应该显示一个适当的错误信息。该程序在 x86 架构上运行良好，但在 x86_64 架构上会崩溃。让我们看看代码有什么问题。仔细浏览程序，故意我还没有包括“strerror()”函数的原型。该函数返回“指向字符的指针”，这将打印一条错误消息，该消息取决于传递给该函数的 errno。请注意，x86 架构是 ILP-32 模型，这意味着整数、指针和 long 都是 32 位宽，这就是为什么程序会在这种架构上正确工作。但是 x86_64 是 LP-64 的型号，这意味着长，指针是 64 位宽。*在 C 语言中，当我们没有提供一个* *函数的原型时，编译器假设该函数返回一个整数*。在我们的例子中，我们没有包含“string.h”头文件(strerror 的原型在这个文件中声明)，这就是为什么编译器假设这个函数返回一个整数。但是它的返回类型是指向一个字符的指针。在 x86_64 中，指针是 64 位宽，整数是 32 位宽，这就是为什么当从函数返回时，返回的地址被截断(即 32 位宽的地址，这是 x86_64 上整数的大小)，这是无效的，当我们试图取消引用这个地址时，结果是分段错误。
现在包含“string.h”头文件并检查输出，程序将正常工作。

```cpp
[narendra@/media/partition/GFG]$ ./file_existence hello.c
No such file or directory
```

再考虑一个例子。

## C

```cpp
#include <stdio.h>

int main(void)
{
    int *p = malloc(sizeof(int));

    if (p == NULL) {
        perror("malloc()");
        return -1;
    }

    *p = 10;
    free(p);

    return 0;
}
```

上述代码在 IA-32 型号上运行良好，但在 IA-64 型号上将会失败。这段代码失败的原因是我们没有包含 malloc()函数的原型，并且在 IA-64 模型中返回值被截断。
本文由**纳伦德拉·康拉尔卡尔**整理。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。