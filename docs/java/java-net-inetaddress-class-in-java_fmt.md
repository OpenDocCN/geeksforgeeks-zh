# Java 中的 InetAddress 类

> 原文: [https://www.geeksforgeeks.org/java-net-inetaddress-class-in-java/](https://www.geeksforgeeks.org/java-net-inetaddress-class-in-java/)

## 简介

`InetAddress` 类扩展了 `Object` 并实现了 `Serializable`。

`java.net.InetAddress` 类提供了获取任何主机名的 IP 地址的方法。IP 地址由 32 位或 128 位无符号数字表示。互联网地址可以同时处理 IPv4 和 IPv6 地址。

地址有两种类型：
1.  **单播** — 单个接口的标识符。
2.  **多播** — 一组接口的标识符。

## 工厂方法

`InetAddress` 类用于封装数字 IP 地址和该地址的域名。该类没有可见的构造函数。`InetAddress` 类不能直接创建对象，因此*工厂方法*用于此目的。工厂方法是类中返回该类对象的静态方法。

`InetAddress` 类的工厂方法如下：

| 方法 | 描述 |
| --- | --- |
| `static InetAddress getLocalHost()` *throws UnknownHostException* | 此方法返回一个包含本地主机名和地址的 `InetAddress` 实例。 |
| `static InetAddress getByName(String host)` *throws UnknownHostException* | 此方法返回一个包含本地主机 IP 和名称的 `InetAddress` 实例。 |
| `static InetAddress[] getAllByName(String hostName)` *throws UnknownHostException* | 此方法返回一个包含 IP 地址的 `InetAddress` 类实例数组。 |
| `static InetAddress getByAddress(byte[] IPAddress)` *throws UnknownHostException* | 此方法返回一个根据原始 IP 地址创建的 `InetAddress` 对象。 |
| `static InetAddress getByAddress(String hostName, byte[] ipAddress)` *throws UnknownHostException* | 此方法根据提供的主机名和 IP 地址创建并返回一个 `InetAddress`。 |

下面是 `InetAddress` 类的 Java 实现，演示了工厂方法的使用：

```java
import java.io.*;
import java.net.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
        throws UnknownHostException
    {
        // To get and print InetAddress of Local Host
        InetAddress address1 = InetAddress.getLocalHost();
        System.out.println("InetAddress of Local Host : "
                           + address1);

        // To get and print InetAddress of Named Host
        InetAddress address2
            = InetAddress.getByName("45.22.30.39");
        System.out.println("InetAddress of Named Host : "
                           + address2);

        // To get and print ALL InetAddresses of Named Host
        InetAddress address3[]
            = InetAddress.getAllByName("172.19.25.29");
        for (int i = 0; i < address3.length; i++) {
            System.out.println(
                "ALL InetAddresses of Named Host : "
                + address3[i]);
        }

        // To get and print InetAddresses of
        // Host with specified IP Address
        byte IPAddress[] = { 125, 0, 0, 1 };
        InetAddress address4
            = InetAddress.getByAddress(IPAddress);
        System.out.println(
            "InetAddresses of Host with specified IP Address : "
            + address4);

        // To get and print InetAddresses of Host
        // with specified IP Address and hostname
        byte[] IPAddress2
            = { 105, 22, (byte)223, (byte)186 };
        InetAddress address5 = InetAddress.getByAddress(
            "gfg.com", IPAddress2);
        System.out.println(
            "InetAddresses of Host with specified IP Address and hostname : "
            + address5);
    }
}
```

**Output**

```
InetAddress of Local Host : localhost/127.0.0.1
InetAddress of Named Host : /45.22.30.39
ALL InetAddresses of Named Host : /172.19.25.29
InetAddresses of Host with specified IP Address : /125.0.0.1
InetAddresses of Host with specified IP Address and hostname : gfg.com/105.22.223.186
```

## 实例方法

`InetAddress` 类有很多可以使用对象调用的实例方法。实例方法有：

| 方法 | 描述 |
| --- | --- |
| `boolean equals(Object obj)` | 此函数将此对象与指定对象进行比较。 |
| `byte[] getAddress()` | 此方法以字节形式返回此 `InetAddress` 对象的原始 IP 地址。 |
| `String getCanonicalHostName()` | 此方法返回此 IP 地址的完全限定域名。 |
| `String getHostAddress()` | 此方法以字符串形式获取 IP 地址。 |
| `String getHostName()` | 此方法返回此 IP 地址的主机名。 |
| `int hashCode()` | 此方法获取此 IP 地址的 `hashCode`。 |
| `boolean isAnyLocalAddress()` | 此方法实用程序例程检查 `InetAddress` 是否是通配地址。 |
| `boolean isLinkLocalAddress()` | 此方法实用程序例程检查地址是否是链路本地单播地址。 |
| `boolean isLoopbackAddress()` | 此方法用于检查 `InetAddress` 是否代表环回地址。 |
| `boolean isMCGlobal()` | 此方法实用程序例程检查此地址是否具有全局范围的多播地址。 |
| `boolean isMCLinkLocal()` | 此方法实用程序例程检查此地址是否具有链路本地范围的多播地址。 |
| `boolean isMCNodeLocal()` | 此方法实用程序例程检查此多播地址是否具有节点本地范围。 |
| `boolean isMCOrgLocal()` | 此方法实用程序例程检查此多播地址是否具有组织本地范围。 |
| `boolean isMCSiteLocal()` | 此方法实用程序例程检查此多播地址是否具有站点本地范围。 |
| `boolean isMulticastAddress()` | 此方法检查此地址是否为多播地址。 |
| `boolean isReachable(int timeout)` | 此方法测试地址是否可达。 |
| `boolean isReachable(NetworkInterface netif, int ttl, int timeout)` | 此方法测试地址是否可达。 |
| `boolean isSiteLocalAddress()` | 此方法实用程序例程检查 `InetAddress` 是否是站点本地地址。 |
| `String toString()` | 此方法将 IP 地址转换为字符串并返回。 |

下面是 `InetAddress` 类的 Java 实现，演示了实例方法的使用：

```java
import java.io.*;
import java.net.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
        throws UnknownHostException
    {
        InetAddress address1
            = InetAddress.getByName("45.22.30.39");
        InetAddress address2
            = InetAddress.getByName("45.22.30.39");
        InetAddress address3
            = InetAddress.getByName("172.19.25.29");

        // true, as clearly seen above
        System.out.println(
            "Is Address-1 equals to Address-2? : "
            + address1.equals(address2));
        // false
        System.out.println(
            "Is Address-1 equals to Address-3? : "
            + address1.equals(address3));

        // returns IP address
        System.out.println("IP Address : "
                           + address1.getHostAddress());
        // returns host name,
        // which is same as IP
        // address in this case
        System.out.println(
            "Host Name for this IP Address : "
            + address1.getHostName());

        // returns address in bytes
        System.out.println("IP Address in bytes : "
                           + address1.getAddress());

        // false, as the given site
        //  has only one server
        System.out.println("Is this Address Multicast? : "
                           + address1.isMulticastAddress());

        System.out.println("Address in string form : "
                           + address1.toString());

        // returns fully qualified
        // domain name for this IP address.
        System.out.println(
            "Fully qualified domain name for this IP address : "
            + address1.getCanonicalHostName());

        // hashcode for this IP address.
        System.out.println("Hashcode for this IP address : "
                           + address1.hashCode());
    }
}
```

```java
// to check if the InetAddress is
// an unpredictable address..
System.out.println(
    "Is the InetAddress an unpredictable address? : "
    + address1.isAnyLocalAddress());
}
}
```

## Output

```java
Is Address-1 equals to Address-2? : true
Is Address-1 equals to Address-3? : false
IP Address : 45.22.30.39
Host Name for this IP Address : 45.22.30.39
IP Address in bytes : [B@579bb367
Is this Address Multicast? : false
Address in string form : 45.22.30.39/45.22.30.39
Fully qualified domain name for this IP address : 45.22.30.39
Hashcode for this IP address : 756424231
Is the InetAddress an unpredictable address? : false
```