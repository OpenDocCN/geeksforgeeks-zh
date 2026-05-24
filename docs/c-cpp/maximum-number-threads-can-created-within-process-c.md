# 在 C 中一个进程内可以创建的最大线程数

> 原文:[https://www . geesforgeks . org/最大线程数-可在进程内创建-c/](https://www.geeksforgeeks.org/maximum-number-threads-can-created-within-process-c/)

**线程**的执行是可由调度器独立管理的最小编程指令序列。线程是进程的一个组件，因此一个进程中可以关联多个线程。Linux 对每个进程没有单独的线程限制，但对系统上的进程总数有限制(因为线程只是 Linux 上具有共享地址空间的进程)。

我们的任务是找出单个进程中可以创建的最大线程数(pthread_create 可以创建的最大线程数)。可以看到的最大线程数是 ubuntu 通过使用命令:

```cpp
cat /proc/sys/kernel/threads-max
```

linux 的这个线程限制可以在运行时修改，方法是将所需的限制写入**/proc/sys/kernel/threads-max**。

在 ubuntu 操作系统上编译以下程序，以检查 c 语言中一个进程内可以创建的最大线程数。

```cpp
cc filename.c -pthread where filename.c 
is the name with which file is saved.
```

```cpp
// C program to find maximum number of thread within
// a process
#include<stdio.h>
#include<pthread.h>

// This function demonstrates the work of thread
// which is of no use here, So left blank
void *thread ( void *vargp){     }

int main()
{
    int err = 0, count = 0;
    pthread_t tid;

    // on success, pthread_create returns 0 and 
    // on Error, it returns error number
    // So, while loop is iterated until return value is 0
    while (err == 0)
    {
        err = pthread_create (&tid, NULL, thread, NULL);
        count++ ;
    }
    printf("Maximum number of thread within a Process"
                                   " is : %d\n", count);
}
```

输出:

```cpp
Maximum number of thread within a Process is : 32754

```

本文由[阿迪蒂亚·库马尔](https://www.linkedin.com/in/aditya-kumar-837315100/)供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。