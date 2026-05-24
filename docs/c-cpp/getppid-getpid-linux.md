# Linux 中的 getppid()和 getpid()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/get PID-get id-Linux/

getppid()和 getpid()都是 **unistd.h** 库中定义的内置函数。

1.  **getppid() :** returns the process ID of the parent of the calling process. If the calling process was created by the **[fork()](https://www.geeksforgeeks.org/fork-system-call/)** function and the parent process still exists at the time of the getppid function call, this function returns the process ID of the parent process. Otherwise, this function returns a value of 1 which is the process id for **init** process.
    **Syntax:**

    ```cpp
    pid_t getppid(void);

    ```

    **返回类型:** getppid()返回当前进程的父进程的进程 id。它从不出错，因此总是成功的。

    ```cpp
    // C++ Code to demonstrate getppid()
    #include <iostream>
    #include <unistd.h>
    using namespace std;

    // Driver Code
    int main()
    {
        int pid;
        pid = fork();
        if (pid == 0)
        {
            cout << "\nParent Process id : " 
                 << getpid() << endl;
            cout << "\nChild Process with parent id : " 
                 << getppid() << endl;
        }
        return 0;
    }
    ```

    输出(不同系统会有所不同):

    ```cpp
    Parent Process id of current process : 3849
    Child Process with parent id : 3851

    ```

    **注意:**在某个时刻，子进程不必先执行，父进程也不必先分配 CPU，任何进程都可以在某个时间段分配 CPU。此外，在不同的执行过程中，进程 id 可能不同。

2.  **getpid() :** returns the process ID of the calling process. This is often used by routines that generate unique temporary filenames.
    **Syntax:**

    ```cpp
    pid_t getpid(void);

    ```

    **返回类型:** getpid()返回当前进程的进程 id。它从不出错，因此总是成功的。

    ```cpp
    // C++ Code to demonstrate getpid()
    #include <iostream>
    #include <unistd.h>
    using namespace std;

    // Driver Code
    int main()
    {
        int pid = fork();
        if (pid == 0)
            cout << "\nCurrent process id of Process : " 
                 << getpid() << endl;
        return 0;
    }
    ```

    输出(不同系统会有所不同):

    ```cpp
    Current process id of Process : 4195

    ```

本文由 **Pushpanjali Chauhan** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。