# 帧间和帧内压缩之间的差异

> 原文：[https://www.geeksforgeeks.org/difference-between-inter-and-intra-frame-compression/](https://www.geeksforgeeks.org/difference-between-inter-and-intra-frame-compression/)

## 压缩概述

在`压缩`中，我们减少了数据的大小，以实现高效率和易于存储。传输大文件非常麻烦，所以我们需要压缩它。压缩文件减少了数据传输时间，降低了存储成本。

![](img/75f55b0199db0420fb810f0978ec55c0.png)

```
Compression Ratio = B1 / B2 
```

其中，
B1 =压缩前表示数据所需的总位数
B2 =压缩后表示数据所需的总位数

有两种主要的压缩类型：

1.  `帧间压缩`
2.  `帧内压缩`

## 帧间和帧内压缩的差异

| 特性 | 帧间压缩 | 帧内压缩 |
| :--- | :--- | :--- |
| **原理** | 在这种情况下，数据缩减发生在帧之间。它利用连续帧之间的冗余。 | 在这种情况下，数据缩减发生在帧内。它利用帧内的冗余。 |
| **别名** | 它也被称为时间冗余，图像过渡是突然的 | 它也被称为空间冗余，其中图像转换是基于块的。 |
| **处理时间** | 它需要更多的处理时间，因为计算机需要查看几个帧。 | 它需要更少的处理时间，因为计算机处理的是单帧。 |
| **流行编解码器** | 一些流行帧间编解码器是：<br>1. `H.264` - MPEG-4 的变体<br>2. `MPEG-4`<br>3. `MPEG-2`<br>4. `H.265` (HEVC) - H.264 的变体<br>5. `XDCAM` - 索尼<br>6. `XAVC` - 索尼 | 一些流行的帧内编解码器有：<br>1. `CineForm`<br>2. `ProRes` - 苹果<br>3. `DNxHD` - Avid<br>4. `All-I` - 在较新的数码单反相机中找到<br>5. `CinemaDNG` - Adobe 的原始图像序列 |