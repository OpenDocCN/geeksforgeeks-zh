# JMS 中 PointToPoint 和发布/订阅模型的区别

> 原文：[https://www.geeksforgeeks.org/differences-between-pointtopoint-and-publish-subscribe-model-in-jms/](https://www.geeksforgeeks.org/differences-between-pointtopoint-and-publish-subscribe-model-in-jms/)

## 概述

**点对点消息模型**和**发布订阅消息模型**是`Java消息服务(JMS)`支持的两类消息模块/类型/域。

这两个是支持异构系统之间异步消息传递的编程模型。

## 关键术语

有一些重要的术语，将有助于我们更好地理解这两种消息模型类型之间的区别：

*   `JMS destination`是一个中转区域，它作为客户端使用的消息源和生成消息的目的地。
*   `JMS producer`是一个发送消息的JMS客户端。
*   `JMS consumer`是一个接收消息的JMS客户端。
*   一个`JMS client`可以既是消息生产者也是消息消费者。
*   `Time Dependence`简单来说，如果生产者发布了某个主题的消息而消费者没有订阅，那么该消费者将不会收到该主题的消息。

## 模型区别

我们来看看这两种消息模型类型的区别：

| **Point-To-Point Messaging Model (P2P)** | **Publish/Subscribe Model (Pub/Sub)** |
| --- | --- |
| 这里的JMS Destination是队列（`queue`）。 | Pub/Sub中的JMS Destination是主题（`topic`）。 |
| 这里的JMS Producer是发送者（`sender`）。 | Pub/Sub中的JMS Producer是发布者（`publisher`）。 |
| 这里的JMS Consumer是接收者（`receiver`）。 | Pub/Sub中的JMS Consumer是订阅者（`subscriber`）。 |
| 消息在这里只被一个JMS Consumer接收。 | 在Pub/Sub中，一条消息可以被多个JMS Consumer接收。 |
| 这里，JMS Consumer在接收到消息时会向生产者发送确认。 | 在Pub/Sub中，JMS Consumer在接收消息时不会发送任何确认。 |
| 接收者接收消息存在时间依赖性。 | 在Pub/Sub中，生产者和消费者之间没有时间依赖性。 |
| 此模型是拉取型（`pull-type`），即接收者负责请求发送者发送新消息。 | 此模式是基于推送（`push-based`）的，意味着消息会自动传递给消费者，他们无需请求新消息。 |
| 示例：发送传真/语音消息。 | 示例：报纸。 |