# exit()、abort()和assert()

> 原文：[https://www.geeksforgeeks.org/understanding-exit-abort-and-assert/](https://www.geeksforgeeks.org/understanding-exit-abort-and-assert/)

## exit()

```cpp
void exit ( int status );
```

`exit()`正常终止进程。
`status`：状态值返回到父进程。通常，状态值 `0` 或常量 `EXIT_SUCCESS` 表示成功，任何其他值或常量 `EXIT_FAILURE` 用于表示错误。`exit()`执行以下操作。
* 刷新未写入的缓冲数据。
* 关闭所有打开的文件。
* 删除临时文件。
* 向操作系统返回整数退出状态。

C 标准库函数 [`atexit()`](http://www.cplusplus.com/reference/clibrary/cstdlib/atexit/) 可用于自定义 `exit()` 在程序终止时执行附加动作。

`exit()` 用法示例：

```cpp
/* exit example */
#include <stdio.h>
#include <stdlib.h>

int main ()
{
  FILE * pFile;
  pFile = fopen ("myfile.txt", "r");
  if (pFile == NULL)
  {
    printf ("Error opening file");
    exit (1);
  }
  else
  {
    /* file operations here */
  }
  return 0;
}
```

当调用 `exit()` 时，属于该进程的任何打开的文件描述符都被关闭，该进程的任何子进程都被进程 `1` (`init`) 继承，并且该进程父进程被发送一个 `SIGCHLD` 信号。

`exit()` 背后的奥秘在于它只接受 `0`–`255` 范围内的整数参数。超出范围的退出值会导致意外的退出代码。大于 `255` 的退出值返回以 `256` 为模的退出代码。
例如，`exit(9999)` 给出的退出代码为 `15`（即 `9999 % 256 = 15`）。

下面是 C 实现来说明上述事实：

```cpp
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <sys/types.h>
#include <sys/wait.h>

int main(void)
{
    pid_t pid = fork();

    if ( pid == 0 )
    {
       exit(9999); //passing value more than 255
    }

    int status;
    waitpid(pid, &status, 0);

    if ( WIFEXITED(status) )
    {
        int exit_status = WEXITSTATUS(status);
        printf("Exit code: %d\n", exit_status);
    }

    return 0;
}
```

输出：

```cpp
Exit code: 15
```

请注意，由于 `fork()` 被禁用，上述代码可能无法与在线编译器一起工作。

说明：是 `8` 位整数溢出的效果。`255` 后（所有 `8` 位设置）为 `0`。
所以输出是“退出码模 `256`”。上面的输出实际上是值 `9999` 和 `256` 的模，即 `15`。

## abort()

```cpp
void abort ( void );
```

与 `exit()` 函数不同，`abort()` 不能关闭打开的文件。它也可能不会删除临时文件，也可能不会刷新流缓冲区。此外，它不调用用 [`atexit()`](http://www.cplusplus.com/reference/clibrary/cstdlib/atexit/) 注册的函数。

这个函数实际上是通过发出一个 `SIGABRT` 信号来终止进程的，你的程序可以包含一个处理器来截取这个信号（见[这个](http://msdn.microsoft.com/en-us/library/xdkz3x12%28VS.80%29.aspx)）。

所以像下面这样的程序可能不会把“Geeks for Geeks”写入“tempfile.txt”：

```cpp
#include<stdio.h>
#include<stdlib.h>
int main()
{
  FILE *fp = fopen("C:\\myfile.txt", "w");

  if(fp == NULL)
  {
    printf("\n could not open file ");
    getchar();
    exit(1);
  }

  fprintf(fp, "%s", "Geeks for Geeks");

  /* ....... */
  /* ....... */
  /* Something went wrong so terminate here */  
  abort();

  getchar();
  return 0;  
}
```

如果我们想确保数据被写入文件和/或缓冲区被刷新，那么我们应该使用 `exit()` 或者为 `SIGABRT` 包含一个信号处理程序。

## assert()

```cpp
void assert( int expression );
```

如果表达式 `expression` 的计算结果为 `0` (`false`)，则将表达式、源代码文件名和行号发送到标准错误，然后调用 `abort()` 函数。如果用 `#define NDEBUG` 定义了标识符 `NDEBUG`（“无调试”），那么宏 `assert` 什么也不做。

常见的错误输出形式如下：

*`Assertion failed: expression, file filename, line number`*

```cpp
#include<assert.h>

void open_record(char *record_name)
{
    assert(record_name != NULL);
    /* Rest of code */
}

int main(void)
{
   open_record(NULL);
}
```

**相关文章：**
[exit() vs _exit() in C and C++](https://www.geeksforgeeks.org/exit-vs-_exit-c-cpp/)

本文由 **Rahul Gupta** 供稿。如果你在上面的文章中发现任何不正确的地方，或者你想分享更多关于上面讨论的主题的信息，请写评论。

**参考资料：**
[Exit Codes](http://www.tldp.org/LDP/abs/html/exitcodes.html)
[http://www.cplusplus.com/reference/clibrary/cstdlib/abort/](http://www.cplusplus.com/reference/clibrary/cstdlib/abort/)
[http://www.cplusplus.com/reference/clibrary/cassert/assert/](http://www.cplusplus.com/reference/clibrary/cassert/assert/)
[http://www.acm.uiuc.edu/webmonkeys/book/c_guide/2.1.html](http://www.acm.uiuc.edu/webmonkeys/book/c_guide/2.1.html)
[https://www.securecoding.cert.org/confluence/display/seccode/ERR06-C.+Understand+the+termination+behavior+of+assert%28%29+and+abort%28%29](https://www.securecoding.cert.org/confluence/display/seccode/ERR06-C.+Understand+the+termination+behavior+of+assert%28%29+and+abort%28%29)
[https://www.securecoding.cert.org/confluence/display/seccode/ERR04-C.+Choose+an+appropriate+termination+strategy](https://www.securecoding.cert.org/confluence/display/seccode/ERR04-C.+Choose+an+appropriate+termination+strategy)