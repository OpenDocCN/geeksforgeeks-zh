# 什么是网络交换机，它是如何工作的？

> 原文: [https://www.geeksforgeeks.org/what-is-a-network-switch-and-how-does-it-work/](https://www.geeksforgeeks.org/what-is-a-network-switch-and-how-does-it-work/)

交换机是一种网络设备，用于将网络划分为不同的子网，称为子网或局域网网段。它负责根据媒体访问控制地址过滤和转发局域网网段之间的数据包。

*   在 [OSI model](https://www.geeksforgeeks.org/layers-of-osi-model/) 模型中工作。
*   在数据链路层工作，并在转发数据前检查错误。
*   仅将数据传输到指定的设备。
*   以全双工模式工作。
*   为每个局域网网段分配有限的带宽。

## 工作原理

当源想要将数据包发送到目的地时，数据包首先进入交换机，交换机读取其报头并找到目的地的媒体访问控制地址来识别设备，然后通过通向目的地设备的适当端口将数据包发送出去。

交换机在通信源和目的地之间建立临时连接，并在会话完成后终止连接。此外，它还同时为进出设备的网络流量提供全部带宽，以减少冲突。

交换技术用于决定源和目的地之间数据传输的最佳路由。这些分为三类:

1.  [circuit switching](https://www.geeksforgeeks.org/circuit-switching-in-computer-network/)
2.  [message exchange](https://www.geeksforgeeks.org/message-switching-techniques/)
3.  [packet switching](https://www.geeksforgeeks.org/packet-switching-and-delays-in-computer-network/)

## 优势

1.  通过将网络划分为更小的子网，可以防止网络中的流量过载。
2.  增加网络带宽。
3.  减少帧冲突，因为交换机为每个连接创建一个冲突域。

## 缺点

1.  它无法阻止 destined for 不同局域网网段的流量到达所有其他局域网网段。