# C 中播放媒体的 CLI 程序，关闭系统

> 原文: [https://www.geeksforgeeks.org/cli-programs-in-c-for-playing-media-and-shut-down-the-system/](https://www.geeksforgeeks.org/cli-programs-in-c-for-playing-media-and-shut-down-the-system/)

## 命令行界面

`CLI` 是一种用于查看和管理计算机文件的基于文本的用户界面（UI）。

命令行界面也称为命令行用户界面、控制台用户界面和字符用户界面。

在编程中，用户在程序执行期间（即在运行阶段）提供输入。然而，有许多情况需要在程序进入执行阶段之前输入。

总结一下，以汽油泵为例：
*   汽油泵的供应商在机器中输入数量，然后机器相应地给出汽油量。
*   这意味着机器将此数量作为函数的参数接受，该参数告诉机器必须释放多少升汽油。
*   这是命令行参数程序的实际应用。参数在机器进入执行阶段之前（甚至在运行之前）就是必需的。

运行命令行参数程序的一个重要方面是在进入程序之前通过命令行提供参数。

### 如何运行？

*   确保程序在创建后仅保存并编译。
*   编译非常重要（因为只有编译后的 exe 文件才会被更新）。
*   不要运行它，因为它应该通过命令行界面运行。
*   因此，保存后，打开 **命令提示符** 并导航到保存程序的文件夹。
*   完成路径后，写下程序名称，后跟 **EXE**。

### 关机

*   在关机程序中，将生成一个命令行参数程序，该程序将采用一个时间参数，从而关闭计算机。
*   下面给出几个要点：
    *   `sprintf` 库函数：它将格式化的数据写入字符串，也就是说，它由一个字符串组成，该字符串的文本与如果在 `printf` 上使用该格式时将打印的文本相同，但是该内容不是被打印，而是作为一个 C 字符串存储在由 `str` 指向的缓冲区中。缓冲区的大小应该足够大，以包含整个结果字符串。它包含三个参数：
        *   `字符串`：指向存储结果字符串的缓冲区的指针。
        *   `格式`：包含格式字符串的 C 字符串，该格式字符串遵循与 `printf()` 中格式相同的规范。
        *   `附加参数`：根据格式字符串，函数可能需要一系列附加参数，每个参数包含一个值，用于替换格式字符串中的格式说明符。
    *   关机过程：每当系统关机/休眠 PC 时，都会触发关机可执行文件。目录中文件的路径由 `C:\Windows\System32\shutdown` 给出。

下面是关闭电脑的程序：

```cpp
// C program to shut down the computer
#include <stdio.h>
#include <stdlib.h>

// Driver Code

int main(int argc, char* argv[])
{
    char buf[32];
    int time;

// Function converting to integer
    val = atoi(argv[1]);
    sprintf(buf, "C:\\Windows\\System32\\shutdown /s /t %d", time);

// System function to run CLI commands
    system(buf);

// Confirming that program is
    // running properly
    printf("Running successfully. "
           "Shutting down in %d sec",
           time);

return 0;
}
```