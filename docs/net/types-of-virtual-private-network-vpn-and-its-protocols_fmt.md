# 虚拟专用网络的类型及其协议

> 原文：[https://www.geeksforgeeks.org/types-of-virtual-private-network-vpn-and-its-protocols/](https://www.geeksforgeeks.org/types-of-virtual-private-network-vpn-and-its-protocols/)

虚拟专用网代表`虚拟专用网络(VPN)`，允许用户通过互联网安全、私密地连接到专用网络。虚拟专用网创建一个加密的连接，称为虚拟专用网隧道，所有互联网流量和通信都通过这个安全的隧道。

虚拟专用网络基本上有两种类型：

1.  **`Remote Access VPN`：**
    `Remote Access VPN`允许用户连接到专用网络并远程访问其所有服务和资源。用户与专用网络之间的连接通过互联网建立，且连接是安全和私密的。`Remote Access VPN`对家庭用户和商业用户都很有用。

    一个公司的员工，当他/她不在办公室时，使用虚拟专用网络连接到他/她的公司的专用网络，并远程访问专用网络上的文件和资源。虚拟专用网的私人用户或家庭用户，主要使用虚拟专用网服务绕过互联网上的区域限制，访问被阻止的网站。意识到互联网安全的用户也使用虚拟专用网服务来增强他们的互联网安全和隐私。

2.  **`Site to Site VPN`：**
    `Site-to-Site VPN`也称为`Router-to-Router VPN`，通常用于大型公司。在不同地点设有分支机构的公司或组织，使用`Site-to-site VPN`将一个办公地点的网络连接到另一个办公地点的网络。

    *   **基于内部网的虚拟专用网：** 当同一公司的几个办公室使用站点到站点的虚拟专用网类型连接时，称为基于内部网的虚拟专用网。
    *   **基于外联网的 VPN：** 当公司使用站点到站点的 VPN 类型连接到另一家公司的办公室时，称为基于外联网的 VPN。

    基本上，站点到站点 VPN 在地理位置较远的办公室的网络之间创建一个想象中的桥梁，并通过互联网将它们连接起来，维持网络之间的安全和私有通信。在站点到站点虚拟专用网中，一台路由器充当虚拟专用网客户端，另一台路由器充当虚拟专用网服务器，因为它是基于路由器到路由器的通信。当两台路由器之间的身份验证通过后，通信才开始。

## 虚拟专用网络(VPN)协议类型

1.  **`Internet Protocol Security (IPSec)`：**
    `Internet Protocol Security`，即`IPSec`，用于保护跨`IP`网络的互联网通信。`IPSec`通过验证会话来保护互联网协议通信，并在连接期间加密每个数据包。

    `IPSec`以两种模式运行：
    *   传输模式
    *   隧道模式

    传输模式的工作是加密数据包中的消息，隧道模式加密整个数据包。`IPSec`还可以与其他安全协议一起使用，以改进安全系统。

2.  **`Layer 2 Tunneling Protocol (L2TP)`：**
    `L2TP`或`Layer 2 Tunneling Protocol`是一种隧道协议，通常与另一种VPN安全协议（如`IPSec`）结合使用，以建立高度安全的VPN连接。`L2TP`在两个`L2TP`连接点之间生成一个隧道，`IPSec`协议则对数据进行加密，并维护隧道之间的安全通信。

3.  **`Point–to–Point Tunneling Protocol (PPTP)`：**
    `PPTP`或`Point-to-Point Tunneling Protocol`生成一个隧道并封装数据包。`Point-to-Point Protocol (PPP)`用于加密连接之间的数据。`PPTP`是最广泛使用的VPN协议之一，自Windows早期版本以来就一直在使用。除了Windows，`PPTP`也用于Mac和Linux。

4.  **`SSL and TLS`：**
    `SSL (Secure Sockets Layer)`和`TLS (Transport Layer Security)`生成一种VPN连接，其中网络浏览器充当客户端，用户访问权限被限制到特定的应用程序而不是整个网络。在线购物网站通常使用`SSL`和`TLS`协议。网络浏览器很容易切换到`SSL`，并且几乎不需要用户进行任何操作，因为网络浏览器集成了`SSL`和`TLS`。`SSL`连接的URL以“https”开头，而不是“http”。

5.  **`OpenVPN`：**
    `OpenVPN`是一种开源VPN，通常用于创建点对点和站点到站点的连接。它使用基于`SSL`和`TLS`协议的传统安全协议。

6.  **`安全外壳(SSH)`：**
    `安全外壳`或`SSH`生成数据传输所通过的虚拟专用网隧道，并确保该隧道是加密的。`SSH`连接由`SSH`客户端生成，数据通过加密隧道从本地端口传输到远程服务器。