# C# 程序查找机器的 IP 地址

> 原文:[https://www . geesforgeks . org/c-sharp-program-to-find-the-IP-address-of-machine/](https://www.geeksforgeeks.org/c-sharp-program-to-find-the-ip-address-of-the-machine/)

IP 地址被称为互联网协议地址。它是通过网络识别设备的唯一地址。它几乎就像一套规则，管理通过互联网或本地网络发送的数据。它有助于互联网区分路由器、计算机、网站等。在本文中，我们将学习如何使用 C# 查找机器的 IP 地址。

### 使用 GetHostByName()方法

我们可以使用 GetHostByName()方法找到机器的 IP 地址。此方法返回给定域名系统主机名的域名系统信息。当您在此方法中传递空字符串时，它将返回本地计算机的标准主机名。

**语法:**

> 公共静态系统。Net.IPHostEntry GetHostByName(字符串 hName)；

这里，hName 是主机的 DNS 名称。

**进场:**

> 要查找机器的 IP 地址，请执行以下步骤:
> 
> *   首先包括 System.Net。
> *   我们需要找到主机的名称来获得主机的 IP 地址。因此，主机的名称可以通过使用 Dns 类中的 GetHostName()方法来检索。
> *   通过将主机名传递给 GetHostByName()方法，我们将获得 IP 地址。
> *   此方法返回指定主机名的 hostent 类型的结构。
> *   AddressList[0]给出了 ip 地址，并使用 ToString()方法将其转换为字符串。

**示例:**

## C#

```cs
// C# program to print the IP address of the machine
using System;  
using System.Text;  
using System.Net;

class GFG{

static void Main(string[] args)  
{

    // Get the Name of HOST  
    string hostName = Dns.GetHostName(); 
    Console.WriteLine(hostName);  

    // Get the IP from GetHostByName method of dns class.
    string IP = Dns.GetHostByName(hostName).AddressList[0].ToString();  
    Console.WriteLine("IP Address is : " + IP);  
}  
}
```

**输出:**

```cs
IP Address is : 192.168.122.136
```

### 使用 GetHostEntry()方法

我们还可以使用 GetHostEntry()方法找到机器的 IP 地址。此方法查询 DNS 服务器，并将 IP 地址返回给 IPHostEntry 实例。

**语法:**

> 公共静态系统。net . IPHostEntry GetHostEntry(IP address 地址)；

**进场:**

> 要查找机器的 IP 地址，请执行以下步骤:
> 
> *   首先包括 System.Net。
> *   我们需要找到主机的名称来获得主机的 IP 地址。因此，可以通过使用 DNS 类中的 GetHostName 方法来检索主机的名称。
> *   绕过主机名到 GetHostEntry()方法，我们将获得 IP 地址。
> *   此方法返回指定主机名的 hostent 类型的结构。
> *   AddressList[0]给出了 IP 地址，并使用 ToString()方法将其转换为字符串。

**示例:**

## C#

```cs
// C# program to print the IP address of the machine
using System;  
using System.Text;  
using System.Net;

class GFG{

static void Main() 
{

    // Getting host name
    string host = Dns.GetHostName();

    // Getting ip address using host name
    IPHostEntry ip = Dns.GetHostEntry(host);
    Console.WriteLine(ip.AddressList[0].ToString());
}
}
```

**输出:**

```cs
IP Address is : 192.168.122.136
```