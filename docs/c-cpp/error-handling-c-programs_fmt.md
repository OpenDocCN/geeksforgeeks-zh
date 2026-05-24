# C 程序中的错误处理

> 原文: [https://www.geeksforgeeks.org/error-handling-c-programs/](https://www.geeksforgeeks.org/error-handling-c-programs/)

虽然 C 语言不直接支持错误处理(或异常处理)，但是有一些方法可以在 C 语言中完成错误处理。程序员必须首先防止错误，并测试函数的返回值。
很多 C 函数调用在出现错误时都会返回`-1`或`NULL`，所以对这些返回值的快速测试很容易通过例如`if`语句来完成。例如，在[套接字编程](https://www.geeksforgeeks.org/socket-programming-cc/)中，像`Socket()`，`listen()`等函数的返回值。检查是否有错误。

## 示例: 套接字编程中的错误处理

```cpp
if ((server_fd = socket(AF_INET, SOCK_STREAM, 0)) == 0)
{
   perror("socket failed");
   exit(EXIT_FAILURE);
}
```

## C 中错误处理的不同方法

### 1. 全局变量 `errno`

在 C 语言中调用一个函数时，一个名为`errno`的变量会自动被赋予一个代码(值)，这个代码可以用来识别已经遇到的错误类型。它是一个全局变量，指示任何函数调用期间发生的错误，并在头文件`errno.h`中定义。`errno`的不同代码(值)表示不同类型的错误。下面列出了几种不同的`errno`值及其相应的含义:

```cpp
errno value       Error
1             /* Operation not permitted */
2             /* No such file or directory */
3             /* No such process */
4             /* Interrupted system call */
5             /* I/O error */
6             /* No such device or address */
7             /* Argument list too long */
8             /* Exec format error */
9             /* Bad file number */
10            /* No child processes */
11            /* Try again */
12            /* Out of memory */
13            /* Permission denied */
```

```cpp
// C implementation to see how errno value is
// set in the case of any error in C
#include <stdio.h>
#include <errno.h>

int main()
{
    // If a file is opened which does not exist,
    // then it will be an error and corresponding
    // errno value will be set
    FILE * fp;

    // opening a file which does
    // not exist.
    fp = fopen("GeeksForGeeks.txt", "r");

    printf(" Value of errno: %d\n ", errno);

    return 0;
}
```

输出:

```cpp
Value of errno: 2
```

注意: 这里的`errno`设置为 2，这意味着没有这样的文件或目录。在在线集成开发环境中，它可能会给出错误 13，表示权限被拒绝。

### 2. `perror()` 和 `strerror()`

上面获得的`errno`值指示遇到的错误类型。如果需要显示错误描述，则有两个函数可用于显示与`errno`关联的文本消息。这些函数是:

*   **`perror`**: 它显示传递给它的字符串，后跟一个冒号、一个空格，然后是当前`errno`值的文本表示。
    **语法:**

    ```cpp
    void perror (const char *str)
    ```
    `str`: 是一个字符串，包含要在错误消息本身之前打印的自定义消息。

*   **`strerror()`**: 返回当前`errno`值的文本表示的指针。
    **语法:**

    ```cpp
    char *strerror (int errnum)
    ```
    `errnum`: 是错误编号(`errno`)。

```cpp
// C implementation to see how perror() and strerror()
// functions are used to print the error messages.
#include <stdio.h>
#include <errno.h>
#include <string.h>

int main ()
{
    FILE *fp;

    // If a file is opened which does not exist,
    // then it will be an error and corresponding
    // errno value will be set
    fp = fopen(" GeeksForGeeks.txt ", "r");

    // opening a file which does
    // not exist.
    printf("Value of errno: %d\n ", errno);
    printf("The error message is : %s\n", strerror(errno));
    perror("Message from perror");

    return 0;
}
```

输出:
**在个人桌面:**

```cpp
Value of errno: 2
The error message is : No such file or directory
Message from perror: No such file or directory
```

**在线 IDE 上:**

```cpp
Value of errno: 13
The error message is : Permission denied
```

**注意:** 函数`perror()`显示一个传递给它的字符串，后跟一个冒号和当前`errno`值的文本消息。

### 3. 退出状态

C 标准指定了两个常量: `EXIT_SUCCESS`和`EXIT_FAILURE`，它们可以传递给`exit()`以分别表示成功或不成功终止。这些是在`stdlib.h`中定义的宏。

```cpp
// C implementation which shows the
// use of EXIT_SUCCESS and EXIT_FAILURE.
#include <stdio.h>
#include <errno.h>
#include <string.h>
#include <stdlib.h>

int main ()
{
    FILE * fp;
    fp = fopen ("filedoesnotexist.txt", "rb");

    if (fp == NULL)
    {
        printf("Value of errno: %d\n", errno);
        printf("Error opening the file: %s\n", strerror(errno));
        perror("Error printed by perror");

        exit(EXIT_FAILURE);
        printf("I will not be printed\n");
    }

    else
    {
        fclose (fp);
        exit(EXIT_SUCCESS);
        printf("I will not be printed\n");
    }
    return 0;
}
```

输出:

```cpp
Value of errno: 2
Error opening the file: No such file or directory
Error printed by perror: No such file or directory
```

### 4. 除以零错误

C 程序员常犯的一个错误是在除法命令之前不检查除数是否为零。除以零会导致未定义行为，C 语言没有提供任何可以处理这种情况的结构。你最好的选择是从一开始就避免除以零，通过检查分母。

```cpp
// C program to check and rectify
// divide by zero condition
#include<stdio.h>
#include <stdlib.h>

void function(int);

int main()
{
    int x = 0;
    function(x);
    return 0;
}

void function(int x)
{
    float fx;

    if (x==0)
    {
        printf("Division by Zero is not allowed");
        fprintf(stderr, "Division by zero! Exiting...\n");
        exit(EXIT_FAILURE);
    }
    else
    {
        fx = 10 / x;
        printf("f(x) is: %.5f", fx);
    }
}
```

输出:

```cpp
Division by Zero is not allowed
```

本文由 [**MAZHAR IMAM KHAN**](https://www.linkedin.com/in/mazhar-imam-khan-95a34ab3) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。