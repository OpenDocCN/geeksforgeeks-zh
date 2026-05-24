# 退出(0)与退出(1)在 C/C++ 中的对比示例

> 原文: [https://www.geeksforgeeks.org/exit0-vs-exit1-in-c-c-with-examples/](https://www.geeksforgeeks.org/exit0-vs-exit1-in-c-c-with-examples/)

`exit()` 是 C/C++ 语言中的跳转语句，取一个整数(零或非零)表示不同的退出状态。

C/C++ 中有两种退出状态:

## 1. 退出成功 (Exit Success)

**退出成功**由 `exit(0)` 语句表示，意味着程序的成功终止，即程序在没有任何错误或中断的情况下执行完毕。

```cpp
#include <file.h>
#include <stdio.h>

int main()
{
    FILE* file;

    // opening the file in read-only mode
    file = fopen("myFile.txt", "r");

    printf("File opening successful!");

    // EXIT_SUCCESS
    exit(0);
}
```

**注意:** 创建一个名为 `myFile.txt` 的文件，并在本地设备中运行代码以查看输出。

## 2. 退出失败 (Exit Failure)

**退出失败**由 `exit(1)` 表示，程序异常终止，即出现了一些错误或中断。我们可以使用 1 以外的不同整数来表示不同类型的错误。

```cpp
#include <file.h>
#include <stdio.h>

int main()
{
    FILE* file;

    // open the file in read-only mode
    file = fopen("myFile.txt", "r");

    if (file == NULL) {
        printf("Error in opening file");

        // EXIT_FAILURE
        exit(1);
    }

    // EXIT_SUCCESS
    exit(0);
}
```

## 对比总结

让我们看看这两种说法之间的区别：

| 特性 | `exit(0)` | `exit(1)` |
| :--- | :--- | :--- |
| **含义** | 报告程序的成功终止/完成。 | 报告程序异常终止。 |
| **触发条件** | 当程序执行无误时报告终止。 | 当程序执行过程中出现错误或中断时，报告终止。 |
| **语法** | 语法为 `exit(0);` | 语法为 `exit(1);` |
| **可移植性** | `exit(0)` 的用法是完全可移植的。 | `exit(1)` 的用法不可移植。 |
| **对应宏** | 用于返回代码 0 的宏是 `EXIT_SUCCESS` | 用于返回代码 1 的宏是 `EXIT_FAILURE` |
| **标准定义** | `EXIT_SUCCESS` 由标准定义为零。 | `EXIT_FAILURE` 并没有被标准限制为一个，但是很多系统确实实现为一个。 |