# 叉()弹

> 原文:[https://www.geeksforgeeks.org/fork-bomb/](https://www.geeksforgeeks.org/fork-bomb/)

先决条件: [fork() in C](https://www.geeksforgeeks.org/fork-system-call/)
Fork Bomb 是一个通过使系统耗尽内存来伤害系统的程序。它无限分叉进程来填充内存。分叉炸弹是一种针对基于 Linux 系统的拒绝服务(DoS)攻击。
一旦一个成功的分叉炸弹在系统中被激活，不重启系统就不可能恢复正常运行，因为分叉炸弹的唯一解决方案是销毁它的所有实例。

**叉弹的 C 程序**

## C

```cpp
// C program Sample  for FORK BOMB
// It is not recommended to run the program as
// it may make a system non-responsive.
#include <stdio.h>
#include <sys/types.h>

int main()
{
    while(1)
       fork();   
    return 0;
}
```

**叉形炸弹的重击脚本**

**注意**:请不要运行此命令来“测试”它，除非您准备好崩溃和/或强制重新启动系统。而且，它不需要 root 就能运行。
如果你使用的是终端，那么 bash 脚本为 fork() bomb 脚本如下。

```cpp
:(){ :|: & };:
```

**脚本分步说明:**

1.  **:()** 表示您正在定义一个名为:
2.  **{:|: & }** 表示运行函数:并将其输出再次发送到:函数并在后台运行。

4.  **；**命令分隔符
5.  **:** 第一次运行功能

本质上，您正在创建一个函数，该函数每次调用它自己两次，并且没有任何方法来终止它自己。它会一直翻倍，直到你用完系统资源。

**工作原理**

分叉炸弹通过在分叉过程中消耗 CPU 时间和饱和操作系统的进程表来运行。叉形炸弹的一个基本实现是一个无限循环，它重复地发射自己的新副本。
要使一个系统失效，他们依赖于一个假设，即在一台计算机上可以同时执行的程序和进程的数量。fork()将生成新的进程，但是如果您将这个进程放入 while true 循环中，那么它将创建许多进程，当超过限制时，您的系统将崩溃。

**防止叉()弹的方法**

*   避免在任何可能导致无限循环的语句中使用 fork。
*   你可以如下限制 fork 的进程:-
    只要以 root 身份登录，编辑这个文件，添加用户并配置，他们的限制。

```cpp
# vi /etc/security/limits.conf
```

将文件编辑为:

```cpp
 your_user_name hard nproc 10
```

*   如果您想运行该命令，可以尝试在 Virtualbox 中运行它。
*   直接关闭系统电源，以防运行后找不到继续运行的方法。

参考文献:

*   [维基百科](https://en.wikipedia.org/wiki/Fork_bomb)
*   [问乌班图](https://askubuntu.com/questions/159491/why-did-the-command-make-my-system-lag-so-badly-i-had-to-reboot)

本文由 **Dhavalkumar Prajapati** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。