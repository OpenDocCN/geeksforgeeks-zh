# java 中的 java.net.URL 类

> 原文: [https://www.geeksforgeeks.org/java-net-url-class-in-java/](https://www.geeksforgeeks.org/java-net-url-class-in-java/)

网址是统一资源定位器的缩写。它是定位 *www* (万维网)中资源的指针。资源可以是任何东西，从一个简单的文本文件到任何其他像图像，文件目录等。

典型的网址可能如下所示

```java
http://www.example.com:80/index.html
```

该网址有以下几个部分:

*   协议:在这种情况下，协议是 HTTP，在某些情况下可以是 HTTPS
*   主机名:主机名代表资源所在机器的地址，在本例中为`www.example.com`
*   端口号:这是一个可选属性。如果未指定，则返回-1。在上面的例子中，端口号是 80。
*   资源名称:它是位于给定服务器上的我们想要查看的资源的名称

你可以在这里了解更多网址[。](https://www.geeksforgeeks.org/url-full-form/)

网址的类结构如下所示:

```java
public final class java.net.URL extends java.lang.Object
```

以下是网址类提供的构造函数。

| 构造函数 | 解释 |
| --- | --- |
| `URL(URL context, String spec)` | This constructor is derived from the given string representation. |
| `URL(String protocol, String host, int port, String file)` | This constructor creates an object of URL from the specified protocol, host, port number and file. |
| `URL(String protocol, String host, String file)` | This constructor creates an object of URL from the specified protocol, port number and file. In this case, the default port number is used. |
| `URL(URL context, String spec, URLStreamHandler handler)` | This constructor creates an instance of the URL by parsing the given src using the specified handler in the given context. |

URL 类提供的方法:

| 方法 | 解释 |
| --- | --- |
| `equals(Object obj)` | This method compares this URL with another object equally. |
| [`getAuthority()`](https://www.geeksforgeeks.org/url-getauthority-method-in-java-with-examples/) | This method gets the permission part of this URL. |
| `getContent()` | This method gets the contents of this URL. |
| `getContent(Class[] classes)` | This method gets the contents of this URL. |
| [`getDefaultPort()`](https://www.geeksforgeeks.org/url-getdefaultport-method-in-java-with-examples/) | This method gets the default port number of the protocol associated with this URL. |
| `getFile()` | This method gets the file name of this URL. |
| `getHost()` | This method gets the host name of this URL, if applicable. |
| [`getPath()`](https://www.geeksforgeeks.org/url-getpath-method-in-java-with-examples/) | This method gets the path part of this URL. |
| [`getPort()`](https://www.geeksforgeeks.org/url-getport-method-in-java-with-examples/) | This method gets the port number of this URL. |
| [`getProtocol()`](https://www.geeksforgeeks.org/url-getprotocol-method-in-java-with-examples/) | This method gets the protocol name of this URL. |
| [`getQuery()`](https://www.geeksforgeeks.org/url-getquery-method-in-java-with-examples/) | This method gets the query part of this URL. |
| [`getRef()`](https://www.geeksforgeeks.org/url-getref-method-in-java-with-examples/) | This method gets the anchor point (also known as "reference") of this URL. |
| [`getUserInfo()`](https://www.geeksforgeeks.org/url-getuserinfo-method-in-java-with-examples/) | This method gets the UserInfo part of this URL. |
| `hashCode()` | This method creates an integer suitable for hash table index. |
| `openConnection()` | This method returns a `URLConnection` instance that represents the connection to the remote object referenced by the URL. |
| `openConnection(Proxy proxy)` | Same as `openConnection()`, except that the connection will be made through the specified proxy; Protocol handlers that do not support proxy will ignore proxy parameters and establish normal connection. |
| `openStream()` | This method opens a connection to this URL and returns an `InputStream` to read from the connection. |
| [`sameFile(URL other)`](https://www.geeksforgeeks.org/url-samefile-method-in-java-with-examples/) | This method compares two URLs, excluding fragment components. |
| `set(String protocol, String host, int port, String file, String ref)` | This method sets the fields of the URL. |
| `set(String protocol, String host, int port, String authority, String userInfo, String path, String query, String ref)` | This method sets the specified 8 fields of the URL. |
| `setURLStreamHandlerFactory(URLStreamHandlerFactory fac)` | This method sets the `URLStreamHandlerFactory` of the application. |
| [`toExternalForm()`](https://www.geeksforgeeks.org/url-toexternalform-method-in-java-with-examples/) | This method constructs the string representation of this URL. |
| `toString()` | This method constructs a string representation of this URL. |
| [`toURI()`](https://www.geeksforgeeks.org/url-touri-method-in-java-with-examples/) | This method returns a `URI` equivalent to this URL. |

## 示例 1

在本演示中，我们将为给定的字符串网址创建一个 `URL` 类对象，并为给定的网址打印主机名、协议、文件名和端口号。

### Java 代码

```java
// importing package required
import java.net.URL;
import java.util.Scanner;

class GFG {
    public static void main(String[] args)
    {
        String url
            = "https://www.geeksforgeeks.org/variables-in-java/";
        // Calling method to get URL info
        getUrlInfo(url);
    }
    static void getUrlInfo(String url_string)
    {
        // Creating object of URL class
        try {
            URL url = new URL(url_string);

            System.out.println("Hostname: "
                               + url.getHost());
            System.out.println("Port Number: "
                               + url.getPort());
            System.out.println("File name: "
                               + url.getFile());
            System.out.println("Protocol:  "
                               + url.getProtocol());
        }
        catch (Exception e) {
        }
    }
}
```

**输出**

```java
Hostname: www.geeksforgeeks.org
Port Number: -1
File name: /variables-in-java/
Protocol:  https
```