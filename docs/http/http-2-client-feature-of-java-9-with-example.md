# Java 9 的 HTTP/2 客户端功能，示例

> 原文:[https://www . geesforgeks . org/http-2-client-feature-of-Java-9-with-example/](https://www.geeksforgeeks.org/http-2-client-feature-of-java-9-with-example/)

**HTTP/2 客户端:** HTTP/2 客户端是 [JDK 9](https://www.geeksforgeeks.org/java-9-features-with-examples/) 的特色之一。HTTP/2 是最新版本的 [HTTP 协议](https://www.geeksforgeeks.org/http-non-persistent-persistent-connection/)。借助 HTTP/2 客户端，从 Java 应用程序中，我们可以发送 HTTP 请求并处理 HTTP 响应。在 JDK 9 之前，为了发送 HTTP 请求和处理 HTTP 响应，我们使用[HTTP 连接](https://www.geeksforgeeks.org/java-net-httpurlconnection-class-java/)类。现在你会想为什么 JDK 9 引入了 HTTP/2 客户端，而我们有【HTTP 连接来解决目的。但是现有的 HTTP 连接几乎没有在 HTTP/2 客户端中消除的问题。

【HttpURLConnection 的几个主要问题:

1.  HttpURLConnection 类只支持 **HTTP/1.1 协议**，不支持 HTTP/2.0 协议。协议只不过是在电子设备(如计算机)之间传输数据的一套规则或程序。HTTP 代表超文本传输协议，这里的协议代表用于建立客户机和服务器之间通信的数据通信协议。由于 HTTP 连接类只支持 HTTP/1.1，这就是为什么如果我们使用 HTTP 连接类，那么每个 TCP 连接只能发送一个请求。这将导致应用程序的网络流量和性能问题。由于 HTTP 连接只支持 HTTP/1.1，所以只能处理**文本数据，不能处理二进制数据**。
2.  HttpURLConnection 类只在**同步模式**下工作。同步模式意味着在发送另一个请求之前，我们必须等待请求完成其任务。如果我们使用 HttpURLConnection 类来处理 HTTP 请求，那么我们必须闲置，直到我们得到请求的响应，然后我们可以处理另一个 HTTP 请求，这将导致性能问题。

**HTTP/2.0 客户端的优势:**

1.  HTTP/2.0 客户端非常轻量级且易于使用。HTTP/2.0 客户端同时支持 **HTTP/1.1 和 HTTP/2.0** 。HTTP/2 关注的是数据是如何在服务器和客户端之间构建和传输的。在 HTTP/1.1 中，我们一次打开的连接不能超过六个，所以每个请求都必须等待其他请求完成。上述问题的解决方案是在 HTTP/2 客户端进行复用。这意味着借助 HTTP/2 可以通过单个 TCP 连接并行发送多个 HTTP 请求。
2.  在 HTTP/1.1 中，当我们发送一个包含报头信息的 HTTP 请求时，HTTP/1.1 将报头数据视为附加数据，这增加了带宽。这可以在 HTTP/2.0 中通过使用 **HPack** 进行头部压缩来消除。
3.  HTTP/2.0 客户端同时支持**文本和二进制数据**进行处理。
4.  HTTP/2.0 客户端在**同步和异步模式下工作。**。与 HTTP 连接相比，HTTP/2.0 客户端的性能要好得多。

**Java 9 中的 HTTP API:**在 Java 9 中引入了一个新的 API，该 API 易于使用，并且还增加了对 HTTP/2 的支持。引入了 3 个新的类来处理 HTTP 通信。这三个类存在于模块内的 **jdk .孵化器. httpclient** 和 **jdk .孵化器. http** 包中。由于 jdk .孵化器. httpclient 不在 java 应用程序中，我们必须在 module-info.java 文件中显式导入它。

1.  **HttpClient:** HttpClient 是多个 HttpRequests 共有的配置信息的容器。所有请求都是通过 HttpClient 发送的。HttpClients 是不可变的，并且是从 newBuilder()返回的生成器创建的。请求生成器是通过调用 HttpRequest.newBuilder()创建的。
2.  **HttpRequest:** HttpRequest 代表一个可以发送到服务器的 HTTP 请求。HTTP 请求是由 HttpRequest 构建器构建的。HttpRequest 构建器是通过调用 HttpRequest.newBuilder 获得的。可以设置请求的 URI、头和主体。请求主体是通过 HttpRequest 提供的。提供给删除、开机自检或放入方法的身体处理器对象。GET 不需要身体。一旦在构建器中设置了所有必需的参数。调用 Builder.build()返回 HttpRequest。
3.  **HttpResponse:** 收到响应状态代码和标头时，通常在也收到响应正文后，可以使用 HttpResponse。

**示例:**

**HTTP/2.0 的虚拟项目:**由于我们已经知道在 Java 9 中不能直接使用内部 API，所以我们必须在模块描述符文件中创建一个条目。这里使用 **jdk .孵化器. httpclient** 模块中的新的 HTTP API。我们必须在模块描述文件中提到它。我们必须按照以下步骤在 Java 9 上使用 HTTP/2 执行操作:-

*   首先创建一个名为 src 的文件夹，即我们的 java 程序的源文件夹，并在其中创建一个名为 geeks 的文件夹，它将包含元数据信息，并在 geeks 中再创建一个名为 httpPackage 的文件夹，它只是我们将放置 java 代码的包的名称。
*   直接在极客内部创建 module-info.java，如下所示:

    ```htmlhtml
    module geeks
    {
        requires jdk.incubator.httpclient;
    }
    ```

*   在名为 Geeksforgeeks.java 的 httpPackage 文件夹中创建 java 类，实现如下:

    ```htmlhtml
    package httpPackage;
    import java.io.IOException;
    import java.net.URI;
    import jdk.incubator.http.HttpClient;
    import jdk.incubator.http.HttpRequest;
    import jdk.incubator.http.HttpResponse;

    public class Geeksforgeeks {
        public static void main(String[] args)
        {
            try {
                // Create a HttpClient
                HttpClient httpClient
                    = HttpClient.newHttpClient();

                // create a HttpRequest object with the URL
                HttpRequest httpRequest
                    = HttpRequest
                          .newBuilder()
                          .uri(new URI("https:// www.geeksforgeeks.org/about/"))
                          .GET()
                          .build();
                // Synchronous send() method
                // to process the HTTP request.
                // HttpResponse.BodyHandler.asString() handles
                // the body of the response as a String.
                HttpResponse<String> httpResponse
                    = httpClient.send(
                        httpRequest,
                        HttpResponse.BodyHandler.asString());

                // statusCode() returns the status code
                // for this response.
                System.out.println(
                    "Status of operation performed:"
                    + httpResponse.statusCode());
            }
            catch (Exception e) {
                System.out.println("Exception" + e);
            }
        }
    }
    ```

*   为了编译我们的 java 代码，我们必须转到 src 文件夹并执行下面的命令:

    ```htmlhtml
    javac --module-source-path src-d-out -m geeks
    ```

*   To run our java code, we have to execute below command:

    ```htmlhtml
    java --module-path out -m geeks/httpPackage.Geeksforgeeks
    ```

    **输出:**

    ```htmlhtml
    WARNING: using incubator modules jdk.incubator.httpclient
    Status of operation performed:200

    ```

*   From the above program, we can send one HTTP GET request through synchronous send() method and handle the response as String. Suppose we don’t want to wait until the completion of the HTTP request and want to send another HTTP request in parallel and also we want to save the response into one file. In the above example, we are using the synchronous feature which will block until it has completed. We can make it asynchronous as well as we can save the response into the file.

    ```htmlhtml
    import java.nio.file.Paths;
    import java.io.IOException;
    import java.net.URI;
    import jdk.incubator.http.HttpClient;
    import jdk.incubator.http.HttpRequest;
    import jdk.incubator.http.HttpResponse;

    public class Geeksforgeeks {
        public static void main(String[] args)
        {
            try {
                // Create a HttpClient
                HttpClient httpClient
                    = HttpClient.newHttpClient();

                // create a HttpRequest object with the URL
                HttpRequest httpRequest
                    = HttpRequest
                          .newBuilder()
                          .uri(new URI("https:// www.geeksforgeeks.org/about/"))
                          .GET()
                          .build();

                // Synchronous send() method
                // to process the HTTP request.
                // HttpResponse.BodyHandler.asFile(Paths.get("GFG.html"))
                // save the response body into GFG.html file
                HttpResponse<String> httpResponse
                    = httpClient.send(
                        httpRequest,
                        HttpResponse.BodyHandler.asFile(Paths.get("GFG.html")));

                // statusCode() returns the status code for this response.
                System.out.println(
                    "Status of operation performed:"
                    + httpResponse.statusCode());

                // body() returns the response of HTTP request
                System.out.println("Response body:"
                                   + httpResponse.body());
            }
            catch (Exception e) {
                System.out.println("Exception" + e);
            }
        }
    }
    ```

    **输出:**

    ```htmlhtml
    WARNING: using incubator modules jdk.incubator.httpclient
    Status of operation performed:200
    Response body: It will return the source code of https://www.geeksforgeeks.org/about/ page. As the response is too big i am not adding in it here.

    ```