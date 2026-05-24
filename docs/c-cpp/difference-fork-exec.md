# 【fork()和 exec() 的区别

> 原文:[https://www.geeksforgeeks.org/difference-fork-exec/](https://www.geeksforgeeks.org/difference-fork-exec/)

每一个应用(程序)都是通过进程来执行的，**进程**是一个程序的运行实例。流程是通过不同的系统调用创建的，最流行的是 **fork()** 和 **exec()**

叉()

```cpp
pid_t pid = fork();

```

fork()通过复制调用进程来创建一个新进程。新进程(称为子进程)是调用进程(称为父进程)的精确副本，但以下情况除外:

1.  子进程有自己唯一的进程标识，该进程标识与任何现有进程组的标识都不匹配。
2.  子进程的父进程标识与父进程的进程标识相同。
3.  子节点不会继承其父节点的内存锁和信号量调整。
4.  子级不会从其父级继承未完成的异步输入/输出操作，也不会从其父级继承任何异步输入/输出上下文。

**fork()**
返回值成功时，父进程返回子进程的 PID，子进程返回 0。失败时，在父进程中返回-1，不创建子进程，并且适当地设置 errno。
T4【详细篇】上叉系统调用

**执行（）**

exec()函数系列**用新的过程映像替换当前过程映像。它将程序加载到当前的进程空间中，并从入口点运行它。**

exec()家族由以下几个函数组成，我在下面的 C 程序中实现了 **execv()** ，大家可以试试休息作为练习

```cpp
int execl(const char *path, const char *arg, ...);
int execlp(const char *file, const char *arg, ...);
int execle(const char *path, const char *arg, ..., 
                               char * const envp[]);
int execv(const char *path, char *const argv[]);
int execvp(const char *file, char *const argv[]);
int execvpe(const char *file, char *const argv[], 
                              char *const envp[]);

```

**fork vs exec**

*   fork 启动一个新的进程，它是调用它的进程的副本，而 exec 用另一个(不同的)进程映像替换当前的进程映像。
*   在 fork()的情况下，父进程和子进程同时执行，而控制永远不会返回到原始程序，除非出现 exec()错误。

```cpp
// C program to illustrate  use of fork() &
// exec() system call for process creation

#include <stdio.h>
#include <sys/types.h>
#include <unistd.h> 
#include <stdlib.h>
#include <errno.h>  
#include <sys/wait.h>

int main(){
   pid_t  pid;
   int ret = 1;
   int status;
   pid = fork();

   if (pid == -1){

      // pid == -1 means error occured
      printf("can't fork, error occured\n");
      exit(EXIT_FAILURE);
   }
   else if (pid == 0){

      // pid == 0 means child process created
      // getpid() returns process id of calling process
      // Here It will return process id of child process
      printf("child process, pid = %u\n",getpid());
      // Here It will return Parent of child Process means Parent process it self
      printf("parent of child process, pid = %u\n",getppid()); 

      // the argv list first argument should point to  
      // filename associated with file being executed
      // the array pointer must be terminated by NULL 
      // pointer
      char * argv_list[] = {"ls","-lart","/home",NULL};

      // the execv() only return if error occured.
      // The return value is -1
      execv("ls",argv_list);
      exit(0);
   }
   else{
      // a positive number is returned for the pid of
      // parent process
      // getppid() returns process id of parent of 
      // calling process
// Here It will return parent of parent process's ID
      printf("Parent Of parent process, pid = %u\n",getppid());
      printf("parent process, pid = %u\n",getpid()); 

        // the parent process calls waitpid() on the child
        // waitpid() system call suspends execution of 
        // calling process until a child specified by pid
        // argument has changed state
        // see wait() man page for all the flags or options
        // used here 
        if (waitpid(pid, &status, 0) > 0) {

            if (WIFEXITED(status) && !WEXITSTATUS(status)) 
              printf("program execution successful\n");

            else if (WIFEXITED(status) && WEXITSTATUS(status)) {
                if (WEXITSTATUS(status) == 127) {

                    // execv failed
                    printf("execv failed\n");
                }
                else 
                    printf("program terminated normally,"
                       " but returned a non-zero status\n");                
            }
            else 
               printf("program didn't terminate normally\n");            
        } 
        else {
           // waitpid() failed
           printf("waitpid() failed\n");
        }
      exit(0);
   }
   return 0;
}
```

输出:

```cpp
parent process, pid = 11523
child process, pid = 14188
Program execution successful

```

**参考资料:**
Linux 手册页

本文由 **[曼德普·辛格](https://github.com/msdeep14)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。