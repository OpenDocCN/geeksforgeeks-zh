# java.net.CookieHandler 类

> 原文: [https://www.geeksforgeeks.org/java-net-cookiehandler-class-in-java/](https://www.geeksforgeeks.org/java-net-cookiehandler-class-in-java/)

Java 中 `CookieHandler` 类的对象提供了一种回调机制，用于将 HTTP 状态管理策略实现挂接到 HTTP 协议处理程序中。如何发出 HTTP 请求和响应的机制由 HTTP 状态管理机制指定。

HTTP 协议处理程序也使用的系统范围的 `CookieHandler` 通常通过执行 `CookieHandler.setDefault(CookieHandler)` 来注册。当前注册的 `CookieHandler` 通常通过调用 `CookieHandler.getDefault()` 来检索。

**声明:**

```java
public abstract class CookieHandler
extends Object
```

**构造方法:**

```java
CookieHandler();
```

## 示例

```java
// Java program to demonstrate the usage
// of CookieHandler Class

import java.net.CookieHandler;
import java.net.CookieManager;
import java.net.CookieStore;
import java.net.HttpCookie;
import java.net.URL;
import java.net.URLConnection;
import java.util.List;
public class JavaCookieHandlerExample1 {
    public static void main(String args[]) throws Exception
    {
        String uri = "https://www.google.com";

        // Instantiate CookieManager;
        CookieManager c = new CookieManager();

        // First set the default cookie manager.
        CookieHandler.setDefault(c);
        URL url = new URL(uri);

        // All the following subsequent URLConnections
        // will use the same cookie manager.
        URLConnection connection = url.openConnection();
        connection.getContent();

        // Get cookies from underlying CookieStore
        CookieStore cookieStore = c.getCookieStore();

        List<HttpCookie> cookieList
            = cookieStore.getCookies();

        for (HttpCookie cookie : cookieList) {
            // Get domain set for the cookie
            System.out.println("The domain is: "
                               + cookie.getDomain());
        }
    }
}
```

**输出:**

```java
The domain is: .google.com
```

`CookieHandler` 类在 Java 中提供了以下方法:

| 方法 | 描述 |
| --- | --- |
| `get(URI uri, Map<String, List<String>> requestHeaders)` | 此方法从 Cookie 缓存中获取请求中指定 URI 的所有适用 Cookie。 |
| `getDefault()` | 此方法获取系统范围的 Cookie 处理程序。 |
| `put(URI uri, Map<String, List<String>> responseHeaders)` | 此方法设置所有适用的 Cookie，例如响应头中名为 Set-Cookie2 的响应头字段，该字段呈现给响应头中的 Cookie 缓存。 |
| `setDefault(CookieHandler chandler)` | 此方法设置或取消设置系统范围的 Cookie 处理程序。 |