# C 中的 exec 函数族

> 原文:[https://www . geesforgeks . org/exec-functions-family-in-c/](https://www.geeksforgeeks.org/exec-family-of-functions-in-c/)

exec 系列函数用一个新进程替换当前运行的进程。它可以通过使用另一个 C 程序来运行一个 C 程序。它位于头文件 **unistd.h.** 下，exec 家族中有许多成员，下面通过示例显示了这些成员。

*   **execvp** : Using this command, the created child process does not have to run the same program as the parent process does. The **exec** type system calls allow a process to run any program files, which include a binary executable or a shell script . **Syntax:**

    ```cpp
    int execvp (const char *file, char *const argv[]);
    ```

    **文件:**指向与正在执行的文件关联的文件名。
    **argv:** 是一个空终止的字符指针数组。

    让我们看一个小例子来展示如何在 c 语言中使用 execvp()函数。c 文件， **EXEC.c** 和 **execDemo.c** 我们将通过调用 execDemo.c 中的 execvp()函数，用 EXEC.c 替换 execDemo.c。

    ```cpp
    //EXEC.c

    #include<stdio.h>
    #include<unistd.h>

    int main()
    {
        int i;

        printf("I am EXEC.c called by execvp() ");
        printf("\n");

        return 0;
    }
    ```

    现在，使用命令创建一个 EXEC.c 的可执行文件

    ```cpp
    gcc EXEC.c -o EXEC
    ```

    ```cpp
    //execDemo.c

    #include<stdio.h>
    #include<stdlib.h>
    #include<unistd.h>
    int main()
    {
            //A null terminated array of character 
            //pointers
            char *args[]={"./EXEC",NULL};
            execvp(args[0],args);

            /*All statements are ignored after execvp() call as this whole 
            process(execDemo.c) is replaced by another process (EXEC.c)
            */
            printf("Ending-----");

        return 0;
    }
    ```

    现在，使用命令创建一个 execDemo.c 的可执行文件

    ```cpp
    gcc execDemo.c -o execDemo
    ```

    使用命令运行 execDemo.cby 的可执行文件后。/excDemo，我们得到以下输出:

    ```cpp
    I AM EXEC.c called by execvp()

    ```

    编译 execDemo.c 文件时，只要执行了 execvp 语句(args[0]，args)，这个程序就会被 EXEC.c 程序替换。不会打印“Ending——因为只要调用 execvp()函数，这个程序就会被 EXEC.c 程序替换。

*   **execv** : This is very similar to execvp() function in terms of syntax as well. The syntax of **execv()** is as shown below:**Syntax:**

    ```cpp
    int execv(const char *path, char *const argv[]);
    ```

    **路径:**应该指向正在执行的文件的路径。
    **argv[]:** 是一个空终止的字符指针数组。

    让我们看一个小例子，展示如何在 c 语言中使用 execv()函数。我们将有两个。c 文件， **EXEC.c** 和 **execDemo.c** 我们将通过调用 execDemo.c 中的 execv()函数，用 EXEC.c 替换 execDemo.c。

    ```cpp
    //EXEC.c

    #include<stdio.h>
    #include<unistd.h>

    int main()
    {
        int i;

        printf("I am EXEC.c called by execv() ");
        printf("\n");
        return 0;
    }
    ```

    现在，使用命令创建一个 EXEC.c 的可执行文件

    ```cpp
    gcc EXEC.c -o EXEC
    ```

    ```cpp
    //execDemo.c

    #include<stdio.h>
    #include<stdlib.h>
    #include<unistd.h>
    int main()
    {
            //A null terminated array of character 
            //pointers
            char *args[]={"./EXEC",NULL};
            execv(args[0],args);

            /*All statements are ignored after execvp() call as this whole 
            process(execDemo.c) is replaced by another process (EXEC.c)
            */
            printf("Ending-----");

        return 0;
    }
    ```

    现在，使用命令创建一个 execDemo.c 的可执行文件

    ```cpp
    gcc execDemo.c -o execDemo
    ```

    使用命令运行 execDemo.c 的可执行文件后。/excDemo，我们得到以下输出:

    ```cpp
    I AM EXEC.c called by execv()

    ```

*   **execlp and execl** : These two also serve the same purpose but the syntax of them are a bit different which is as shown below:**Syntax:**

    ```cpp
    int execlp(const char *file, const char *arg,.../* (char  *) NULL */);
    int execl(const char *path, const char *arg,.../* (char  *) NULL */);

    ```

    **文件:**与正在执行的文件相关联的文件名
    **const char *arg** **和省略号**:描述指向空终止字符串的一个或多个指针的列表，该列表表示已执行程序可用的参数列表。

    上面显示的相同的 C 程序可以用 execlp()或 execl()函数执行，它们将执行相同的任务，即用新的进程替换当前的进程。

*   **execvpe and execle** : These two also serve the same purpose but the syntax of them are a bit different from all the above members of exec family. The synatxes of both of them are shown below :
    **Syntax:**

    ```cpp
    int execvpe(const char *file, char *const argv[],char *const envp[]);

    Syntax:
    int execle(const char *path, const char *arg, .../*, (char *) NULL, 
    char * const envp[] */);

    ```

    上面显示的语法有一个不同于上面所有 exec 成员的参数，即
    **char * const envp[]:** 允许调用者通过参数 envp 指定执行程序的环境。
    **envp:** 此参数是指向空终止字符串的指针数组，必须由空指针终止。其他函数从调用进程的外部变量 environ 中获取新进程映像的环境。

**<u>参考:</u>** [exec(3)手册页](https://linux.die.net/man/3/execvp)

本文由 **MAZHAR IMAM KHAN** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。