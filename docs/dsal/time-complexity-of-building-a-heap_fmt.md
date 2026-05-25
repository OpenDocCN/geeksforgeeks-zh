# 堆构建的时间复杂度

> 原文：[https://www.geeksforgeeks.org/time-complexity-of-building-a-heap/](https://www.geeksforgeeks.org/time-complexity-of-building-a-heap/)

考虑以下构建输入数组 `A` 的堆的算法：

```
BUILD-HEAP(A) 
    heapsize := size(A); 
    for i := floor(heapsize/2) downto 1 
        do HEAPIFY(A, i); 
    end for 
END
```

## 初步分析

快速浏览一下上面的算法，运行时间是 $O(n \lg n)$，因为每次调用 `HEAPIFY` 都要花费 $O(\lg n)$，而 `BUILD-HEAP` 进行 $O(n)$ 次这样的调用。
这个上限虽然正确，但并不是渐近紧的。

## 推导更紧的界限

我们可以通过观察 `HEAPIFY` 的运行时间依赖于树的高度 $h$（等于 $\lg n$，其中 $n$ 是节点数），并且大多数子树的高度都很小，从而推导出一个更紧的界限。
随着我们沿着树向上移动，高度 $h$ 增加。`BUILD-HEAP` 的第 3 行从最后一个内部节点（索引 `heapsize/2`，高度=1）到根（索引 1，高度= $\lg n$）运行一个循环。因此，`HEAPIFY` 对于每个节点花费不同的时间，即 $O(h)$。

## 计算节点数量

为了找到构建堆的时间复杂度，我们必须知道高度为 $h$ 的节点数量。
为此，我们使用了这样一个事实，即大小为 $n$ 的堆最多有高度为 $h$ 的 $\left \lceil \frac{n}{2^{h+1}} \right \rceil$ 个节点。

## 时间复杂度推导

现在为了推导时间复杂度，我们将 `BUILD-HEAP` 的总成本表示为：

(1) $$
\begin{flalign*}
T(n) &= \sum_{h = 0}^{\lg n}\left \lceil \frac{n}{2^{h+1}} \right \rceil * O(h)\\
&= O\left(n * \sum_{h = 0}^{\lg n}\frac{h}{2^{h}}\right)\\
&= O\left(n * \sum_{h = 0}^{\infty}\frac{h}{2^{h}}\right)\\
\end{flalign*}
$$

步骤 2 使用 Big-Oh 符号的属性来忽略上限函数和常数 2（$2^{h+1} = 2 \cdot 2^h$）。类似地，在第三步中，求和的上限可以增加到无穷大，因为我们使用的是大 O 符号。

## 无穷等比数列求和

无穷等比数列之和（$x < 1$）：

(2) $$
\sum_{n = 0}^{\infty}{x}^{n} = \frac{1}{1-x}
$$

微分两边，乘以 $x$，我们得到：

(3) $$
\sum_{n = 0}^{\infty}n{x}^{n} = \frac{x}{(1-x)^{2}}
$$

## 最终结果

将(3)中得到的结果放回推导(1)中，我们得到：

(4) $$
\begin{flalign*}
&= O\left(n * \frac{\frac{1}{2}}{(1 - \frac{1}{2})^2}\right)\\
&= O(n * 2)\\
&= O(n)\\
\end{flalign*}
$$

因此证明了建立二叉堆的时间复杂度是 $O(n)$。

## 参考文献

**参考:** [http://www.cs.sfu.ca/CourseCentral/307/petra/2009/SLN_2.pdf](http://www.cs.sfu.ca/CourseCentral/307/petra/2009/SLN_2.pdf)

本文由 **Chirag Manwani** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。