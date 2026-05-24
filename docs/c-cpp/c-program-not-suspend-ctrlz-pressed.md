# 按下 Ctrl+Z 时不暂停的 C 程序

> 原文:[https://www . geesforgeks . org/c-program-not-suspend-ctrl z-prested/](https://www.geeksforgeeks.org/c-program-not-suspend-ctrlz-pressed/)

写一个按 Ctrl+Z 不终止的 C 程序。它会打印一条消息“不能使用 Ctrl+Z 暂停”并继续执行。

对此我们可以使用 [Unix 信号](https://en.wikipedia.org/wiki/Unix_signal#POSIX_signals)。当按下 Ctrl+Z 时，产生 SIGTSTP 信号。

**SIGTTP**信号由其控制终端发送给进程，请求其停止(终端停止)。我们可以捕捉到这个信号，并运行我们自己定义的信号。
标准 C 库函数**信号()**可用于为上述任何信号设置处理器。

```cpp
// C program that does not suspend when
// Ctrl+Z is pressed
#include <stdio.h>
#include <signal.h>

// Signal Handler for SIGTSTP
void sighandler(int sig_num)
{
    // Reset handler to catch SIGTSTP next time
    signal(SIGTSTP, sighandler);
    printf("Cannot execute Ctrl+Z\n");
}

int main()
{
    // Set the SIGTSTP (Ctrl-Z) signal handler
    // to sigHandler
    signal(SIGTSTP, sighandler);
    while(1)
    {
    }
    return 0;
}
```

输出:

```cpp
Cannot execute Ctrl+Z

```

本文由**普拉莫德·库马尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。