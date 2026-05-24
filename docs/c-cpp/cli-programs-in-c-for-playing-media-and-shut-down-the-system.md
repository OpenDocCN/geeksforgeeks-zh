# C 中播放媒体的 CLI 程序，关闭系统

> 原文:[https://www . geesforgeks . org/CLI-programs-in-c-for-playing-media-然后关闭系统/](https://www.geeksforgeeks.org/cli-programs-in-c-for-playing-media-and-shut-down-the-system/)

[**命令行界面**](https://www.geeksforgeeks.org/linux-operating-system-cli-command-line-interface-and-gui-graphic-user-interface/)**:**

*   [CLI](https://www.geeksforgeeks.org/command-line-interface-programming-python/) **is a text-based user interface (UI) for viewing and managing computer files.**
***   Command line interface is also called command line user interface, console user interface and character user interface.*   In programming, the user gives input during the execution of the program, that is, during the running phase. However, there are many situations that need to be input before the program enters execution.*   To summarize, take the gasoline pump as an example:
    *   The supplier at the petrol pump enters the quantity in the machine, and then the machine gives the quantity of petrol accordingly.
    *   So this means that the machine is accepting this quantity as a parameter of a function, which in turn tells the machine how many liters of gasoline must be released.
    *   This is the real application of the command line parameter program. Parameters are required before the machine enters the execution stage (even before running).*   Before entering the program, an important aspect of running the [command line parameter](https://www.geeksforgeeks.org/command-line-arguments-in-c-cpp/) program is to give parameters through the command line.**

****如何运行？****

***   Make sure that only the program is saved and compiled after it is created.*   Compilation is very important (because only the compiled exe file will be updated).*   Don't run it because it should be run through the command line interface.*   So after saving, open the **command prompt** and navigate to the folder where the program is saved.*   After completing the path, write down the program name, followed by **EXE** .**

### **[**<u>关机</u>**](https://www.geeksforgeeks.org/cc-program-shutdown-system/) **:****

*   **在关机程序中，将生成一个命令行参数程序，该程序将采用一个时间参数，从而关闭计算机。**
*   **下面给出几个要点:

    *   [**sprintf**](https://www.geeksforgeeks.org/sprintf-in-c/) **库函数:**它将格式化的数据写入字符串，也就是说，它由一个字符串组成，该字符串的文本与如果在 **printf** 上使用该格式时将打印的文本相同，但是该内容不是被打印，而是作为一个 [C 字符串](https://www.geeksforgeeks.org/strings-in-c-2/)存储在由 str 指向的[缓冲区](https://www.geeksforgeeks.org/clearing-the-input-buffer-in-cc/)中。缓冲区的大小应该足够大，以包含整个结果字符串。它包含三个参数:
        *   **字符串:**指向存储结果字符串的缓冲区的指针。
        *   **格式:**包含格式字符串的 C 字符串，该格式字符串遵循与 [printf()](https://www.geeksforgeeks.org/puts-vs-printf-for-printing-a-string/) 中格式相同的规范
        *   **附加参数:**根据格式字符串，函数可能需要一系列附加参数，每个参数包含一个值，用于替换格式字符串中的格式说明符。** 
*   ****关机过程:**每当系统关机/休眠 PC 时，都会触发关机可执行文件。目录中文件的路径由**C:\ \ Windows \ \ System32 \ \关机**给出。**

**下面是关闭电脑的程序:**

## **C**

**T5**

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