# 缓冲区溢出攻击示例

> 原文:[https://www . geeksforgeeks . org/buffer-overflow-attack-with-example/](https://www.geeksforgeeks.org/buffer-overflow-attack-with-example/)

一个**缓冲区**是数据存储的临时区域。当程序或系统进程放置了更多的数据(比最初分配存储的数据多)时，额外的数据就会溢出。它导致一些数据泄漏到其他缓冲区，这可能会破坏或覆盖他们持有的任何数据。
在**缓冲区溢出攻击中，**额外的数据有时包含黑客或恶意用户想要采取的行动的特定指令；例如，数据可能会触发一个响应，破坏文件、更改数据或泄露私人信息。
攻击者会利用缓冲区溢出漏洞利用正在等待用户输入的程序。缓冲区溢出有两种类型:基于堆栈的和基于堆的。基于堆的攻击很难执行，也是两种攻击中最不常见的，它通过淹没为程序保留的内存空间来攻击应用程序。基于堆栈的缓冲区溢出在攻击者中更常见，它通过使用所谓的堆栈(用于存储用户输入的内存空间)来利用应用程序和程序。
让我们研究一些真实的程序示例，这些示例显示了基于 c 的这种情况的危险。
在示例中，我们没有实现任何恶意代码注入，只是为了显示缓冲区可能溢出。现代编译器通常在编译/链接期间提供溢出检查选项，但是在运行期间，如果没有任何额外的保护机制(例如使用异常处理)，很难检查这个问题。

## C

```cpp
// A C program to demonstrate buffer overflow
#include <stdio.h>
#include <string.h>
#include <stdlib.h>

int main(int argc, char *argv[])
{

       // Reserve 5 byte of buffer plus the terminating NULL.
       // should allocate 8 bytes = 2 double words,
       // To overflow, need more than 8 bytes...
       char buffer[5];  // If more than 8 characters input
                        // by user, there will be access
                        // violation, segmentation fault

       // a prompt how to execute the program...
       if (argc < 2)
       {
              printf("strcpy() NOT executed....\n");
              printf("Syntax: %s <characters>\n", argv[0]);
              exit(0);
       }

       // copy the user input to mybuffer, without any
       // bound checking a secure version is srtcpy_s()
       strcpy(buffer, argv[1]);
       printf("buffer content= %s\n", buffer);

       // you may want to try strcpy_s()
       printf("strcpy() executed...\n");

       return 0;
}
```

**在 Linux 中编译该程序，并使用命令 output_file INPUT**
进行输出

```cpp
 Input  : 12345678 (8 bytes), the program run smoothly.
```

```cpp
 Input : 123456789 (9 bytes)
"Segmentation fault" message will be displayed and the program terminates.
```

该漏洞的存在是因为如果用户输入(argv[1])大于 8 字节，缓冲区可能会溢出。为什么是 8 字节？对于 32 位(4 字节)系统，我们必须填满一个双字(32 位)存储器。字符(char)大小是 1 字节，所以如果我们请求 5 字节的缓冲区，系统将分配 2 个双字(8 字节)。这就是为什么当你输入超过 8 个字节时；mybuffer 将被溢出
技术上不太脆弱的类似标准函数，如 strncpy()、strncat()和 memcpy()，确实存在。但是这些函数的问题在于，断言缓冲区的大小是程序员的责任，而不是编译器的责任。
每一个 C/C++ 编码人员或者程序员在做编码之前都必须知道缓冲区溢出的问题。在大多数情况下，由于缓冲区溢出，会产生许多漏洞。
**REFERENCES**
[维基百科](https://en.wikipedia.org/wiki/Buffer_overflow)
[buffer overflow](http://www.cse.scu.edu/~tschwarz/coen152_05/Lectures/BufferOverflow.html)
[c++ buffer overflow](http://www.tenouk.com/cncplusplusbufferoverflow.html)
本文由**阿卡什·莎兰**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。