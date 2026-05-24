# 算法分析 | 集合 3 (渐近符号)

> 原文: [https://www.geeksforgeeks.org/analysis-of-algorithms-set-3-asymptotic-notations/](https://www.geeksforgeeks.org/analysis-of-algorithms-set-3-asymptotic-notations/)

我们已经讨论了[渐近分析](https://www.geeksforgeeks.org/analysis-of-algorithms-set-1-asymptotic-analysis/)，以及[最差、平均](https://www.geeksforgeeks.org/analysis-of-algorithms-set-2-asymptotic-analysis/)、[和算法的最佳情况](https://www.geeksforgeeks.org/analysis-of-algorithms-set-2-asymptotic-analysis/)。渐近分析的主要思想是对算法的效率进行度量，这些算法不依赖于机器特定的常数，也不需要实现算法和比较程序所花费的时间。渐近符号是表示渐近分析算法时间复杂性的数学工具。以下 3 个渐近符号主要用于表示算法的时间复杂度。

![thetanotation](img/f6f524e7a1972263a6844f82d41fbda9.png)

## 1) θ 表示法
θ 表示法从上而下界定了一个函数，因此它定义了精确的渐近行为。
获得表达式的 θ 符号的一个简单方法是去掉低阶项，忽略前导常数。例如，考虑以下表达式。
`3n^3 + 6n^2 + 6000 = θ(n^3)`
去掉低阶项总是可以的，因为总是会有一个数 (`n`)，在这个数之后，`θ(n^3)` 的值比 `θ(n^2)` 的值高，而与所涉及的常数无关。
对于给定的函数 `g(n)`，我们表示 `θ(g(n))` 是下面的一组函数。

```
Θ(g(n)) = {f(n): there exist positive constants c1, c2 and n0 such 
                 that 0 <= c1*g(n) <= f(n) <= c2*g(n) for all n >= n0}
```

上述定义意味着，如果 `f(n)` 是 `g(n)` 的 θ，那么对于 `n` (`n >= n0`) 的大值，`f(n)` 的值总是在 `c1*g(n)` 和 `c2*g(n)` 之间。θ 的定义还要求对于大于 `n0` 的 `n` 值，`f(n)` 必须是非负的。

![BigO](img/1cd9908d3872918a9a2e382416a26c27.png)

## 2) 大 O 符号
大 O 符号定义了一个算法的上界，它只从上界定义一个函数。例如，考虑插入排序的情况。最好的情况下需要线性时间，最坏的情况下需要二次时间。我们可以有把握地说，插入排序的时间复杂度是 `O(n^2)`。注意，`O(n^2)` 也涵盖线性时间。
如果我们用 θ 符号来表示插入排序的时间复杂度，那么对于最好和最坏的情况，我们必须使用两个语句:
1.  插入排序的最坏时间复杂度是 `θ(n^2)`。
2.  插入排序的最佳时间复杂度是 `θ(n)`。

当我们对一个算法的时间复杂度只有一个上限时，大 O 符号是有用的。很多时候，我们只要看一下算法，就很容易找到一个上限。

```
O(g(n)) = { f(n): there exist positive constants c and 
                  n0 such that 0 <= f(n) <= c*g(n) for 
                  all n >= n0}
```

![BigOmega](img/7707d2462dcc9af840c72158a745a072.png)

## 3) ω 记数法
正如大 O 记数法提供了函数的渐近上界，ω 记数法也提供了渐近下界。
当我们对算法的时间复杂度有一个下限时，ω 记数法可能是有用的。如前一篇文章中所讨论的，算法的[最佳情况性能通常没有什么用处](https://www.geeksforgeeks.org/analysis-of-algorithms-set-2-asymptotic-analysis/)，欧米茄符号是三种符号中使用最少的。

对于给定的函数 `g(n)`，我们用 `ω(g(n))` 表示这组函数。

```
Ω (g(n)) = {f(n): there exist positive constants c and
                  n0 such that 0 <= c*g(n) <= f(n) for
                  all n >= n0}.
```

让我们在这里考虑相同的插入排序示例。插入排序的时间复杂度可以写成 `ω(n)`，但它不是关于插入排序的非常有用的信息，因为我们通常对最坏情况感兴趣，有时对一般情况感兴趣。

## 渐近符号的性质
我们已经讨论了这三种符号的定义，现在让我们讨论这些符号的一些重要性质。

### 1. 常规属性
如果 `f(n)` 是 `O(g(n))`，那么 `a*f(n)` 也是 `O(g(n))`；其中 `a` 是常数。
例: `f(n) = 2n + 5` 是 `O(n)`
那么 `7*f(n) = 7(2n + 5) = 14n + 35` 也是 `O(n)`。
类似地，该属性同时满足 θ 和 ω 符号。
我们可以说
如果 `f(n)` 是 `θ(g(n))`，那么 `a*f(n)` 也是 `θ(g(n))`；其中 `a` 是常数。
如果 `f(n)` 是 `ω(g(n))`，那么 `a*f(n)` 也是 `ω(g(n))`；其中 `a` 是常数。

### 2. 传递属性
如果 `f(n)` 是 `O(g(n))`，`g(n)` 是 `O(h(n))`，那么 `f(n) = O(h(n))`。
举例: 如果 `f(n) = n`，`g(n) = n`，`h(n) = n^2`
`n` 是 `O(n)`，`n` 是 `O(n^2)`
那么 `n` 就是 `O(n^2)`
类似地，该属性同时满足 θ 和 ω 符号。
我们可以说
如果 `f(n)` 是 `θ(g(n))`，`g(n)` 是 `θ(h(n))`，那么 `f(n) = θ(h(n))`。
如果 `f(n)` 是 `ω(g(n))`，`g(n)` 是 `ω(h(n))`，那么 `f(n) = ω(h(n))`

### 3. 自反属性
自反性质在传递之后总是容易理解的。
如果给出了 `f(n)`，那么 `f(n)` 就是 `O(f(n))`。因为 `f(n)` 的最大值将是 `f(n)` 本身！
因此 `x = f(n)` 和 `y = O(f(n))` 总是以自反关系联系在一起。
例: `f(n) = n`；`O(n)` i.e 或 `f(n)` 项
类似地，该属性同时满足 θ 和 ω 符号。
我们可以说:
如果给出 `f(n)`，那么 `f(n)` 就是 `θ(f(n))`。
如果给出 `f(n)`，那么 `f(n)` 就是 `ω(f(n))`。

### 4. 对称属性
如果 `f(n)` 是 `θ(g(n))`，那么 `g(n)` 就是 `θ(f(n))`。
例如: `f(n) = n^2` 和 `g(n) = n^2`
然后 `f(n) = θ(n^2)` 和 `g(n) = θ(n^2)`
**该属性仅满足 θ 表示法。**

### 5. 转置对称属性
如果 `f(n)` 是 `O(g(n))`，那么 `g(n)` 就是 `ω(f(n))`。
例: `f(n) = n`，`g(n) = n^2`
那么 `n` 就是 `O(n^2)`，`n^2` 就是 `ω(n)`
**该属性仅满足 O 和 ω 符号。**

### 6. 更多属性
1.  如果 `f(n) = O(g(n))` 和 `f(n) = ω(g(n))` 那么 `f(n) = θ(g(n))`
2.  如果 `f(n) = O(g(n))` 和 `d(n) = O(e(n))` 那末 `f(n) + d(n) = O( max( g(n), e(n) )`
    例如: `f(n) = n` i.e. `O(n)`
    `d(n) = n^2` i.e. `O(n^2)`
    然后 `f(n) + d(n) = O(n^2)`
3.  如果 `f(n) = O(g(n))` 和 `d(n) = O(e(n))`
    那么 `f(n) * d(n) = O( g(n) * e(n) )`
    例如: `f(n) = n` i.e. `O(n)`
    `d(n) = n^2` i.e. `O(n^2)`
    那么 `f(n) * d(n) = O(n^3)`

---

## 练习
以下哪个陈述是/是有效的？
1.  归并排序的时间复杂度是 `θ(n^2)`
2.  归并排序的时间复杂度是 `O(n^2)`
3.  对于任意两个函数 `f(n)` 和 `g(n)`，我们有 `f(n) = θ(g(n))` 当且仅当 `f(n) = O(g(n))` 和 `f(n) = ω(g(n))`。
4.  所有计算机算法的时间复杂度可以写成 `ω(1)`

## 重要环节
*   还有两个符号叫做 [**小 o 和小欧米茄**](https://www.geeksforgeeks.org/analysis-of-algorithems-little-o-and-little-omega-notations/)。小 O 提供严格的上限(从大 O 中移除相等条件)，小 ω 提供严格的下限(从大 ω 中移除相等条件)
*   [算法分析 | 集合 4 (循环分析)](https://www.geeksforgeeks.org/analysis-of-algorithms-set-4-analysis-of-loops/)
*   [算法分析近期文章。](https://www.geeksforgeeks.org/category/algorithm/analysis/)

## 参考文献
[Lec 1 | MIT (算法导论)](http://www.youtube.com/watch?v=JPyuH4qXLZ0)

本文由**阿沛·拉提**供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。