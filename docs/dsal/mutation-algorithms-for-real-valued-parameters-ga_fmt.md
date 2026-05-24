# 实值参数变异算法(GA)

> 原文：[https://www.geeksforgeeks.org/mutation-algorithms-for-real-valued-parameters-ga/](https://www.geeksforgeeks.org/mutation-algorithms-for-real-valued-parameters-ga/)

[遗传算法](https://www.geeksforgeeks.org/genetic-algorithms/) (GAs)是属于进化算法中较大部分的自适应启发式搜索算法。在每一代中，染色体(我们的候选解)经历变异、交叉和选择，以产生染色体更接近我们期望解的更好的群体。变异操作符是一元操作符，它只需要一个父操作符。它是通过从我们选择的染色体(父母)中选择一些基因，然后对它们应用所需的突变操作符来实现的。

在本文中，我将讨论四种实值参数的变异算法：
1. 均匀变异
2. 非均匀变异
3. 边界变异
4. 高斯变异

这里我们考虑的是一条染色体，有 `n` 个实数(是我们的基因)，`x_i` 代表一个基因，`i` 属于 `[1, n]`。

## 均匀变异

在均匀突变中，我们从染色体中选择一个随机基因，比如说 `x_i`，并给它分配一个均匀的随机值。
让 `x_i` 在范围 `[a_i, b_i]` 内，然后我们将 `U(a_i, b_i)` 分配给 `x_i`。`U(a_i, b_i)` 表示范围 `[a_i, b_i]` 内的统一随机数。

```
Algorithm –
1. Select a random integer number i from [1,n]
2. Set xi to U(ai,bi).
```

## 边界变异

在边界突变中，我们从我们的染色体中选择一个随机基因，比如说 `x_i`，并给它指定 `x_i` 的上限或下限。
让 `x_i` 在范围 `[a_i, b_i]` 内，然后我们将 `a_i` 或 `b_i` 分配给 `x_i`。
我们还选择了一个变量 `r = U(0, 1)` (`r` 是 0 到 1 之间的数字)。
如果 `r` 大于或等于 0.5，将 `b_i` 指定给 `x_i`，否则将 `a_i` 指定给 `x_i`。

```
Algorithm –
1. select a random integer number i form [1,n]
2. select a random real value r from (0,1).
3. If(r >= 0.5)
         Set xi to bi
   else
         Set xi to ai
```

## 非均匀变异

在非均匀突变中，我们从染色体中选择一个随机基因，比如说 `x_i`，并为其分配一个非均匀随机值。
让 `x_i` 在范围 `[a_i, b_i]` 内，然后我们给它分配一个非均匀随机值。

我们使用一个函数，
`f(G) = (r2 * (1 - G / Gmax))^b`，
其中 `r2 = (0, 1)`
`G` = 当前世代数
`Gmax` = 最大世代数
`b` = 一个形状参数
这里我们选择一个 `(0, 1)` 之间的统一随机数 `r1`。
如果 `r1` 大于或等于 0.5，我们分配 `(b_i - x_i) * f(G)` 到 `x_i`，否则我们分配 `(a_i + x_i) * f(G)`。

```
Algorithm –
1. Select a random integer i within [1,n]
2. select two random real values r1 ,r2 from (0,1).
3. If(r1 >= 0.5)
         Set xi to (bi-xi) * f(G)
   else
         Set xi to (ai+ xi) * f(G)
```

## 高斯变异

高斯变异利用了高斯误差函数。它在收敛方面远比前面提到的算法更有效。我们随机选择一个基因，比如说 `x_i`，它属于范围 `[a_i, b_i]`。让突变的关簧为 `x'_i`。每个变量都有一个变异强度算子(`σ_i`)。我们使用 `σ = σ_i / (b_i - a_i)` 作为所有 `n` 个变量的固定无量纲化参数；
因此后代 `x'_i` 由下式给出：

```
x'i= xi + √2 * σ * (bi-ai)erf-1(u’i)
```

这里 `erf()` 表示高斯误差函数。

```
erf(y)=2⁄√π ∫y0 e-t^2 dt
```

为了计算 `u'_i`，我们首先从范围 `(0, 1)` 内选择一个随机值 `u_i`，然后使用以下公式

```
if(ui>=0.5)
    u’i=2*uL*(1-2*ui)
else
    u’i=2*uR*(2*ui-1)
```

同样，`u_L` 和 `u_R` 由公式给出

```
uL=0.5(erf( (ai-xi)⁄(√2(bi-ai)σ) )+1)
uR=0.5(erf( (bi-xi)⁄(√2(bi-ai)σ) )+1)
```

## 参考文献
1. [https://www.iitk.ac.in/kangal/papers/k2012016.pdf](https://www.iitk.ac.in/kangal/papers/k2012016.pdf)
2. [https://en.wikipedia.org/wiki/Mutation_(genetic_algorithm)](https://en.wikipedia.org/wiki/Mutation_(genetic_algorithm))
3. [http://read.pudn.com/downloads152/ebook/662702/gaotv5.pdf](http://read.pudn.com/downloads152/ebook/662702/gaotv5.pdf)