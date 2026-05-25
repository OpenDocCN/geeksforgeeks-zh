# AS Override和Allowas In的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-as-override-and-allowas-in/](https://www.geeksforgeeks.org/difference-between-as-override-and-allowas-in/)

## 1. AS Override
其功能允许提供商边缘（PE）路由器在VPN路由和转发接入链路上运行的外部BGP会话上更改客户边缘（CE）设备使用的私有自治系统。专用自治系统号改为PE号。

## 2. Allowas In
该功能允许接收和处理路由，即使路由器在AS-Path中检测到自己的ASN。如果[路由器](https://www.geeksforgeeks.org/introduction-of-a-router/)认为其在AS-Path中的ASN是一种环路防止机制，它会丢弃BGP网络前缀。

## AS Override和Allowas In的区别

| 参数 | AS Override | Allowas In |
| :--- | :--- | :--- |
| 概观 | 它被PE用来修改AS路径。这样做是为了在默认行为下不丢弃前缀，从而不允许它自己的AS成员出现在前缀的AS路径中。 | 它被用作自治系统路径环路防止机制，其中BGP的默认行为是不允许其自身的自治系统号出现在前缀的自治系统路径中。 |
| 输出 | 在对本地自治系统的BGP更新中，AS Override功能取代了AS。 | 它在包含本地AS的BGP更新中是允许的。 |
| 配置于 | 其功能在服务提供商端配置。 | 其功能在客户端配置。 |
| 配置 | 它配置在：
`router bgp`
`neighbor <ip> as-override` 下 | 在
`router bgp`
`neighbor <ip> allowas-in` 下配置 |
| AS路径 | AS路径中有修改。 | AS路径中没有修改。 |
| 范围 | 在服务提供商端执行配置。 | 在客户端执行配置。 |
| 最佳用途 | 当客户要求在CE端保持最低配置时，最好使用这种方法。 | 这种方法最适合在BGP中引入一个异常作为循环防止机制。 |