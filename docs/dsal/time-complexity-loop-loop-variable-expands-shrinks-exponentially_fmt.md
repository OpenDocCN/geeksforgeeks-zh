# 当循环变量指数“膨胀或收缩”时循环的时间复杂度

> 原文：[https://www.geeksforgeeks.org/time-complexity-loop-loop-variable-expands-shrinks-exponentially/](https://www.geeksforgeeks.org/time-complexity-loop-loop-variable-expands-shrinks-exponentially/)

对于这种情况，循环的时间复杂度为 `O(log(log(n)))`。以下案例分析了问题的不同方面。

## 案例 1

```cpp
for (int i = 2; i <= n; i = pow(i, k)) {
    // some O(1) expressions or statements
}
```

在这种情况下，`i` 取值 `2`，`2^k`，`(2^k)^k = 2^(k^2)`，`(2^(k^2))^k = 2^(k^3)`，…，`2^(k^(log_k(log(n))))`。最后一项必须小于等于 `n`，我们有 `2^(k^(log_k(log(n)))) = 2^(log(n)) = n`，完全符合我们最后一项的数值。所以总共有 `log_k(log(n))` 多次迭代，每次迭代需要恒定的运行时间，因此总时间复杂度为 `O(log(log(n)))`。

## 案例 2

```cpp
// func() is any constant root function
for (int i = n; i > 1; i = func(i)) {
   // some O(1) expressions or statements
}
```

在这种情况下，`i` 取值 `n`，`n^(1/k)`，`(n^(1/k))^(1/k) = n^(1/(k^2))`，`n^(1/(k^3))`，…，`n^(1/(k^(log_k(log(n)))))`，所以总共有 `log_k(log(n))` 次迭代。每次迭代需要恒定的运行时间，因此总时间复杂度为 `O(log(log(n)))`。

有关不同类型循环的分析，请参考下面的文章。
[https://www.geeksforgeeks.org/analysis-of-algorithms-set-4-analysis-of-loops/](https://www.geeksforgeeks.org/analysis-of-algorithms-set-4-analysis-of-loops/)

本文由 **里沙夫·拉吉** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。