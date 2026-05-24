# fork()和使用它创建的内存共享 b/w 进程

> 原文:[https://www . geesforgeks . org/fork-memory-shared-bw-processes-created-using/](https://www.geeksforgeeks.org/fork-memory-shared-bw-processes-created-using/)

先决条件:[C](https://www.geeksforgeeks.org/fork-system-call/)中的叉()。

那么当我们做 fork()时，这两个过程实际上共享了哪些部分呢？
是每个进程的堆内存吗？
全局变量是否共享？
malloc 会给两者返回相同的地址吗？

让我们运行下面的程序，看看它的输出，以清除上面的问题。

```cpp
// C program to demonstrate working of fork()
#include <unistd.h>
#include <sys/types.h>
#include <errno.h>
#include <stdio.h>
#include <sys/wait.h>
#include <stdlib.h>

int globalVar; /*  A global variable*/

int main(void)
{
    int localVar = 0;
    int* p = (int*) malloc(2);
    pid_t childPID = fork();

    // Putting value at allocated address
    *p = 0;

    if (childPID >= 0) // fork was successful
    {
        if (childPID == 0) // child process
        {
            printf("\n Child Process Initial Value :: localVar"
                   " = %d, globalVar = %d", localVar,
                   globalVar);
            localVar++ ;
            globalVar++ ;

            int c = 500;
            printf("\n Child Process :: localVar = %d, "
                   "globalVar = %d", localVar, globalVar);
            printf("\n Address of malloced mem child = %p "
                   "and value is %d", p, *p);
            printf("\n lets change the value pointed my malloc");

            *p = 50;
            printf("\n Address of malloced mem child = %p "
                   "and value is %d", p, *p);
            printf("\n lets change the value pointed my "
                   "malloc in child");

            *p = 200;
            printf("\n Address of malloced mem child = %p "
                   "and value is %d\n\n\n", p, *p);
        }
        else // Parent process
        {
            printf("\n Parent process Initial Value :: "
                   "localVar = %d, globalVar = %d",
                   localVar, globalVar);

            localVar = 10;
            globalVar = 20;
            printf("\n Parent process :: localVar = %d,"
                  " globalVar = %d", localVar, globalVar);
            printf("\n Address of malloced mem parent= %p "
                   "and value is %d", p, *p);

            *p = 100;
            printf("\n Address of malloced mem parent= %p "
                   "and value is %d", p, *p);
            printf("\n lets change the value pointed my"
                    " malloc in child");
            *p = 400;
            printf("\n Address of malloced mem child = %p"
                   " and value is %d \n", p, *p);
        }
    }
    else // fork failed
    {
        printf("\n Fork failed, quitting!!!!!!\n");
        return 1;
    }

    return 0;
}
```

```cpp
 Parent process Initial Value :: localVar = 0, globalVar = 0
 Parent process :: localVar = 10, globalVar = 20
 Address of malloced mem parent= 0x1bb5010 and value is 0
 Address of malloced mem parent= 0x1bb5010 and value is 100
 lets change the value pointed my malloc in child
 Address of malloced mem child = 0x1bb5010 and value is 400 

 Child Process Initial Value :: localVar = 0, globalVar = 0
 Child Process :: localVar = 1, globalVar = 1
 Address of malloced mem child = 0x1bb5010 and value is 0
 lets change the value pointed my malloc
 Address of malloced mem child = 0x1bb5010 and value is 50
 lets change the value pointed my malloc in child
 Address of malloced mem child = 0x1bb5010 and value is 200

```

解释:

1.  因此，每个进程的子进程和父进程都有自己的全局变量和局部变量的副本，否则，如果它们共享了全局变量和局部变量，我们就会在子进程中得到“子进程初始值::局部变量= [10]，全局变量[20]”，这是在首先执行的父进程中分配的，但我们没有。
2.  Though address of memory returned by malloc is same but in actual they are pointing to or mapped to different physical address otherwise when parent assigned value of 100 at memory address 0x1535010 the same 100 we should have got in child but we got 0.

    本文由 **Abhilash Kumar Jaiswal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。