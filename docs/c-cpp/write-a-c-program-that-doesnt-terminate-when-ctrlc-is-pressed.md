# 写一个按 Ctrl+C 时不终止的 C 程序

> 原文:[https://www . geesforgeks . org/write-a-c-program-the-not-terminal-当-ctrlc-被按下/](https://www.geeksforgeeks.org/write-a-c-program-that-doesnt-terminate-when-ctrlc-is-pressed/)

写一个按下 Ctrl+C 不会终止的 C 程序。它会打印一条消息“不能使用 Ctrl+c 终止”并继续执行。

对此我们可以使用 C 中的[信号处理。当按下](http://en.wikipedia.org/wiki/C_signal_handling) [Ctrl+C](http://en.wikipedia.org/wiki/Control-C) 时，产生 SIGINT 信号，我们可以捕捉到这个信号并运行我们定义的信号处理器。c 标准在 signal.h 头文件中定义了以下 6 个信号。

SIGABRT–异常终止。
SIGFPE–浮点异常。
SIGILL–无效指令。
SIGINT–发送给程序的互动关注请求。
SIGSEGV–无效内存访问。
SIGTERM–发送给程序的终止请求。

附加信号是指定的 Unix 和类 Unix 操作系统(如 Linux)定义了 15 个以上的附加信号。参见[http://en.wikipedia.org/wiki/<wbr>Unix _ signal # POSix _ signal](http://en.wikipedia.org/wiki/Unix_signal#POSIX_signals)
标准 C 库函数 [signal()](http://en.cppreference.com/w/c/program/signal) 可用于为上述任何信号设置处理器。

```cpp
/* A C program that does not terminate when Ctrl+C is pressed */
#include <stdio.h>
#include <signal.h>

/* Signal Handler for SIGINT */
void sigintHandler(int sig_num)
{
    /* Reset handler to catch SIGINT next time.
       Refer http://en.cppreference.com/w/c/program/signal */
    signal(SIGINT, sigintHandler);
    printf("\n Cannot be terminated using Ctrl+C \n");
    fflush(stdout);
}

int main ()
{
    /* Set the SIGINT (Ctrl-C) signal handler to sigintHandler 
       Refer http://en.cppreference.com/w/c/program/signal */
    signal(SIGINT, sigintHandler);

    /* Infinite loop */
    while(1)
    {        
    }
    return 0;
}
```

输出:按两次 Ctrl+C 时

```cpp

 Cannot be terminated using Ctrl+C

 Cannot be terminated using Ctrl+C
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。