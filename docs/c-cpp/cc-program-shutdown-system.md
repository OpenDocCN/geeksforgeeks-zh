# C/C++ 程序关闭系统

> 原文:[https://www.geeksforgeeks.org/cc-program-shutdown-system/](https://www.geeksforgeeks.org/cc-program-shutdown-system/)

如何在 Linux 和/或 Windows 中关闭计算机？

思路是在 C 中使用[系统()。该函数用于从 C 程序调用操作系统命令。](https://www.geeksforgeeks.org/system-call-in-c/)

**Linux OS:**

```cpp
// C program to shutdown in Linux
#include <stdio.h>
#include <stdlib.h>

int main()
{
   // Running Linux OS command using system
   system("shutdown -P now");

   return 0;
}
```

**Windows OS:**

**关闭/注销/重启一个 Windows 操作系统**

我们将从< stdlib.h >开始利用 system()在一个 C 程序的帮助下执行一个系统操作。要执行上述任何系统操作，我们将编码为:

```cpp
#include <stdio.h>
#include <stdlib.h>

int main()
{
  system("c:\\windows\\system32\\shutdown /i");
  return 0;
}
```

系统功能的论点是通往操作系统的路径，而 I/o 是我们可用的大量选项中的一个实体。要查看选项，我们运行 cmd 并键入:

```cpp
C:\Users\User>shutdown

```

关机命令为我们提供了一个选项列表。这些是:
![](img/3bb6824e7d2b9660540f85f363bd7e67.png)
要执行不同的操作，我们只需替换 system()参数中的最后一个“/path”。常见的操作有:

**关机**

```cpp
system("c:\\windows\\system32\\shutdown /s");
```

**重启**

```cpp
system("c:\\windows\\system32\\shutdown /r");
```

注销

```cpp
system("c:\\windows\\system32\\shutdown /l");
```

本文由**萨哈布拉****阿玛蒂亚·兰詹·赛基亚**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。