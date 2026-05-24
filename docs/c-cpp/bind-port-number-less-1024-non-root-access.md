# 非根访问如何绑定到小于 1024 的端口号？

> 原文:[https://www . geesforgeks . org/bind-端口号-less-1024-非根访问/](https://www.geeksforgeeks.org/bind-port-number-less-1024-non-root-access/)

**为什么前 1024 个端口仅限根用户？**

**绑定**是服务器端套接字不可或缺的一步。这就像给最终用户(服务器)提供一些地址。因此，我们为运行服务器分配了一个 IP 地址和一个端口号。但是我们不能向服务器提供任何随机端口号。端口号**从 1 到 1023** 仅限于根用户，我们不能在没有根用户访问权限的情况下分配这些端口。

这种限制背后的原因是大多数主要的网络服务，如 HTTP、FTP、SSH、Telnet、POP 等。在这个范围内运行。因此，如果允许任何一个在这些端口上运行，可能会出现以下情况:

*   不受信任的用户可以运行一个在这些端口上监听登录(访问)详细信息的程序。
*   不受信任的用户可以运行未经授权的服务器应用程序。

下面的程序验证了从 1 到 1023 的端口号被限制为根访问的事实。

我们使用 [bind()函数](http://man7.org/linux/man-pages/man2/bind.2.html)，成功时返回 0，失败时返回-1。我们在循环中为不同的端口号调用 bind，直到它返回 0。

```cpp
// Server side C program to demonstrate
// that we can not assign port number less
// than 1024 without root access
#include<stdio.h>
#include<arpa/inet.h>

int main()
{
    int server = socket(AF_INET, SOCK_STREAM, 0);
    if (server < 0)
        printf("Error in server creating\n");
    else
        printf("Server Created\n");

    struct sockaddr_in my_addr, peer_addr;
    my_addr.sin_family = AF_INET;
    my_addr.sin_addr.s_addr = INADDR_ANY;
    my_addr.sin_addr.s_addr = inet_addr("10.32.40.213");
    int b = 1, i = 0;
    while (b)
    {
        i++ ;

        // Assigning every port number starting
        // from one to check
        // if it is able to bind properly or not
        my_addr.sin_port = htons(i);

        // On correct binding, it return 0
        // and so 0 in b will terminate loop
        b = bind(server, (struct sockaddr*) &my_addr,
                                    sizeof(my_addr));
    }
    printf("Binded Correctly on port number %d\n", i);
}
```

输出:

```cpp
Server Created
Binded Correctly on port number 1024

```

**如何允许非根访问绑定端口号 1024 以下？**

但是有两种方法可以在没有 root 权限情况下分配小于 1024 的端口号:

1.  **方法 1** :使用**[CAP _ NET _ BIND _ SERVICE](http://man7.org/linux/man-pages/man7/capabilities.7.html)**授予进程的低编号端口访问权限:
    为此，我们只需要在终端运行以下命令:

    ```cpp
    sudo setcap CAP_NET_BIND_SERVICE=+eip /path/to/binary
    ```

2.  **方法二**:使用 **[authbind](https://en.wikipedia.org/wiki/Authbind)** 授予一次性访问权限，用户/组/端口控制更精细。让我们分配端口号 80。为此，需要以下步骤:
    *   使用任何包管理器安装 authbind
    *   Run following two commands one by one in terminal :

        ```cpp
        sudo touch /etc/authbind/byport/80
        sudo chmod 777 /etc/authbind/byport/80
        ```

        在这里， **80** 在命令结束时给出，因为我们试图分配端口号 80。

    *   现在在终端

        ```cpp
        authbind --deep /path/to/binary command line args
        ```

        执行以下命令

本文由[阿迪蒂亚·库马尔](https://www.linkedin.com/in/aditya-kumar-837315100/)供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。