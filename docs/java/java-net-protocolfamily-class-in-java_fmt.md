# java 中的 `java.net.ProtocolFamily` 类

> 原文: [https://www.geeksforgeeks.org/java-net-protocolfamily-class-in-java/](https://www.geeksforgeeks.org/java-net-protocolfamily-class-in-java/)

`ProtocolFamily` 是一个 Java 接口。`java.net.ProtocolFamily` 代表了一个通信协议家族。`java.net.StandardProtocolFamily` 实现 `ProtocolFamily` 接口。

```java
public interface ProtocolFamily 
```

## `java.net.ProtocolFamily` 的方法

`java.net.ProtocolFamily` 接口只包含一个方法：

| 序号 | 方法 | 说明 | 返回类型 |
| :--- | :--- | :--- | :--- |
| 1. | `name()` | `name()` 方法返回协议家族的名称。 | `String` |

## 使用 `ProtocolFamily` 接口

| 序号 | 包 | 修饰符和类型 | 名称 | 说明 |
| :--- | :--- | :--- | :--- | :--- |
| 1. | `java.net` | 类 | `StandardProtocolFamily` | 标准协议类定义了通信协议的标准系列。 |
| 2. | `java.nio.channels` | 静态 `DatagramChannel` | `open(ProtocolFamily family)` | 方法打开一个数据报通道。 |
| 3. | `java.nio.channels.spi` | 抽象 `DatagramChannel` | `SelectorProvider.openDatagramChannel(ProtocolFamily family)` | 打开数据报通道。 |

### 更好理解 `ProtocolFamily` 接口的 Java 程序

```java
// Java Program to get Protocol
// family for an IP Address

// import Guava library
import com.google.common.net.InetAddresses;
import java.io.*;
import java.net.*;

class GFG {
    public static void main(String[] args)
    {
        try {
            // to get the ip address of
            InetAddress ip
                = InetAddress.getByName("45.22.30.39");
            System.out.println("Host Name is "
                               + ip.getHostName());

            // getProtocolFamily() will check and return the
            // protocol family of the given IP
            ProtocolFamily protocolFamily
                = getProtocolFamily(ip);

            System.out.println("Protocol family of the "
                               + ip.getHostName() + " is "
                               + protocolFamily);
        }
        catch (Exception e) {
            System.out.println("Some exception"
                               + e.getMessage());
        }
    }

    public static ProtocolFamily
    getProtocolFamily(InetAddress inetAddress)
    {
        // to check if address is valid or not
        if (InetAddresses.isInetAddress(
                inetAddress.getHostName())) {
            // if address is valid
            // will return the protocol family of the
            // address
            return StandardProtocolFamily.INET;
        }
        else {
            // address is not valid
            System.out.println(
                "Address " + inetAddress
                + "is invalid hence can't determine the protocol family");
        }
        return StandardProtocolFamily.INET;
    }
}
```

**输出**

```
Host Name is 45.22.30.39
Protocol family of the 45.22.30.39 is INET
```