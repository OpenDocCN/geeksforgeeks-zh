# Java 中的 `java.net.CookiePolicy` 类

> 原文: [https://www.geeksforgeeks.org/java-net-cookiepolicy-class-in-java/](https://www.geeksforgeeks.org/java-net-cookiepolicy-class-in-java/)

`CookiePolicy` 实现决定哪些 cookies 应该被接受，哪些应该被拒绝。提供了三种预定义的策略实现，即 `ACCEPT_ALL`、`ACCEPT_NONE` 和 `ACCEPT_ORIGINAL_SERVER`。

## 签名

```java
public interface CookiePolicy
```

## 字段

| S.NO | 字段 | 描述 | 数据类型 |
| :--- | :--- | :--- | :--- |
| 1. | `ACCEPT_ALL` | `CookiePolicy.ACCEPT_ALL` 是一个接受所有 cookies 的预定义策略。 | 静态 `CookiePolicy` |
| 2. | `ACCEPT_ORIGINAL_SERVER` | `CookiePolicy.ACCEPT_ORIGINAL_SERVER` 是一个预定义的策略，它只接受来自原始服务器的 cookies。 | 静态 `CookiePolicy` |
| 3. | `ACCEPT_NONE` | `CookiePolicy.ACCEPT_NONE` 是一个预定义的策略，不接受任何 cookies。 | 静态 `CookiePolicy` |

## 方法

`CookiePolicy` 接口只包含一个名为 `shouldAccept(URI uri, HttpCookie cookie)` 的方法。

### `shouldAccept(URI uri, HttpCookie cookie)` 方法

**语法:**

```java
boolean shouldAccept(URI uri, HttpCookie cookie)
```

**方法参数:**

`shouldAccept()` 有两个 `URI` 和 `HttpCookie` 类型的参数。

**方法返回类型:**

`shouldAccept()` 具有 `boolean` 返回类型，如果 cookie 应该被接受将返回 `true`，否则将返回 `false`。

## 定义我们自己的 Cookie 策略

定义 Cookie 策略：

*   实现 `CookiePolicy` 接口。
*   定义 `CookiePolicy` 的 `shouldAccept` 方法并根据我们的需求进行编程。

## 示例

### 1. Java 程序设置 `cookieManager` cookie 策略以接受所有 cookie

```java
import java.net.*;
class GFG {
    public static void main(String[] args)
    {
        // create instance of cookieManager
        CookieManager cookieManager = new CookieManager();
        // set cookieManager cookie policy using
        // setCookiePolicy method
        cookieManager.setCookiePolicy(CookiePolicy.ACCEPT_ALL);
        System.out.println("Cookie Policy for cookieManager is set to : CookiePolicy.ACCEPT_ALL");
    }
}
```

**输出**

```
Cookie Policy for cookieManager is set to : CookiePolicy.ACCEPT_ALL
```

### 2. Java 程序将 `cookieManager` cookie 策略设置为不接受 cookie

```java
import java.net.*;
class GFG {
    public static void main(String[] args)
    {
        // create instance of cookieManager
        CookieManager cookieManager = new CookieManager();
        // set cookieManager cookie policy using
        // setCookiePolicy method
        cookieManager.setCookiePolicy(CookiePolicy.ACCEPT_NONE);
        System.out.println("Cookie Policy for cookieManager is set to : CookiePolicy.ACCEPT_NONE");
    }
}
```

**输出**

```
Cookie Policy for cookieManager is set to : CookiePolicy.ACCEPT_NONE
```

### 3. Java 程序设置 `cookieManager` cookie 策略，只接受来自原服务器的 cookie

```java
import java.net.*;
class GFG {
    public static void main(String[] args)
    {
        // create instance of cookieManager
        CookieManager cookieManager = new CookieManager();
        // set cookieManager cookie policy using
        // setCookiePolicy method
        cookieManager.setCookiePolicy(CookiePolicy.ACCEPT_ORIGINAL_SERVER);
        System.out.println("Cookie Policy for cookieManager is set to : CookiePolicy.ACCEPT_ORIGINAL_SERVER");
    }
}
```

**输出**

```
Cookie Policy for cookieManager is set to : CookiePolicy.ACCEPT_ORIGINAL_SERVER
```