# 使用 C++ boost 的同步聊天应用::asio

> 原文:[https://www . geeksforgeeks . org/synchronic-chating-application-use-c-boostasio/](https://www.geeksforgeeks.org/synchronous-chatting-application-using-c-boostasio/)

[**Boost 库**](https://www.geeksforgeeks.org/advanced-c-boost-library/) 由 **asio** 组成，这是一个免费的跨平台 C++ 库，用于网络和低级 I/O 编程，使用现代 C++ 方法提供一致的异步模型。本文将帮助开发一个使用 boost::asio 的**客户端-服务器同步聊天应用程序。我们明确提到“同步”，因为在同步模型中，我们的一个客户机或服务器必须等待另一个。
**服务器端应用程序:**以下是创建服务器端应用程序的各个步骤:** 

*   导入 boost/asio.hpp(版本:1.65.1.0)

```cpp
#include <boost/asio.hpp>
```

*   正在创建 io_service 对象(用于服务器)，这是使用 boost::asio 所必需的。

```cpp
boost::asio::io_service io_service_object;
```

*   创建接受者的对象，传递 io_service 对象和连接端点，即 IPv4 和端口号 9999(在 boost::asio 中也支持 IPv6 协议，还要注意端口 0–1233 是保留的)。

```cpp
boost::asio::ip::tcp::acceptor 
  acceptor_object(
    io_service_object, 
    tcp::endpoint(boost::asio::ip::tcp::v4(), 
                  9999));
```

*   为我们的服务器创建 tcp::socket 对象。

```cpp
boost::asio::ip::tcp::socket socket_object(io_service_object) 
```

*   调用接受者对象的 accept 方法建立连接。

```cpp
acceptor_server.accept(server_socket);
```

*   read _ 直到()方法在通信过程中从存储数据的缓冲区获取消息。这里我们使用“\n”作为输出分隔符，这意味着我们将继续从缓冲区读取数据，直到遇到“\n”并存储它。

```cpp
// Create buffer for storing
boost::asio::streambuf buf;

boost::asio::read_until(socket, buf, "\n");
string data = boost::asio::buffer_cast(buf.data());
```

*   write()方法以套接字对象和消息为参数将数据写入缓冲区。

```cpp
boost::asio::write(
  socket, 
  boost::asio::buffer(message + "\n"));
```

**客户端应用程序:**以下是创建客户端应用程序的各个步骤:

*   导入 boost/asio . HPP

```cpp
#include <boost/asio.hpp>
```

*   正在为客户端创建 io_service 对象。

```cpp
boost::asio::io_service io_service_object;
```

*   正在为客户端创建 tcp::socket 对象。

```cpp
boost::asio::ip::tcp::socket
  socket_object(io_service_object) 
```

*   调用 socket 对象的 connect 方法，使用 localhost (IP 127.0.0.1)启动与服务器的连接，并连接到同一个端口 9999。

```cpp
client_socket.connect(
  tcp::endpoint(
    address::from_string("127.0.0.1"), 
    9999 ));
```

*   read _ 直到()和 write()对于我们的客户端应用程序以及服务器端都将保持不变。

下面是上述方法的实现:**程序:**

<gfg-tab role="tab" slot="tab" id="gfg-tab-0">server.cpp</gfg-tab><gfg-panel role="tabpanel" slot="panel" id="gfg-panel-0" data-code-lang="CPP"></gfg-panel>

```cpp
 // Server-side Synchronous Chatting Application
// using C++ boost::asio

#include <boost/asio.hpp>
#include <iostream>

using namespace std;
using namespace boost::asio;
using namespace boost::asio::ip;

// Driver program for receiving data from buffer
string getData(tcp::socket& socket)
{
    streambuf buf;
    read_until(socket, buf, "\n");
    string data = buffer_cast<const char*>(buf.data());
    return data;
}

// Driver program to send data
void sendData(tcp::socket& socket, const string& message)
{
    write(socket,
          buffer(message + "\n"));
}

int main(int argc, char* argv[])
{
    io_service io_service;

    // Listening for any new incomming connection
    // at port 9999 with IPv4 protocol
    tcp::acceptor acceptor_server(
        io_service,
        tcp::endpoint(tcp::v4(), 9999));

    // Creating socket object
    tcp::socket server_socket(io_service);

    // waiting for connection
    acceptor_server.accept(server_socket);

    // Reading username
    string u_name = getData(server_socket);
    // Removing "\n" from the username
    u_name.pop_back();

    // Replying with default message to initiate chat
    string response, reply;
    reply = "Hello " + u_name + "!";
    cout << "Server: " << reply << endl;
    sendData(server_socket, reply);

    while (true) {

        // Fetching response
        response = getData(server_socket);

        // Popping last character "\n"
        response.pop_back();

        // Validating if the connection has to be closed
        if (response == "exit") {
            cout << u_name << " left!" << endl;
            break;
        }
        cout << u_name << ": " << response << endl;

        // Reading new message from input stream
        cout << "Server"
             << ": ";
        getline(cin, reply);
        sendData(server_socket, reply);

        if (reply == "exit")
            break;
    }
    return 0;
} 
```

<gfg-tab role="tab" slot="tab" id="gfg-tab-1"><gfg-panel role="tabpanel" slot="panel" id="gfg-panel-1" data-code-lang="CPP"></gfg-panel></gfg-tab>

```cpp
 // Client-side Synchronous Chatting Application
// using C++ boost::asio

#include <boost/asio.hpp>
#include <iostream>
using namespace std;
using namespace boost::asio;
using namespace boost::asio::ip;

string getData(tcp::socket& socket)
{
    streambuf buf;
    read_until(socket, buf, "\n");
    string data = buffer_cast<const char*>(buf.data());
    return data;
}

void sendData(tcp::socket& socket, const string& message)
{
    write(socket,
          buffer(message + "\n"));
}

int main(int argc, char* argv[])
{
    io_service io_service;
    // socket creation
    ip::tcp::socket client_socket(io_service);

    client_socket
        .connect(
            tcp::endpoint(
                address::from_string("127.0.0.1"),
                9999));

    // Getting username from user
    cout << "Enter your name: ";
    string u_name, reply, response;
    getline(cin, u_name);

    // Sending username to another end
    // to initiate the conversation
    sendData(client_socket, u_name);

    // Infinite loop for chit-chat
    while (true) {

        // Fetching response
        response = getData(client_socket);

        // Popping last character "\n"
        response.pop_back();

        // Validating if the connection has to be closed
        if (response == "exit") {
            cout << "Connection terminated" << endl;
            break;
        }
        cout << "Server: " << response << endl;

        // Reading new message from input stream
        cout << u_name << ": ";
        getline(cin, reply);
        sendData(client_socket, reply);

        if (reply == "exit")
            break;
    }
    return 0;
} 
```