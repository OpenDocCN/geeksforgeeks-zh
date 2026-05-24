# Java 中的 `Inet4Address` 类

> 原文: [https://www.geeksforgeeks.org/java-net-inet4address-class-java/](https://www.geeksforgeeks.org/java-net-inet4address-class-java/)

这个类扩展了 `InetAddress` 类，表示一个 IPv4 地址。它提供了解释和显示关于 IP 地址的有用信息的方法。

**这个类的方法采用 4 种格式输入:**

1.  **D.D.D.D.:** 当使用此格式作为输入时，每个给定的值从左到右分配给 IP 地址的 4 个字节。
2.  **D.D.D.:** 当使用此格式作为输入时，最后一部分被解释为一个 16 位数字，并作为主机地址分配给最右边的 2 个字节。这通常用于指定 B 类地址。
3.  **D.D.:** 当使用此格式作为输入时，最后一部分被解释为一个 24 位数字，并作为主机地址分配给最右边的 3 个字节。这通常用于指定 A 类地址。
4.  **D:** 当使用此格式作为输入时，给定的值直接存储为网络地址，无需任何重新排列。

**方法:**

| 方法 | 描述 |
| --- | --- |
| `equals(Object obj)` | 此方法将此对象与指定的对象进行比较。 |
| `getAddress()` | 此方法返回此 `InetAddress` 对象的原始 IP 地址。 |
| `getHostAddress()` | 此方法以文本表示形式返回 IP 地址字符串。 |
| `hashCode()` | 此方法返回此 IP 地址的哈希码。 |
| `isAnyLocalAddress()` | 此方法实用程序例行检查 `InetAddress` 是否是通配符地址。 |
| `isLinkLocalAddress()` | 此方法实用程序例行检查 `InetAddress` 是否是链路本地地址。 |
| `isLoopbackAddress()` | 此方法实用程序例行检查 `InetAddress` 是否是回环地址。 |
| `isMCGlobal()` | 此方法实用程序例行检查组播地址是否具有全局范围。 |
| `isMCLinkLocal()` | 此方法实用程序例行检查组播地址是否具有链路范围。 |
| `isMCNodeLocal()` | 此方法实用程序例行检查组播地址是否具有节点范围。 |
| `isMCOrgLocal()` | 此方法实用程序例行检查组播地址是否具有组织范围。 |
| `isMCSiteLocal()` | 此方法实用程序例行检查组播地址是否具有站点范围。 |
| `isMulticastAddress()` | 此方法实用程序例行检查 `InetAddress` 是否是 IP 组播地址。 |
| `isSiteLocalAddress()` | 此方法实用程序例行检查 `InetAddress` 是否是站点的本地地址。 |

**Java 实现:**

## Java 代码示例

```java
// Java program to illustrate various
// Inet4Address class methods
import java.net.Inet4Address;
import java.net.InetAddress;
import java.net.UnknownHostException;
import java.util.Arrays;

public class inet4add
{
    public static void main(String args[]) throws UnknownHostException
    {
        String url = "www.geeksforgeeks.org";
        Inet4Address ip1 = (Inet4Address) Inet4Address.getByName(url);
        Inet4Address ip2 = (Inet4Address) InetAddress.getByName("www.yahoo.com");

// Following methods checks the property of the thus created object.
        // getAddress() method
        System.out.println("Address : " + Arrays.toString(ip1.getAddress()));

// getHostAddress() method
        System.out.println("Host Address : " + ip1.getHostAddress());

// isAnyLocalAddress() method
        System.out.println("isAnyLocalAddress : " + ip1.isAnyLocalAddress());

// isLinkLocalAddress() method
        System.out.println("isLinkLocalAddress : " + ip1.isLinkLocalAddress());

// isLoopbackAddress() method
        System.out.println("isLoopbackAddress : " + ip1.isLoopbackAddress());

// isMCGlobal() method
        System.out.println("isMCGlobal : " + ip1.isMCGlobal());

// isMCLinkLocal() method
        System.out.println("isMCLinkLocal : " + ip1.isMCLinkLocal());

// isMCNodeLocal() method
        System.out.println("isMCNodeLocal : " + ip1.isMCNodeLocal());

// isMCOrgLocal() method
        System.out.println("isMCOrgLocal : " + ip1.isMCOrgLocal());

// isMCSiteLocal() method
        System.out.println("isMCSiteLocal : " + ip1.isMCSiteLocal());

// isMulticastAddress() method
        System.out.println("isMulticastAddress : " + ip1.isMulticastAddress());

// isSiteLocalAddress() method
        System.out.println("isSiteLocalAddress : " + ip1.isSiteLocalAddress());

// hashCode() method
        System.out.println("hashCode : " + ip1.hashCode());

// equals() method
        System.out.println("ip1==ip2 : " + ip1.equals(ip2));
    }
}
```

## 输出

```java
Address : [52, 84, 102, -116]
Host Address : 52.84.102.140
isAnyLocalAddress : false
isLinkLocalAddress : false
isLoopbackAddress : false
isMCGlobal : false
isMCLinkLocal : false
isMCNodeLocal : false
isMCOrgLocal : false
isMCSiteLocal : false
isMulticastAddress : false
isSiteLocalAddress : false
hashCode : 877946508
ip1==ip2 : false
```

本文由**里沙布·马赫塞**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。