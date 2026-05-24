# 使用 C

中的 fork()从同一父进程创建 n 个子进程

> 原文:[https://www . geesforgeks . org/create-n-child-process-parent-process-using-fork-c/](https://www.geeksforgeeks.org/create-n-child-process-parent-process-using-fork-c/)

**fork()** 是一个系统调用函数，可以从父主进程生成子进程。使用一些条件，我们可以根据需要生成尽可能多的子进程。

我们已经给了 n，我们必须从同一个父进程(主进程)创建*n*-子进程。

示例:

```cpp
Input :3
Output :[son] pid 25332 from [parent] pid 25329
        [son] pid 25331 from [parent] pid 25329
        [son] pid 25330 from [parent] pid 25329

here 25332, 25331,25330 are child processes from same parent process
with process id 25329 

Input :5
Output :[son] pid 28519 from [parent] pid 28518
        [son] pid 28523 from [parent] pid 28518
        [son] pid 28520 from [parent] pid 28518
        [son] pid 28521 from [parent] pid 28518
        [son] pid 28522 from [parent] pid 28518

here 28519, 28519,28520,28521,28522 are child processes from same parent process
with process id 28518 

```

```cpp
#include<stdio.h>

int main()
{
    for(int i=0;i<5;i++) // loop will run n times (n=5)
    {
        if(fork() == 0)
        {
            printf("[son] pid %d from [parent] pid %d\n",getpid(),getppid());
            exit(0);
        }
    }
    for(int i=0;i<5;i++) // loop will run n times (n=5)
    wait(NULL);

}
```

输出:

```cpp
[son] pid 28519 from [parent] pid 28518
[son] pid 28523 from [parent] pid 28518
[son] pid 28520 from [parent] pid 28518
[son] pid 28521 from [parent] pid 28518
[son] pid 28522 from [parent] pid 28518

```

本文由 [**迪本杜·罗伊·乔杜里**](https://auth.geeksforgeeks.org/profile.php?user=Dibyendu Roy Chaudhuri) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。