# C 中的 exec 函数族

> 原文: [https://www.geeksforgeeks.org/exec-family-of-functions-in-c/](https://www.geeksforgeeks.org/exec-family-of-functions-in-c/)

exec 系列函数用一个新进程替换当前运行的进程。它可以通过使用另一个 C 程序来运行一个 C 程序。它位于头文件 `unistd.h` 下，exec 家族中有许多成员，下面通过示例显示了这些成员。

## execvp

使用此命令，创建的子进程不必运行与父进程相同的程序。`exec` 类型的系统调用允许进程运行任何程序文件，包括二进制可执行文件或 shell 脚本。

**语法:**

```cpp
int execvp (const char *file, char *const argv[]);
```

- `file`: 指向与正在执行的文件关联的文件名。
- `argv`: 是一个空终止的字符指针数组。

让我们看一个小例子来展示如何在 C 语言中使用 `execvp()` 函数。我们将有两个 C 文件，`EXEC.c` 和 `execDemo.c`。我们将通过调用 `execDemo.c` 中的 `execvp()` 函数，用 `EXEC.c` 替换 `execDemo.c`。

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

现在，使用命令创建一个 `EXEC.c` 的可执行文件：

```bash
gcc EXEC.c -o EXEC
```

```cpp
//execDemo.c
#include<stdio.h>
#include<stdlib.h>
#include<unistd.h>
int main()
{
    //A null terminated array of character pointers
    char *args[]={"./EXEC",NULL};
    execvp(args[0],args);

    /*All statements are ignored after execvp() call as this whole
    process(execDemo.c) is replaced by another process (EXEC.c)
    */
    printf("Ending-----");
    return 0;
}
```

现在，使用命令创建一个 `execDemo.c` 的可执行文件：

```bash
gcc execDemo.c -o execDemo
```

使用命令运行 `execDemo.c` 的可执行文件后 (`./execDemo`)，我们得到以下输出:

```text
I AM EXEC.c called by execvp()
```

编译 `execDemo.c` 文件时，只要执行了 `execvp(args[0],args)` 语句，这个程序就会被 `EXEC.c` 程序替换。不会打印 "Ending-----"，因为只要调用 `execvp()` 函数，这个程序就会被 `EXEC.c` 程序替换。

## execv

这在语法上与 `execvp()` 函数非常相似。`execv()` 的语法如下所示：

**语法:**

```cpp
int execv(const char *path, char *const argv[]);
```

- `path`: 应该指向正在执行的文件的路径。
- `argv[]`: 是一个空终止的字符指针数组。

让我们看一个小例子，展示如何在 C 语言中使用 `execv()` 函数。我们将有两个 C 文件，`EXEC.c` 和 `execDemo.c`。我们将通过调用 `execDemo.c` 中的 `execv()` 函数，用 `EXEC.c` 替换 `execDemo.c`。

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

现在，使用命令创建一个 `EXEC.c` 的可执行文件：

```bash
gcc EXEC.c -o EXEC
```

```cpp
//execDemo.c
#include<stdio.h>
#include<stdlib.h>
#include<unistd.h>
int main()
{
    //A null terminated array of character pointers
    char *args[]={"./EXEC",NULL};
    execv(args[0],args);

    /*All statements are ignored after execv() call as this whole
    process(execDemo.c) is replaced by another process (EXEC.c)
    */
    printf("Ending-----");
    return 0;
}
```

现在，使用命令创建一个 `execDemo.c` 的可执行文件：

```bash
gcc execDemo.c -o execDemo
```

使用命令运行 `execDemo.c` 的可执行文件后 (`./execDemo`)，我们得到以下输出:

```text
I AM EXEC.c called by execv()
```

## execlp 和 execl

这两个函数也服务于相同的目的，但它们的语法有点不同，如下所示：

**语法:**

```cpp
int execlp(const char *file, const char *arg,.../* (char  *) NULL */);
int execl(const char *path, const char *arg,.../* (char  *) NULL */);
```

- `file`: 与正在执行的文件相关联的文件名。
- `const char *arg` 和省略号: 描述指向空终止字符串的一个或多个指针的列表，该列表表示已执行程序可用的参数列表。

上面显示的相同的 C 程序可以用 `execlp()` 或 `execl()` 函数执行，它们将执行相同的任务，即用新的进程替换当前的进程。

## execvpe 和 execle

这两个函数也服务于相同的目的，但它们的语法与上述所有 exec 家族成员都有所不同。两者的语法如下所示：

**语法:**

```cpp
int execvpe(const char *file, char *const argv[],char *const envp[]);
int execle(const char *path, const char *arg, .../*, (char *) NULL, char * const envp[] */);
```

上面显示的语法有一个不同于上面所有 exec 成员的参数，即 `char * const envp[]`，它允许调用者通过参数 `envp` 指定执行程序的环境。`envp` 参数是指向空终止字符串的指针数组，必须由空指针终止。其他函数从调用进程的外部变量 `environ` 中获取新进程映像的环境。

**参考:** [exec(3) 手册页](https://linux.die.net/man/3/execvp)

本文由 **MAZHAR IMAM KHAN** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。