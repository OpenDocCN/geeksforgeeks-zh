# 在 Windows 系统默认浏览器中打开输入 URL 的 Java 程序

> 原文：[https://www.geeksforgeeks.org/java-program-to-open-input-url-in-system-default-browser-in-windows/](https://www.geeksforgeeks.org/java-program-to-open-input-url-in-system-default-browser-in-windows/)

**网址** 是你想在默认网页浏览器中显示的网址。例如，将 `http://www.site.com/report.html` 连线到这个输入，在浏览器的网络服务器 `www.site.com` 上显示 HTML 文件 `report.html`。

我们的问题是编写一个 Java 程序，在 Windows 的系统默认浏览器中打开输入 URL。

为了打开任何网址，我们使用不同的 Java 预定义文件来操作我们的桌面。

1.  [`java.awt.Desktop`](https://www.geeksforgeeks.org/java-awt-desktop-class/)：我们使用 `java.awt.Desktop` 类，因为它允许我们与桌面的不同功能进行交互。例如，启动用户的默认浏览器，启动用户的默认邮件客户端等。
2.  [`java.net.URI`](https://www.geeksforgeeks.org/java-net-uri-class-java/)：`java.net.URI` 用于表示用户资源标识符的引用。

## 算法

首先，我们创建定义类的对象，并通过 `java.awt.Desktop` 导入它。

在创建对象的过程中，我们使用 `getDesktop()` 方法来返回当前桌面上下文的桌面实例。Desktop API 可能在某些平台上不受支持。在这种情况下，我们使用 `isDesktopSupported()` 方法来确定当前桌面是否受支持。

```java
Desktop desk=Desktop.getDesktop();
```

然后我们使用 `browse()` 方法，在其中输入我们想要在桌面上打开的新 URL。

```java
desk.browse(new URI("http://xyz.com"));
```

## 代码示例

```java
// Java Program to Open Input URL in
// System Default Browser in Windows

import java.awt.Desktop;
import java.io.*;
import java.net.URI;

class GFG {
    public static void main(String[] args)
             throws Exception
    {
        Desktop desk = Desktop.getDesktop();

        // now we enter our URL that we want to open in our
        // default browser
        desk.browse(new URI("http://xyz.com"));
    }
}
```

## 输出

```java
(Our URL "http://xyz.com" will open in our desktop default browser)
```