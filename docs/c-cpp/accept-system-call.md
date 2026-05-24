# 接受系统调用

> 原文:[https://www.geeksforgeeks.org/accept-system-call/](https://www.geeksforgeeks.org/accept-system-call/)

**使用基于连接的套接字类型( **SOCK_STREAM，SOCK_SEQPACKET** )接受**()系统调用。它提取侦听套接字 sockfd 的挂起连接队列中的第一个连接请求，创建一个新的已连接套接字，并返回一个引用该套接字的新文件描述符。新创建的套接字不处于侦听状态。原始套接字 sockfd 不受此调用的影响。
**语法:**

```cpp
 int accept(int sockfd, struct sockaddr *addr, socklen_t *addrlen); 
```

*   **sockfd:** 参数 **sockfd** 是一个已经用 socket()创建的套接字，用 **bind** ()绑定到一个本地地址，并且在**侦听**()之后正在侦听连接。
*   **addr** :参数 **addr** 是指向 sockaddr 结构的指针。这个结构用对等套接字的地址来填充，这是通信层所知道的。返回地址的确切格式由套接字的地址族决定。当 addr 为空时，
    不填写任何内容；这种情况下，不使用 **addrlen** ，也应该为 NULL。
*   **addr len**:**addr len**参数是一个值-结果参数:调用者必须初始化它以包含 addr 指向的结构的大小(以字节为单位)；返回时，它将包含对等地址的实际大小。
*   **返回:**成功后，这些系统调用返回一个非负整数，它是接受的套接字的文件描述符。出错时，返回-1，适当设置**错误**。

如果提供的缓冲区太小，返回的地址将被截断；在这种情况下，addrlen 将返回一个大于提供给调用的值。
如果队列中没有未决连接，并且套接字没有标记为非阻塞，则**接受**()阻塞调用者，直到有连接为止。如果套接字被标记为非阻塞，并且队列中没有未决连接，则**接受**()失败，出现错误 **EAGAIN** 或 **EWOULDBLOCK** 。

```cpp
// C program to show accept system call is blocking call
#include <stdio.h>                                                                                                                                       
#include <sys/types.h>                                                                                                                                   
#include <sys/socket.h>                                                                                                                                  
#include <netinet/in.h>                                                                                                                                  
#include <string.h>                                                                                                                                      
#define BACKLOG 3                                                                                                                                            

// Driver program                                                                                                                                                            
int main()                                                                                                                                               
{                                                                                                                                                            
        struct sockaddr_in my_addr, peer_addr;                                                                                                               
        socklen_t peer_addr_size;                                                                                                                            
        int sd, b, l, acc;                                                                                                                                   
        my_addr.sin_family = AF_INET;

        // Creating socket                                                                                                                       
        sd = socket(AF_INET, SOCK_STREAM, 0); 

        // Binding                                                                                                               
        b = bind(sd, (struct sockaddr *)&my_addr, sizeof(struct sockaddr_in));                                                                               
        if(b > 0)                                                                                                                                            
                printf("Binded Successfully\n");                                                                                                             
        else                                                                                                                                                
                printf("Binding Error\n"); 
        // Listening                                                                                                                 
        l = listen(sd, BACKLOG);                                                                                                                             
        if(l > 0)                                                                                                                                            
                printf("Listening...\n");                                                                                                                    
        else                                                                                                                                                
                printf("Not listening..\n");                                                                                                                 
        peer_addr_size = sizeof(struct sockaddr_in); 

        // Accept system call                                                                                                    
        acc = accept(sd, (struct sockaddr *)&peer_addr, &peer_addr_size);                                                                                    
        if(acc > 0)                                                                                                                                      
                printf("Accepted\n");                                                                                                                        
        else                                                                                                                                                
                printf("Not accepted\n");                                                                                                                    
}                                           

```

输出:

```cpp
Binding Successfully
Listening.. 

```

**接受()呼叫的错误**

1.  **EAGAIN 或 EWOULDBLOCK :** 套接字被标记为非阻塞，不存在可接受的连接。对于这种情况，POSIX.1-2001 和 POSIX.1-2008 允许返回任何一个错误，并且不要求这些常量具有相同的值，因此可移植应用程序应该检查这两种可能性。
2.  **EBADF :** sockfd 不是打开的文件描述符。
3.  **经济报告:**连接已中止。
4.  **EFAULT:**addr 参数不在用户地址空间的可写部分。
5.  **EINTR :** 系统调用被有效连接到达前捕获的信号中断；参见信号(7)。
6.  **EINVAL :** Socket 没有侦听连接，或者 addrlen 无效(例如，为负数)。
7.  **EINVAL :** (accept4())标志中的值无效。
8.  **EMFILE :** 已达到每个进程打开文件描述符的数量限制。
9.  **ENFILE :** 已达到系统范围内打开文件总数的限制。
10.  **ENOBUFS，ENOMEM :** 空闲内存不够。这通常意味着内存
    的分配受到套接字缓冲区限制的限制，而不是系统内存。
11.  **ENOTSOCK :** 文件描述符 sockfd 没有引用套接字。
12.  **EOPNOTSUPP :** 引用的套接字不是 SOCK_STREAM 类型。
13.  **EPROTO:** 协议错误。

本文由**普拉莫德·库马尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。