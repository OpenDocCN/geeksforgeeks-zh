# 将字节数组转换为 IP 地址的程序

> 原文:[https://www . geesforgeks . org/program-convert-byte-array-IP-address/](https://www.geeksforgeeks.org/program-convert-byte-array-ip-address/)

给定一个字节数组，将其转换为 [IP 地址](https://www.geeksforgeeks.org/ip-addressing-introduction-and-classful-addressing/)的格式。

示例:

```cs
Input : {16, 16, 16, 16}
Output : 16.16.16.16

Input : {172, 31, 102, 14}
Output : 172.31.102.14

```

**字节数组:**
一个字节是比特(8)的集合。字节数组是连续字节的数组，可以用来存储二进制信息。使用字节数组，可以直接处理字节，从而控制位。字节数组提供了一种更快的方式来访问使用中的每个字节。
更多详情:[https://msdn.microsoft.com/en-us/library/dd126860.aspx](https://msdn.microsoft.com/en-us/library/dd126860.aspx)

**语法:**

```cs
byte[] ArrayName = new byte[] 
```

**IP 地址类:**
**IP 地址类**包含 IP 网络上计算机的地址。IPAddress 类通过扩展[八位字节串类](http://snmpsharpnet.sourceforge.net/ver0-4/html/T_SnmpSharpNet_OctetString.htm)，容纳传递给[简单网络管理协议(SNMP)](https://en.wikipedia.org/wiki/Simple_Network_Management_Protocol) 代理或由其返回的 IP 地址值。IP 地址类属于**系统。Net'** 命名空间。

详见链接:[http://SnmpSharpNet . SourceForge . net/ver0-4/html/T _ SnmpSharpNet _ ipaddress . htm](http://snmpsharpnet.sourceforge.net/ver0-4/html/T_SnmpSharpNet_IpAddress.htm)

**语法:**

```cs
[Serializable]
public class IPAddress
```

**使用带 IP 地址类的字节数组**

```cs
IPAddress ObjectName = new IPAddress(byte[])
```

**方法:**
IP address 类用于获取 IP 地址。IP 地址是在地址属性设置为地址的情况下创建的。如果地址长度为 4，IPAddress(Byte[])将构造一个 IPv4 地址，否则将构造一个作用域为 0 的 IPv6 地址。假设字节数组按网络字节顺序排列，最高有效字节位于索引位置 0。

```cs
// C# code to convert Byte array to IP Address
using System;
using System.Net;

public class GFG {

    public static void Main()
    {

        /* Initializes a new instance of the 
        IPAddress class with the address 
        specified as a Byte Array.*/
        IPAddress add = new IPAddress(new byte[] 
                            { 172, 31, 102, 14 });

        /* ToString() Converts an Internet address
        to its standard notation and 
        console.WriteLine is used for printing*/
        Console.WriteLine(add.ToString());
    }
}
```

**输出:**

```cs
172.31.102.14
```