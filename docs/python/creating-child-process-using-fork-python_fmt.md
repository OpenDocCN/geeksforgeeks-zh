# 使用 Python 中的 `fork()` 创建子进程

> 原文: [https://www.geeksforgeeks.org/creating-child-process-using-fork-python/](https://www.geeksforgeeks.org/creating-child-process-using-fork-python/)

创建子进程并显示父进程和子进程的进程 id。

`Fork` 系统调用用于创建一个新的进程，称为 `子进程`，该进程与调用 `fork` 的进程（称为 `父进程`）并发运行。创建新的子进程后，两个进程都将执行 `fork()` 系统调用之后的下一条指令。

## 库使用

`os`：Python 中的 OS 模块提供了一种使用操作系统相关功能的方式。操作系统模块提供的功能允许您与运行 Python 的底层操作系统进行交互；无论是 Windows、macOS 还是 Linux。它可以被导入为：

```py
import os
```

## 使用的系统调用

*   `fork()`：`fork()` 是进程创建自身副本的操作。它通常是一个系统调用，在内核中实现。
*   `getpid()`：`getpid()` 返回调用进程的进程 ID (PID)。

下面是实现上述功能的 Python 程序：

```py
# Python code to create child process
import os

def parent_child():
    n = os.fork()

    # n greater than 0 means parent process
    if n > 0:
        print("Parent process and id is : ", os.getpid())

    # n equals to 0 means child process
    else:
        print("Child process and id is : ", os.getpid())

# Driver code
parent_child()
```

输出：

```py
Child process and id is :  32523
Parent process and id is :  32524
```

**注意：** 输出可以因时间、机器或进程调度而异。