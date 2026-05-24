# C/c++ 中的 Socket 编程:在没有多线程的情况下处理服务器上的多个客户端

> 原文:[https://www . geesforgeks . org/socket-programming-in-cc-handling-多客户端-服务器-无多线程/](https://www.geeksforgeeks.org/socket-programming-in-cc-handling-multiple-clients-on-server-without-multi-threading/)

本教程假设您具有套接字编程的基本知识，即您熟悉基本的服务器和客户端模型。在基本模型中，服务器一次只处理一个客户端，如果您想开发任何可扩展的服务器模型，这是一个很大的假设。
处理多个客户端的简单方法是为连接到服务器的每个新客户端生成新线程。由于各种缺点，强烈建议不要使用这种方法，即:

*   线程很难编码、调试，有时会有不可预测的结果。
*   上下文开销切换
*   对于大量客户端不可扩展
*   死锁可能会发生

**选择()**

处理多个客户端的更好方法是使用 **select()** linux 命令。

*   Select 命令允许监视多个文件描述符，等待其中一个文件描述符变为活动状态。
*   例如，如果有一些数据要在其中一个套接字上读取，select 将提供该信息。
*   **选择**就像一个中断处理程序，只要任何文件描述符发送任何数据，它就会被激活。

**用于选择的数据结构:** fd_set
它包含监控某些活动的文件描述符列表。
FD _ set 有四个功能:

```cpp
fd_set readfds;

// Clear an fd_set
FD_ZERO(&readfds);  

// Add a descriptor to an fd_set
FD_SET(master_sock, &readfds);   

// Remove a descriptor from an fd_set
FD_CLR(master_sock, &readfds); 

//If something happened on the master socket , then its an incoming connection  
FD_ISSET(master_sock, &readfds); 

```

**激活选择:**请阅读选择手册页，检查选择命令的所有参数。

```cpp
activity = select( max_fd + 1 , &readfds , NULL , NULL , NULL);
```

**实施:**

```cpp
//Example code: A simple server side code, which echos back the received message.
//Handle multiple socket connections with select and fd_set on Linux 
#include <stdio.h> 
#include <string.h>   //strlen 
#include <stdlib.h> 
#include <errno.h> 
#include <unistd.h>   //close 
#include <arpa/inet.h>    //close 
#include <sys/types.h> 
#include <sys/socket.h> 
#include <netinet/in.h> 
#include <sys/time.h> //FD_SET, FD_ISSET, FD_ZERO macros 

#define TRUE   1 
#define FALSE  0 
#define PORT 8888 

int main(int argc , char *argv[])  
{  
    int opt = TRUE;  
    int master_socket , addrlen , new_socket , client_socket[30] , 
          max_clients = 30 , activity, i , valread , sd;  
    int max_sd;  
    struct sockaddr_in address;  

    char buffer[1025];  //data buffer of 1K 

    //set of socket descriptors 
    fd_set readfds;  

    //a message 
    char *message = "ECHO Daemon v1.0 \r\n";  

    //initialise all client_socket[] to 0 so not checked 
    for (i = 0; i < max_clients; i++)  
    {  
        client_socket[i] = 0;  
    }  

    //create a master socket 
    if( (master_socket = socket(AF_INET , SOCK_STREAM , 0)) == 0)  
    {  
        perror("socket failed");  
        exit(EXIT_FAILURE);  
    }  

    //set master socket to allow multiple connections , 
    //this is just a good habit, it will work without this 
    if( setsockopt(master_socket, SOL_SOCKET, SO_REUSEADDR, (char *)&opt, 
          sizeof(opt)) < 0 )  
    {  
        perror("setsockopt");  
        exit(EXIT_FAILURE);  
    }  

    //type of socket created 
    address.sin_family = AF_INET;  
    address.sin_addr.s_addr = INADDR_ANY;  
    address.sin_port = htons( PORT );  

    //bind the socket to localhost port 8888 
    if (bind(master_socket, (struct sockaddr *)&address, sizeof(address))<0)  
    {  
        perror("bind failed");  
        exit(EXIT_FAILURE);  
    }  
    printf("Listener on port %d \n", PORT);  

    //try to specify maximum of 3 pending connections for the master socket 
    if (listen(master_socket, 3) < 0)  
    {  
        perror("listen");  
        exit(EXIT_FAILURE);  
    }  

    //accept the incoming connection 
    addrlen = sizeof(address);  
    puts("Waiting for connections ...");  

    while(TRUE)  
    {  
        //clear the socket set 
        FD_ZERO(&readfds);  

        //add master socket to set 
        FD_SET(master_socket, &readfds);  
        max_sd = master_socket;  

        //add child sockets to set 
        for ( i = 0 ; i < max_clients ; i++)  
        {  
            //socket descriptor 
            sd = client_socket[i];  

            //if valid socket descriptor then add to read list 
            if(sd > 0)  
                FD_SET( sd , &readfds);  

            //highest file descriptor number, need it for the select function 
            if(sd > max_sd)  
                max_sd = sd;  
        }  

        //wait for an activity on one of the sockets , timeout is NULL , 
        //so wait indefinitely 
        activity = select( max_sd + 1 , &readfds , NULL , NULL , NULL);  

        if ((activity < 0) && (errno!=EINTR))  
        {  
            printf("select error");  
        }  

        //If something happened on the master socket , 
        //then its an incoming connection 
        if (FD_ISSET(master_socket, &readfds))  
        {  
            if ((new_socket = accept(master_socket, 
                    (struct sockaddr *)&address, (socklen_t*)&addrlen))<0)  
            {  
                perror("accept");  
                exit(EXIT_FAILURE);  
            }  

            //inform user of socket number - used in send and receive commands 
            printf("New connection , socket fd is %d , ip is : %s , port : %d 
                  \n" , new_socket , inet_ntoa(address.sin_addr) , ntohs
                  (address.sin_port));  

            //send new connection greeting message 
            if( send(new_socket, message, strlen(message), 0) != strlen(message) )  
            {  
                perror("send");  
            }  

            puts("Welcome message sent successfully");  

            //add new socket to array of sockets 
            for (i = 0; i < max_clients; i++)  
            {  
                //if position is empty 
                if( client_socket[i] == 0 )  
                {  
                    client_socket[i] = new_socket;  
                    printf("Adding to list of sockets as %d\n" , i);  

                    break;  
                }  
            }  
        }  

        //else its some IO operation on some other socket
        for (i = 0; i < max_clients; i++)  
        {  
            sd = client_socket[i];  

            if (FD_ISSET( sd , &readfds))  
            {  
                //Check if it was for closing , and also read the 
                //incoming message 
                if ((valread = read( sd , buffer, 1024)) == 0)  
                {  
                    //Somebody disconnected , get his details and print 
                    getpeername(sd , (struct sockaddr*)&address , \
                        (socklen_t*)&addrlen);  
                    printf("Host disconnected , ip %s , port %d \n" , 
                          inet_ntoa(address.sin_addr) , ntohs(address.sin_port));  

                    //Close the socket and mark as 0 in list for reuse 
                    close( sd );  
                    client_socket[i] = 0;  
                }  

                //Echo back the message that came in 
                else 
                {  
                    //set the string terminating NULL byte on the end 
                    //of the data read 
                    buffer[valread] = '\0';  
                    send(sd , buffer , strlen(buffer) , 0 );  
                }  
            }  
        }  
    }  

    return 0;  
}  
```

编译文件并运行服务器。
使用 telnet 将服务器连接为客户端。

尝试使用以下命令在不同的计算机上运行:

```cpp
 telnet localhost 8888
```

**代码说明:**

*   我们已经创建了一个 fd_set 变量 readfds，它将监控客户端的所有活动文件描述符以及主服务器侦听套接字的描述符。
*   每当有新的客户端连接时，master_socket 就会被激活，并为该客户端打开一个新的 fd。我们将把它的 fd 存储在我们的 client_list 中，在下一个迭代中，我们将把它添加到 readfds 中，以监视来自这个客户端的活动。
*   Similarly, if an old client sends some data, readfds will be activated and we will check from the list of existing client to see which client has send the data.

    **替代品:** 还有其他功能可以执行类似选择的任务。选择，投票，投票

    本文由 **Akshat Sinha** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。