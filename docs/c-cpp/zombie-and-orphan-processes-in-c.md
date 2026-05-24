# C

中的僵尸和孤儿进程

> 原文:[https://www . geesforgeks . org/僵尸和孤儿进程-in-c/](https://www.geeksforgeeks.org/zombie-and-orphan-processes-in-c/)

先决条件:[C](http://geeksquiz.com/fork-system-call/)中的叉()

<center>**Zombie Process:**</center>

A process which has finished the execution but still has entry in the process table to report to its parent process is known as a zombie process. A child process always first becomes a zombie before being removed from the process table. The parent process reads the exit status of the child process which reaps off the child process entry from the process table.

在下面的代码中，子进程使用 exit()系统调用完成其执行，而父进程休眠 50 秒，因此不调用 [wait()](https://en.wikipedia.org/wiki/Wait_%28system_call%29) ，并且子进程的条目仍然存在于进程表中。

```cpp
// A C program to demonstrate Zombie Process. 
// Child becomes Zombie as parent is sleeping
// when child process exits.
#include <stdlib.h>
#include <sys/types.h>
#include <unistd.h>
int main()
{
    // Fork returns process id
    // in parent process
    pid_t child_pid = fork();

    // Parent process 
    if (child_pid > 0)
        sleep(50);

    // Child process
    else        
        exit(0);

    return 0;
}
```

请注意，由于 fork()被禁用，上述代码可能无法与联机编译器一起工作。

<center>**Orphan Process:**</center>

A process whose parent process no more exists i.e. either finished or terminated without waiting for its child process to terminate is called an orphan process.

在下面的代码中，父进程完成执行并在子进程仍在执行时退出，现在被称为孤立进程。

然而，一旦其父进程死亡，孤儿进程很快被 init 进程采用。

```cpp
// A C program to demonstrate Orphan Process. 
// Parent process finishes execution while the
// child process is running. The child process
// becomes orphan.
#include<stdio.h>
#include <sys/types.h>
#include <unistd.h>

int main()
{
    // Create a child process      
    int pid = fork();

    if (pid > 0)
        printf("in parent process");

    // Note that pid is 0 in child process
    // and negative if fork() fails
    else if (pid == 0)
    {
        sleep(30);
        printf("in child process");
    }

    return 0;
}
```

请注意，由于 fork()被禁用，上述代码可能无法与在线编译器一起工作。

**相关:**
[知道什么是操作系统中的僵尸吗？](http://qa.geeksforgeeks.org/5282/any-idea-what-are-zombies-in-operating-system)
[僵尸进程及其预防](https://www.geeksforgeeks.org/zombie-processes-prevention/)

本文由**普拉哈尔·马图尔**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论