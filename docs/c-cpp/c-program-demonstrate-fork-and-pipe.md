# C 程序演示叉()和管()

> 原文:[https://www . geesforgeks . org/c-program-explain-fork-and-pipe/](https://www.geeksforgeeks.org/c-program-demonstrate-fork-and-pipe/)

编写 Linux C 程序创建两个进程 P1 和 P2。P1 拿了一根绳子递给 P2。P2 在不使用 string 函数的情况下将接收到的字符串与另一个字符串连接起来，并将其发送回 P1 进行打印。

示例:

```cpp
Other string is: *forgeeks.org*

Input  : www.geeks
Output : www.geeksforgeeks.org

Input :  www.practice.geeks
Output : practice.geeksforgeeks.org

```

**说明:**

*   为了创建子进程，我们使用 fork()。fork()返回:
    *   **< 0** 无法创建子(新)流程
    *   **=0** 为子流程
    *   **> 0** 即子进程到父进程的进程标识。当> 0 父进程执行时。
*   pipe()用于将信息从一个进程传递到另一个进程。pipe()是单向的因此，对于进程之间的双向通信，可以设置两个管道，每个方向一个。

    ```cpp
     *Example:* 
     int fd[2];
     pipe(fd);
     fd[0]; *//-> for using read end*
     fd[1]; *//-> for using write end*

    ```

**内部父进程:**我们首先关闭第一个管道的读取端(fd1[0])，然后通过管道的写入端(fd1[1])写入字符串。现在家长将**等待**直到子进程完成。在子进程之后，父进程将关闭第二个管道的写入端(fd2[1])，并通过管道的读取端(fd2[0])读取字符串。

**子进程内部:**子进程通过关闭管道的写端(fd1[1])读取父进程发送的第一个字符串，读取后连接两个字符串，并通过 fd2 管道将字符串传递给父进程，并将退出。

```cpp
// C program to demonstrate use of fork() and pipe()
#include<stdio.h>
#include<stdlib.h>
#include<unistd.h>
#include<sys/types.h>
#include<string.h>
#include<sys/wait.h>

int main()
{
    // We use two pipes
    // First pipe to send input string from parent
    // Second pipe to send concatenated string from child

    int fd1[2];  // Used to store two ends of first pipe
    int fd2[2];  // Used to store two ends of second pipe

    char fixed_str[] = "forgeeks.org";
    char input_str[100];
    pid_t p;

    if (pipe(fd1)==-1)
    {
        fprintf(stderr, "Pipe Failed" );
        return 1;
    }
    if (pipe(fd2)==-1)
    {
        fprintf(stderr, "Pipe Failed" );
        return 1;
    }

    scanf("%s", input_str);
    p = fork();

    if (p < 0)
    {
        fprintf(stderr, "fork Failed" );
        return 1;
    }

    // Parent process
    else if (p > 0)
    {
        char concat_str[100];

        close(fd1[0]);  // Close reading end of first pipe

        // Write input string and close writing end of first
        // pipe.
        write(fd1[1], input_str, strlen(input_str)+1);
        close(fd1[1]);

        // Wait for child to send a string
        wait(NULL);

        close(fd2[1]); // Close writing end of second pipe

        // Read string from child, print it and close
        // reading end.
        read(fd2[0], concat_str, 100);
        printf("Concatenated string %s\n", concat_str);
        close(fd2[0]);
    }

    // child process
    else
    {
        close(fd1[1]);  // Close writing end of first pipe

        // Read a string using first pipe
        char concat_str[100];
        read(fd1[0], concat_str, 100);

        // Concatenate a fixed string with it
        int k = strlen(concat_str);
        int i;
        for (i=0; i<strlen(fixed_str); i++)
            concat_str[k++ ] = fixed_str[i];

        concat_str[k] = '\0';   // string ends with '\0'

        // Close both reading ends
        close(fd1[0]);
        close(fd2[0]);

        // Write concatenated string and close writing end
        write(fd2[1], concat_str, strlen(concat_str)+1);
        close(fd2[1]);

        exit(0);
    }
}
```

```cpp
Input : www.geeks
Output : Concatenated string
         www.geeksforgeeks.org

```

 **参考文献:**
http://www . csl . MTU . edu/cs 4411 . CK/www/NOtes/process/fork/create . html
http://www . csl . MTU . edu/cs 4411 . CK/www/NOtes/process/fork/wait . html
http://searchenterpriselinux.techtarget.com/definition/pipe

本文由 **Kartik Ahuja** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。