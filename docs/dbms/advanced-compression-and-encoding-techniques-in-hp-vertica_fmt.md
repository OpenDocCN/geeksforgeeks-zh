# 惠普 Vertica 中的高级压缩和编码技术

> 原文：[https://www.geeksforgeeks.org/advanced-compression-and-encoding-techniques-in-hp-vertica/](https://www.geeksforgeeks.org/advanced-compression-and-encoding-techniques-in-hp-vertica/)

我们在计算机系统中存储数据的主要目的是减少数据将占用的存储空间。`Vertica` 使用`编码和压缩`技术来优化数据存储，并提高查询性能。

## 编码

编码是将数据转换成某种标准格式的过程，这种编码数据可以由 `Vertica` 直接处理。`Vertica` 中最常用的编码技术有：

*   游程编码（`RLE`）
*   `Deltaval` 编码

## 压缩

压缩是压缩数据的方法，`Vertica` 无法直接理解。首先，数据必须被解压缩，只有这个解压缩的数据才能被 `Vertica` 理解。最常用的压缩技术是：

*   `LZO`（基于莱姆佩尔-齐夫-奥伯胡默）压缩

### 游程编码（RLE）

`RLE` 用于压缩列中几乎没有不同值的排序数据。

![](img/b0289584b7c95868fcceb8f8b3ccb311.png)

### Deltaval 编码

在 `Deltaval` 编码中，数据可以是已排序的，也可以是未排序的，并且值不是很明显。以其中一个数据为基础，找出数据之间的差异。

![](img/e309c482dcdabebc195e53d6c33414eb.png)

### LZO 压缩

`LZO` 压缩是在数据未排序时使用的数据非常鲜明。`LZO` 压缩删除了字符之间的空格，并对它们进行编码，就像在我们发送电子邮件之前压缩文档一样。

![](img/36ca00975f14b93465e8e73a014c46c7.png)