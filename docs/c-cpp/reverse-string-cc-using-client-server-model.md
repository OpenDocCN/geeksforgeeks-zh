# 使用客户端服务器模型在 C/C++ 中反转字符串

> 原文:[https://www . geesforgeks . org/reverse-string-cc-use-client-server-model/](https://www.geeksforgeeks.org/reverse-string-cc-using-client-server-model/)

本文描述了一个客户机和服务器设置，其中客户机连接，向服务器发送一个字符串，服务器显示原始字符串，并使用套接字连接向客户机发送反向字符串。

**先决条件:** [插座编程](https://www.geeksforgeeks.org/socket-programming-cc/)

示例:

```cpp
Input : welcome
Output :emoclew

Input :geeks for geeks
Output :skeeg rof skeeg

```

**说明**
在此，首先设置客户端-服务器连接。当连接建立时，客户端将通过发送系统调用向服务器发送用户输入字符串。在服务器端，服务器将等待客户端发送的字符串。服务器通过读取系统调用读取字符串。在此之后，服务器将反转字符串并将其发送回客户端。

**编译:**
1。首先以如下方式运行服务器程序

```cpp
gcc Server.c -o server

```

2.在另一个终端上运行客户端程序

```cpp
gcc Client.c -o client

```

3.服务器程序正在等待客户端发送的字符串。
4。在客户端输入字符串。
5。服务器程序将打印原始字符串。
6。客户端程序将打印反向字符串。

**客户端**T2】

## C

```cpp
// C client code to send string to reverse
#include <arpa/inet.h>
#include <netinet/in.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <sys/socket.h>
#include <unistd.h>

#define PORT 8090

// Driver code
int main()
{
    struct sockaddr_in address;
    int sock = 0, valread;
    struct sockaddr_in serv_addr;
    char str[100];

    printf("\nInput the string:");
    scanf("%[^\n]s", str);

    char buffer[1024] = { 0 };

    // Creating socket file descriptor
    if ((sock = socket(AF_INET,
                       SOCK_STREAM, 0))
        < 0) {
        printf("\n Socket creation error \n");
        return -1;
    }

    memset(&serv_addr, '0', sizeof(serv_addr));
    serv_addr.sin_family = AF_INET;
    serv_addr.sin_port = htons(PORT);

    // Convert IPv4 and IPv6 addresses from
    // text to binary form 127.0.0.1 is local
    // host IP address, this address should be
    // your system local host IP address
    if (inet_pton(AF_INET, "127.0.0.1",
                  &serv_addr.sin_addr)
        <= 0) {
        printf("\nAddress not supported \n");
        return -1;
    }

    // connect the socket
    if (connect(sock, (struct sockaddr*)&serv_addr,
                sizeof(serv_addr))
        < 0) {
        printf("\nConnection Failed \n");
        return -1;
    }

    int l = strlen(str);

    // send string to server side
    send(sock, str, sizeof(str), 0);

    // read string sent by server
    valread = read(sock, str, l);

    printf("%s\n", str);

    return 0;
}
```

**服务器. c**T2】

## C

```cpp
// Server C code to reverse a
// string by sent from client
#include <netinet/in.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <sys/socket.h>
#include <unistd.h>

#define PORT 8090

// Driver code
int main()
{
    int server_fd, new_socket, valread;
    struct sockaddr_in address;
    char str[100];
    int addrlen = sizeof(address);
    char buffer[1024] = { 0 };
    char* hello = "Hello from server";

    // Creating socket file descriptor
    if ((server_fd = socket(AF_INET, 
                          SOCK_STREAM, 0)) == 0) {
        perror("socket failed");
        exit(EXIT_FAILURE);
    }

    address.sin_family = AF_INET;
    address.sin_addr.s_addr = INADDR_ANY;
    address.sin_port = htons(PORT);

    // Forcefully attaching socket to
    // the port 8090
    if (bind(server_fd, (struct sockaddr*)&address, 
                          sizeof(address)) < 0) {
        perror("bind failed");
        exit(EXIT_FAILURE);
    }

    // puts the server socket in passive mode
    if (listen(server_fd, 3) < 0) {
        perror("listen");
        exit(EXIT_FAILURE);
    }
    if ((new_socket = accept(server_fd,
                  (struct sockaddr*)&address,
                  (socklen_t*)&addrlen)) < 0) {
        perror("accept");
        exit(EXIT_FAILURE);
    }

    // read string send by client
    valread = read(new_socket, str,
                   sizeof(str));
    int i, j, temp;
    int l = strlen(str);

    printf("\nString sent by client:%s\n", str);

    // loop to reverse the string
    for (i = 0, j = l - 1; i < j; i++, j--) {
        temp = str[i];
        str[i] = str[j];
        str[j] = temp;
    }

    // send reversed string to client
    // by send system call
    send(new_socket, str, sizeof(str), 0);
    printf("\nModified string sent to client\n");

    return 0;
}
```