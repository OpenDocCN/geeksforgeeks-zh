# c++ 中的 Web 编程

> 原文:[https://www.geeksforgeeks.org/web-programming-in-c/](https://www.geeksforgeeks.org/web-programming-in-c/)

**CGI(COMMON GATEWAY INTERFACE)**可以是一组标准，概述了数据如何从在线服务器更改，将在线用户的请求传递给护理应用程序中的关联，并将数据接收回用户。当任何用户请求一个网页时，服务器会发回所请求的页面。网络服务器通常将表单信息传递给一个处理数据的小应用程序，并可能发回一条确认消息。这种在服务器和应用程序之间来回传递知识的方法或惯例被称为公共中心接口(CGI)，是网络超文本传输协议(HTTP)的一个元素。

**公共入口接口(CGI)** 可以是一组在在线服务器上运行脚本和程序的规则。它指定了在线服务器和客户端网络浏览器之间的数据通信以及数据传输方式。大多数网络服务器在服务器上每个网站的根文件夹中都包含一个 **cgi-bin 目录**。放置在该目录中的任何脚本都应该遵循公共入口接口的原则。例如，位于 cgi-bin 目录中的脚本也被赋予了可行的权限，而目录之外的文件可能不被允许执行。一个 CGI 脚本可以另外请求 CGI 环境变量，如 SERVER_PROTOCOL 和 REMOTE_HOST，它们可以用作脚本的输入变量。

由于 CGI 可能是一个普通的接口，所以它将在多种硬件平台上使用，并得到多种网络服务器软件包的支持，如 Apache 和 Windows Server。CGI 脚本和程序也可以用许多完全不同的语言编写，例如 C++、Java 和 Perl。虽然一些网站仍然使用 CGI 来运行程序和脚本，但开发人员现在经常直接在网页中包含脚本。这些脚本，用 PHP 和 ASP 这样的语言编写的区域单元，在页面加载之前在服务器上处理的区域单元，以及随之而来的知识被发送到用户的浏览器。

**浏览网页**
为了了解 CGI 的思想，让我们来看一下用户使用特定地址在线浏览一件事情时发生的情况。

1.  您正在使用的浏览器会联系 HTTP 网络服务器并要求提供网址。
2.  网络服务器将解析该网址并搜索文件名；如果找到请求的文件，会立即将该文件发送回浏览器，否则会发送错误消息。
3.  网络浏览器接收来自网络服务器的响应，并显示收到的文件或错误消息。
4.  如果您正在开发一个网站，并且您需要一个 CGI 应用程序来控制，那么您可以在 URL(统一资源定位符)中指定应用程序的名称，您的代码在一个 HTML 文件中。

**服务器端配置**
在使用 CGI 编程之前，程序员应该确保 Web 服务器支持 CGI，并为处理 CGI 程序进行了良好的配置。按照惯例，CGI 文件的扩展名为。cgi，尽管它们是 C++ 可执行文件。默认情况下，Apache 网络服务器被配置为在中运行 CGI 程序

```cpp
/var/www/cgi-bin
```

程序员需要有一个网络服务器启动并运行，以便运行任何 CGI 程序，如 Perl、shell 等。

**使用 C++ 的 CGI 程序示例**

```cpp
// C++ example of CGI program

#include <iostream>
using namespace std;
int main()
{
    cout << "Content-type:text/html\r\n\r\n";
    cout << "<html>\n";
    cout << "<head>\n";
    cout << "<title>Hello TutorialsCloud </title>\n";
    cout << "</head>\n";
    cout << "<body>\n";
    cout << "<h3> <b> First CGI program </b> </h2>\n";
    cout << "</body>\n";
    cout << "</html>\n";
    return 0;
}
```

**Output:**

> 内容类型:文本/html
> 
> <title>Hello TutorialsCloud</title>
> 
> ### **第一个 CGI 程序**

*   编译上面的程序，给这个可执行文件一个合适的名字和扩展名**。cgi** 。
*   This file needs to be kept in

    ```cpp
    /var/www/cgi-bin directory
    ```

    它包含以下内容。

*   CGI 程序中经常使用的其他一些 HTTP 头有:
    1.  **内容类型**:定义返回文件格式的 MIME 字符串。
    2.  **过期:日期**:定义当前网页信息失效的日期。
    3.  **位置:网址**:必须返回的网址，而不是请求的网址。
    4.  **上次修改:日期**:资源上次修改的日期。
    5.  **内容长度:N** :返回数据的长度，以字节为单位。浏览器使用该值“N”来报告估计的下载时间。
    6.  **Set-Cookie:字符串**:用于设置通过字符串传递的 Cookie

**CGI 环境变量**

*   **CONTENT_LENGTH** :可选提供长度，以字节为单位。它仅适用于开机自检请求。
*   **CONTENT_TYPE** :可选提供内容的种类，即内容的数据类型。
*   **HTTP_COOKIE** :把访客的 COOKIE 拿回来，如果一个在键的类型内准备好了就试试。
*   **HTTP_USER_AGENT** :访问者的浏览器类型。它的请求头字段包含关于发起请求的用户代理的信息。
*   **PATH_INFO** :提供了 CGI 脚本的踪迹。
*   **REMOTE_ADDR** :访问者的科学地址，即创建请求的远程主机的科学地址。
*   **REMOTE_HOST** :访问者的主机名，即创建请求的主机的完全限定名