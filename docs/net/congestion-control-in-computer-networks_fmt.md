# 计算机网络中的拥塞控制

> 原文：[https://www.geeksforgeeks.org/congestion-control-in-computer-networks/](https://www.geeksforgeeks.org/congestion-control-in-computer-networks/)

## 什么是拥塞？

网络层中出现的一种状态，此时消息流量过大，导致网络响应时间变慢。

## 拥塞的影响

## 拥塞控制算法

让我们考虑一个例子来理解。

想象一个底部有小孔的桶。无论水以何种速率进入桶，流出的速率都是恒定的。当桶装满水时，额外进入的水会从桶边溢出并丢失。

类似地，每个网络接口都包含一个漏桶，漏桶算法涉及以下**步骤**：

## 令牌桶算法的必要性

漏桶算法强制以平均速率输出，无论流量多么突发。因此，为了处理突发流量，我们需要一种灵活的算法，以免数据丢失。令牌桶算法就是这样一种算法。

## 该算法的步骤

该算法的步骤可以描述如下：

让我们通过一个例子来理解：

在图（A）中，我们看到一个桶持有三个令牌，有五个数据包等待传输。一个数据包要传输，必须捕获并销毁一个令牌。在图（B）中，我们看到五个数据包中有三个已经通过，但另外两个被卡住，等待生成更多令牌。

```
Let us consider an example to understand
Imagine a bucket with a small hole in the bottom.
No matter at what rate water enters the bucket, the outflow is at a constant rate. When the bucket is full of water additional water enters spills over the sides and is lost.
Similarly, each network interface contains a leaky bucket and the following steps are involved in the leaky bucket algorithm:
Let’s understand with an example,
In figure (A) we see a bucket holding three tokens, with five packets waiting to be transmitted. For a packet to be transmitted, it must capture and destroy one token. In figure (B) We see that three of the five packets have gotten through, but the other two are stuck waiting for more tokens to be generated.
```

## 令牌桶优于漏桶的方式

漏桶算法控制数据包引入网络的速率，但本质上非常保守。令牌桶算法引入了一些灵活性。在令牌桶中，算法令牌在每个刻度处生成（直到某个限制）。对于要传输的传入数据包，它必须捕获令牌，并且传输以相同的速率进行。因此，如果令牌可用，一些繁忙的数据包会以相同的速率传输，从而在系统中引入一定的灵活性。

## 公式

`M * s = C + ρ * s`

其中：
- `S` – 是花费的时间
- `M` – 最大输出速率
- `ρ` – 令牌到达速率
- `C` – 令牌桶的容量（以字节为单位）

漏桶算法问题链接：[https://www.geeksforgeeks.org/computer-networks-set-8/](https://www.geeksforgeeks.org/computer-networks-set-8/)

本文由[维卡什·库马尔](https://www.quora.com/profile/Vikash-Kumar-164)供稿。如果你发现任何不正确的地方，请写评论，或者你想分享更多关于上面讨论的话题的信息。