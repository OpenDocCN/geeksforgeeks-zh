# 双叉防止僵尸进程

> 原文: [https://www.geeksforgeeks.org/double-forking-prevent-zombie-process/](https://www.geeksforgeeks.org/double-forking-prevent-zombie-process/)

我们已经讨论了[预防僵尸的三种方法](https://www.geeksforgeeks.org/zombie-processes-prevention/)。这篇文章是关于僵尸预防的另一种方法。

## 僵尸进程

一个进程已经完成了执行，但是在进程表中仍然有条目要报告给它的父进程，这个进程被称为僵尸进程。子进程在从进程表中移除之前总是先变成僵尸。

## 创建孙子/双叉有什么帮助？

1.  父进程调用 `wait` 并创建一个子进程。子进程生了一个孙子进程然后退出。
2.  孙子进程执行其指令（任务）并最终终止。由于子进程已经退出，孙子进程将由 `init` 进程接管。
3.  收集孙子进程的退出状态。因此孙子进程不会变成僵尸。

注意：子进程不是僵尸，因为父进程调用了 `wait`。同样在这种情况下，父进程不能验证孙进程的退出状态。

```cpp
// C program of zombie prevention by
// creating grandchild or double forking
#include <stdio.h>
#include <unistd.h>
#include <stdlib.h>
#include <sys/wait.h>

int main()
{
    pid_t pid;

    // fork first time
    pid = fork();

    if (pid == 0)
    {
        // double fork
        pid = fork();
        if (pid == 0)
            printf("Grandchild pid : %d\n Child"
                   " pid : %d\n", getpid(), getppid());
    }

    else
    {
        wait(NULL);
        sleep(10);
    }
}
```

本文由**普拉莫德·库马尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。