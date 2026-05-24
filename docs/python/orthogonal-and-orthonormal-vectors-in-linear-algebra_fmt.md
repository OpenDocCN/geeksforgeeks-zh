# 线性代数中的正交和正交向量

> 原文：[https://www.geeksforgeeks.org/orthogonal-and-orthonormal-vectors-in-linear-algebra/](https://www.geeksforgeeks.org/orthogonal-and-orthonormal-vectors-in-linear-algebra/)

## 正交向量

两个向量的点积为 0 时相互正交。

### 我们如何定义点积？

两个 n 维向量 `A` 和 `B` 的点积（标量积），由这个表达式给出。

$$A . B=\sum_{i=1}^{n} a_{i} b_{i}$$

因此，向量 `A` 和 `B` 相互正交当且仅当

$$A.B=\sum_{i=1}^{n} a_{i} b_{i}=A^{T} B=0$$

注意：在紧凑形式中，上述表达式可以写成 `(A^T)B`。

### 示例

考虑 3D 空间中的向量 `v1` 和 `v2`。

$$v_{1}=\left[\begin{array}{c} 1 \\ -2 \\ 4 \end{array}\right], v_{2}=\left[\begin{array}{l} 2 \\ 5 \\ 2 \end{array}\right]$$

取向量的点积。

$$v_{1}, v_{2}=V_{1}^{T} V_{2}=[1-24]\left[\begin{array}{l} 2 \\ 5 \\ 2 \end{array}\right]=0$$

因此，这两个向量相互正交。

### 代码：Python 程序说明正交向量

```py
# A python program to illustrate orthogonal vector

# Import numpy module
import numpy

# Taking two vectors
v1 = [[1, -2, 4]]
v2 = [[2, 5, 2]]

# Transpose of v1
transposeOfV1 = numpy.transpose(v1)

# Matrix multiplication of both vectors
result = numpy.dot(v2, transposeOfV1)
print("Result  = ", result)

# This code is contributed by Amiya Rout
```

### 输出

```py
Result = [[0]]
```

## 单位向量

我们来考虑一个向量 `A`，向量 `A` 的单位向量可以定义为

$$\hat{a}=\frac{A}{|A|}$$

让我们通过一个例子来理解。考虑 2D 空间中的一个向量 `A`。

$$A=\left[\begin{array}{l} 3 \\ 4 \end{array}\right]$$

`A` 的大小由下式给出

$$\text { Magnitude of } \mathrm{A}:|A|=\sqrt{3^{2}+4^{2}}=5$$

因此，`A` 的单位向量可以计算为

$$\hat{a}=\frac{A}{|A|}=\left[\begin{array}{l} 3 / 5 \\ 4 / 5 \end{array}\right]$$

### 单位向量的属性

*   单位矢量用于定义坐标系中的方向。
*   任何向量都可以写成单位向量和标量大小的乘积。

## 正交向量

这些是单位大小的向量。现在，取相同的两个相互正交的向量，你知道，当我取这两个向量之间的点积时，它将为 0。因此，如果我们也强加一个条件，我们希望这些向量中的每一个都有单位大小，那么我们可能做的是，取这个向量，然后用这个向量除以这个向量的大小，就像我们在单位向量中看到的那样。现在我们可以把 `v1` 和 `v2` 写成

$$v_{1}=\left[\begin{array}{c} 1 \\ -2 \\ 4 \end{array}\right] / \sqrt{1^{2}+(-2)^{2}+4^{2}} \quad v_{2}=\left[\begin{array}{l} 2 \\ 5 \\ 2 \end{array}\right] / \sqrt{2^{2}+5^{2}+2^{2}}$$

所以我们要做的是，我们从前面的例子中获取向量，并通过将它们除以它们的大小，将它们转换成单位向量。**所以，这些向量仍然相互正交，现在它们各自也有单位幅度。这种向量被称为正交向量。**

注意：根据定义本身，所有正交向量都是正交的。