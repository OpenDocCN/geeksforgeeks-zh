# 使用 fork()

创建多个进程

> 原文:[https://www . geeksforgeeks . org/creating-multi-process-use-fork/](https://www.geeksforgeeks.org/creating-multiple-process-using-fork/)

**先决条件–**[引入 fork](https://www.geeksforgeeks.org/fork-system-call/) 、 [getpid()和 getppid()](https://www.geeksforgeeks.org/getppid-getpid-linux)
**问题陈述–**编写一个程序，使用 [fork()](https://www.geeksforgeeks.org/fork-system-call/) 函数创建一个有三个子进程的父进程，每个进程在其中找到自己的 id。例如:

```cpp
Output :parent
28808 28809 
 my id is 28807 
First child
0 28810 
my id is 28808  
Second child
28808 0 
my id is 28809  
third child
0 0 

```

**解释–**在这里，我们使用了 fork()函数来创建四个进程一个父进程和三个子进程。

*   现有进程可以通过调用 fork()函数来创建新的进程。
*   fork()创建的新进程称为子进程。
*   我们在这里使用 [getpid()](https://www.geeksforgeeks.org/getppid-getpid-linux) 来获取进程 id
*   在 fork()中，创建的总进程是= fork()的 2^number

**注意–**在某个时刻，子进程不必首先执行，父进程也不必首先分配 CPU，任何进程都可以在某个时间段分配 CPU。此外，在不同的执行过程中，进程 id 可能不同。

**代码 1–**使用`getpid()`

```cpp
// C++ program to demonstrate creating processes using fork()
#include <unistd.h>
#include <stdio.h>

int main()
{
    // Creating first child
    int n1 = fork();

    // Creating second child. First child
    // also executes this line and creates
    // grandchild.
    int n2 = fork();

    if (n1 > 0 && n2 > 0) {
        printf("parent\n");
        printf("%d %d \n", n1, n2);
        printf(" my id is %d \n", getpid());
    }
    else if (n1 == 0 && n2 > 0)
    {
        printf("First child\n");
        printf("%d %d \n", n1, n2);
        printf("my id is %d  \n", getpid());
    }
    else if (n1 > 0 && n2 == 0)
    {
        printf("Second child\n");
        printf("%d %d \n", n1, n2);
        printf("my id is %d  \n", getpid());
    }
    else {
        printf("third child\n");
        printf("%d %d \n", n1, n2);
        printf(" my id is %d \n", getpid());
    }
    return 0;
}
```

**输出–**

```cpp
parent
28808 28809 
 my id is 28807 
First child
0 28810 
my id is 28808  
Second child
28808 0 
my id is 28809  
third child
0 0 

```

**代码 2–**使用`getppid()`

```cpp
// C++ program to demonstrate creating processes using fork()
#include <unistd.h>
#include <stdio.h>

int main()
{
    // Creating first child
    int n1 = fork();

    // Creating second child. First child
    // also executes this line and creates
    // grandchild.
    int n2 = fork();

    if (n1 > 0 && n2 > 0)
    {
        printf("parent\n");
        printf("%d %d \n", n1, n2);
        printf(" my id is %d \n", getpid());
        printf(" my parentid is %d \n", getppid());
    }
    else if (n1 == 0 && n2 > 0)
    {
        printf("First child\n");
        printf("%d %d \n", n1, n2);
        printf("my id is %d  \n", getpid());
        printf(" my parentid is %d \n", getppid());
    }
    else if (n1 > 0 && n2 == 0)
    {
        printf("second child\n");
        printf("%d %d \n", n1, n2);
        printf("my id is %d  \n", getpid());
        printf(" my parentid is %d \n", getppid());
    }
    else {
        printf("third child\n");
        printf("%d %d \n", n1, n2);
        printf(" my id is %d \n", getpid());
        printf(" my parentid is %d \n", getppid());
    }

    return 0;
}
```

**输出–**

```cpp
parent
5219 5220 
 my id is 5217 
 my parentid is 5215 
First child
0 5221 
my id is 5219  
 my parentid is 1 
second child
5219 0 
my id is 5220  
my parentid is 1 
third child
0 0 
 my id is 5221 
 my parentid is 1 

```

本文由 **Pushpanjali Chauhan** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。