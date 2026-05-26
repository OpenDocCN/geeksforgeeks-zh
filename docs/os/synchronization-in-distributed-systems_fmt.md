# 分布式系统中的同步

> 原文：[https://www.geeksforgeeks.org/synchronization-in-distributed-systems/](https://www.geeksforgeeks.org/synchronization-in-distributed-systems/)

[分布式系统](https://www.geeksforgeeks.org/design-issues-of-distributed-system/)是通过高速通信网络连接的计算机的集合。在分布式系统中，硬件和软件组件通过消息传递来通信和协调它们的动作。分布式系统中的每个节点都可以与其他节点共享资源。因此，需要适当分配资源，以保持资源状态，并帮助协调几个流程。为了解决这种冲突，使用了同步。分布式系统中的同步是通过时钟实现的。

物理时钟用于调整节点的时间。系统中的每个节点都可以与系统中的其他节点共享其本地时间。时间是根据世界协调时设定的。UTC 用作系统中节点的参考时钟。

时钟同步可以通过两种方式实现：外部和内部时钟同步。

1.  `External clock synchronization` 是一个带有外部参考时钟的时钟。它被用作参考，系统中的节点可以据此设置和调整自己的时间。
2.  `Internal clock synchronization` 意味着每个节点与其他节点共享其时间，所有节点据此设置和调整自己的时间。

时钟同步算法有两种类型：集中式和分布式。

1.  `Centralized` 指的是时间服务器。单个时间服务器将其时间传播给节点，所有节点相应地调整时间。它依赖于单个时间服务器，因此如果此节点发生故障，整个系统将失去同步。集中式的例子包括 `Berkeley algorithm`、`passive time server`、`active time server` 等。
2.  `Distributed` 没有集中式的时间服务器。相反，节点使用其本地时间调整时间，然后与其他节点平均时间差。分布式算法克服了集中式算法的可扩展性和单点故障问题。分布式算法的例子包括 `global average algorithm`、`local average algorithm`、`network time protocol` 等。