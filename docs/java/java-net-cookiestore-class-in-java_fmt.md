# java 中的 java.net.CookieStore 类

> 原文: [https://www.geeksforgeeks.org/java-net-cookiestore-class-in-java/](https://www.geeksforgeeks.org/java-net-cookiestore-class-in-java/)

`CookieStore` 是 Java 中的一个接口，是一个存放 cookies 的区域。它用于存储和检索 cookies。`CookieStore` 负责删除过期的 `HttpCookie` 实例。

`CookieManager` 通过调用 `CookieStore.add()` 为每个传入的 HTTP 响应将 cookie 添加到 `CookieStore` 中，并通过调用 `CookieStore.get()` 为每个传出的 HTTP 请求从 `CookieStore` 中检索 cookie。

下表显示了 `CookieStore` 接口中的方法。

<figure class="table">

| 方法 | 执行的操作 |
| --- | --- |
| `add(URI uri, HttpCookie cookie)` | 向存储中添加一个 `HttpCookie`。 |
| `get(URI uri)` | 检索其域与 URI 匹配的 cookies。 |
| `getCookies()` | 获取 `CookieStore` 中所有未过期的 cookie。 |
| `getURIs()` | 获取 `CookieStore` 中识别 cookie 的所有 URI。 |
| `remove(URI uri, HttpCookie cookie)` | 从 `CookieStore` 中移除一个 cookie。 |
| `removeAll()` | 从 `CookieStore` 中移除所有 cookie。 |

</figure>

## 方法

### 方法 1: `add(URI uri, HttpCookie cookie)`

`add(URI uri, HttpCookie cookie)` 方法向存储中添加一个 `HttpCookie`。每个传入的 **HTTP 响应**都调用这个方法。如果对应于给定 URI 的 cookie 已经存在，它将被替换为新的 cookie。

#### 语法

```java
public void add(URI uri, HttpCookie cookie)
```

### 方法 2: `get(URI uri)`

`get(URI uri)` 方法检索其域与 URI 匹配的 cookies。每个传出的 **HTTP 请求**都调用这个方法。它返回一个未过期的不可变的 HTTP cookies 列表。如果没有与 URI 匹配的 cookie，它将返回一个空列表。如果参数 URI 被传递为空，那么它会抛出一个名为 `NullPointerException` 的异常。

#### 语法

```java
public List<HttpCookie> get(URI uri)
```

### 方法 3: `getCookies()`

`getCookies()` 方法从 `CookieStore` 中检索所有没有过期的 cookie。它返回一个不可变的 HTTP cookies 列表。如果 `CookieStore` 中没有 cookie，它将返回一个空列表。

#### 语法

```java
public List<HttpCookie> getCookies()
```

### 方法 4: `getURIs()`

`getURIs()` 方法检索所有在 `CookieStore` 中标识 cookies 的 URIs，并返回一个不可变的 URIs 列表。如果 `CookieStore` 中没有与 URI 相关联的 cookie，它将返回一个空列表。

#### 语法

```java
public List<URI> getURIs()
```

### 方法 5: `remove(URI uri, HttpCookie cookie)`

`remove(URI uri, HttpCookie cookie)` 方法删除 `CookieStore` 中的一个 cookie，该 cookie 的 URI 与给定的 cookie 相关联。如果添加时要删除的 cookie 与 URI 不相关，那么 URI 将作为空值传递。如果 cookie 作为空值传递，它将引发 `NullPointerException`。如果成功删除了 cookie，那么它将返回一个布尔值 `true`。

#### 语法

```java
public boolean remove(URI uri, HttpCookie cookie)
```

### 方法 6: `removeAll()`

`removeAll()` 方法会删除 `CookieStore` 中的所有 cookies。如果所有的 cookies 都被成功删除，那么它将返回一个布尔值 `true`。

#### 语法

```java
public boolean removeAll()
```

## 示例程序

```java
import java.io.*;
import java.net.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // CookieManager and CookieStore
        CookieManager cookieManager = new CookieManager();
        CookieStore cookieStore
            = cookieManager.getCookieStore();

        // creating cookies and URI
        HttpCookie cookieA = new HttpCookie("First", "1");
        HttpCookie cookieB = new HttpCookie("Second", "2");

        URI uri
            = URI.create("https://www.geeksforgeeks.org/");

        // Method 1 - add(URI uri, HttpCookie cookie)
        cookieStore.add(uri, cookieA);
        cookieStore.add(null, cookieB);
        System.out.println(
            "Cookies successfully added\n");

        // Method 2 - get(URI uri)
        List cookiesWithURI = cookieStore.get(uri);
        System.out.println(
            "Cookies associated with URI in CookieStore : "
            + cookiesWithURI + "\n");

        // Method 3 - getCookies()
        List cookieList = cookieStore.getCookies();
        System.out.println("Cookies in CookieStore : "
                           + cookieList + "\n");

        // Method 4 - getURIs()
        List uriList = cookieStore.getURIs();
        System.out.println("URIs in CookieStore" + uriList
                           + "\n");

        // Method 5 - remove(URI uri, HttpCookie cookie)
        System.out.println(
            "Removal of Cookie : "
            + cookieStore.remove(uri, cookieA));
        List remainingCookieList = cookieStore.getCookies();
        System.out.println(
            "Remaining Cookies : " + cookieList + "\n");

        // Method 6 - removeAll()
        System.out.println("Removal of all Cookies : "
                           + cookieStore.removeAll());
        List EmptyCookieList = cookieStore.getCookies();
        System.out.println(
            "Empty CookieStore : " + cookieList);
    }
}
```

**输出**

```java
Cookies successfully added

Cookies associated with URI in CookieStore : [First="1"]

Cookies in CookieStore : [First="1", Second="2"]

URIs in CookieStore[https://www.geeksforgeeks.org]

Removal of Cookie : true
Remaining Cookies : [Second="2"]

Removal of all Cookies : true
Empty CookieStore : []
```