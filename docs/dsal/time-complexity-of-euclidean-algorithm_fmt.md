# 欧几里德算法的时间复杂度

> 原文: [https://www.geeksforgeeks.org/time-complexity-of-euclidean-algorithm/](https://www.geeksforgeeks.org/time-complexity-of-euclidean-algorithm/)

在本文中，我们将讨论[欧几里德算法](http://geeksforgeeks.org/euclidean-algorithms-basic-and-extended/)的时间复杂度，它是 `O(log(min(a, b)))` 并且实现了。

[**欧几里德算法**](http://geeksforgeeks.org/euclidean-algorithms-basic-and-extended/)是求两个整数的 [GCD(最大公约数)](https://www.geeksforgeeks.org/c-program-find-gcd-hcf-two-numbers/)的有效方法。该算法的时间复杂度为 `O(log(min(a, b)))`。递归地，它可以表示为:

> `gcd(a, b) = gcd(b, a % b)`，
> 其中，`a` 和 `b` 是两个整数。

## 证明

假设 `a` 和 `b` 是两个整数，使得 `a > b`，然后根据欧几里得算法:

> `gcd(a, b) = gcd(b, a % b)`

重复使用上述公式，直到到达步骤 `b` 为 `0`。在这一步，结果将是两个整数的 `GCD`，等于 `a`。所以，仔细观察之后，可以说这个算法的时间复杂度会和将 `b` 减少到 `0` 所需的步数成正比。

让我们假设，使用该算法将 `b` 减少到 `0` 所需的步数是 `N`。

```
gcd(a, b) ------> N steps
```

现在，如果两个数字的欧几里德算法 `a` 和 `b` 在 `N` 步中减少，那么 `a` 应该至少为 `f_(N + 2)`，`b` 应该至少为 `f_(N + 1)`。

> `gcd(a, b) —> N 步`
> 然后，`a >= f_(N + 2)` 和 `b >= f_(N + 1)`
> 其中，`f_N` 是斐波那契数列中的第 `N` 项(0，1，1，2，3，…)，`N >= 0`。

用[数学归纳法](https://www.geeksforgeeks.org/principle-of-mathematical-induction/)的[原理证明上述说法:](https://www.geeksforgeeks.org/principle-of-mathematical-induction/)

### 基本情况

*   假设 `a = 2`，`b = 1`。然后，`gcd(2, 1)` 将在 `1` 步减少到 `gcd(1, 0)`，即 `N = 1`。
*   也就是说 `2` 至少应为 `f_3`，`1` 至少应为 `f_2`。`f_3 = 2` 和 `f_2 = 1`。
*   这就意味着，`a` 至少是 `f_(N+2)`，`b` 至少是 `f_(N + 1)`。
*   可以得出结论，该陈述适用于基本案例。

### 归纳步骤

假设对于 `(N–1)` 第步该陈述成立。因此，以下是第 `N` 步的证明步骤:

> `gcd(b, a % b) —> (N-1)步`
> 然后，
> `b >= f_(N-1+2)` 即 `b >= f_(N+1)`
> `a % b >= f_(N-1+1)` 即 `a % b >= f_N`

*   也可以写成:

> `a = floor(a/b) * b + a % b`

*   现在，`(a/b)` 总是大于 1。所以，从上述结果可以得出结论:

> `a >= b + (a % b)`
> 这意味着，`a >= f_(N + 1) + f_N`

*   众所周知，每个数字都是一个[斐波那契数列](https://www.geeksforgeeks.org/program-for-nth-fibonacci-number/)中前面两项的和。这意味着 `f_(N+2) = f_(N+1) + f_N`。

> `a >= f_(N + 2)` 和 `b >= f_(N + 1)`

*   因为上述陈述同样适用于感应步骤。这证明这个说法是正确的。

## 比奈公式

在继续之前，先看看**比奈公式**:

> `f_n = {((1+√5)/2)^n - ((1-√5)/2)^n} / √5`
> 或
> `f_N ≈ φ^n / √5`

*   其中，`φ` 被称为黄金 `ratio (φ ≈ 1.618)`，`f_N` 是 [N `th` 斐波那契数](https://www.geeksforgeeks.org/find-nth-fibonacci-number-using-golden-ratio/)。
*   现在，已经陈述了时间复杂度将与 `N` 成比例，即，将 `b` 减少到 `0` 所需的步数。
*   所以，为了证明时间复杂性，我们知道:

> `f_n ≈ φ^n / √5`
> `=> n ≈ log_φ(f_n * √5)`

现在，从上面的陈述中，证明了利用数学归纳法的[原理，可以说如果两个数 `a` 和 `b` 的欧几里德算法在 `N 步`中约简，那么 `a` 至少应该是 `f_(N + 2)` 和 `b` 至少应该是 `f_(N + 1)`](https://www.geeksforgeeks.org/mathematics-introduction-to-proofs/)

从以上两个结果可以得出结论:

> `=> f_(n+1) <= min(a, b)`
> `=> (n+1) <= log_φ(min(a, b) * √5)`
> `=> O(N) = O(N+1) = O(log(min(a, b)))`