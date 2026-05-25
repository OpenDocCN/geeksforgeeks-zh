# 如何在 JavaScript 中计算两个整数 n 和 k 的二项式系数？

> 原文：[https://www.geeksforgeeks.org/how-to-evaluate-binomial-coefficient-of-two-integers-n-and-k-in-javascript/](https://www.geeksforgeeks.org/how-to-evaluate-binomial-coefficient-of-two-integers-n-and-k-in-javascript/)

以下是[二项式系数的常用定义。](http://en.wikipedia.org/wiki/Binomial_coefficient)

一个二项式系数 `C(n, k)` 可以定义为 `(1 + x)^n` 展开式中 `x^k` 的系数。二项式系数 `C(n, k)` 也给出了从 `n` 个对象中选择 `k` 个对象（不考虑顺序）的方式数。更正式地说，它是 `n` 个元素集合的 `k` 个元素子集（或 `k` 个组合）的数量。

## 问题陈述

写一个函数，取两个参数 `n` 和 `k`，返回二项式系数 `C(n, k)` 的值。例如，对于 `n = 4` 和 `k = 2`，您的函数应该返回 `6`；对于 `n = 5` 和 `k = 2`，它应该返回 `10`。

## 方法

下面是创建一个返回两个整数的二项式系数的函数需要遵循的步骤。

*   创建一个参数为 `n` 和 `k` 的函数。
*   现在检查 `n` 和 `k` 是否为数字。如果其中任何一个或两个都不是数字，则返回 `NaN`。
*   现在检查 `k` 是否小于 `0` 或 `k` 是否大于 `n`。如果其中一个条件为真，则返回 `0`。
*   现在检查 `k` 是否等于 `0` 或 `k` 是否等于 `n`。如果其中一个条件为真，则返回 `1`。
*   现在检查 `k` 是否等于 `1` 或 `k` 是否等于 `(n-1)`。如果其中一个条件为真，则返回 `n`。
*   现在编写计算二项式系数的逻辑。

## 示例

```javascript
<script>
  function binomialCoefficient(n, k) {
    // 检查 n 和 k 是否为整数
    if (Number.isNaN(n) || Number.isNaN(k)) {
      return NaN;
    }

    if (k < 0 || k > n) {
      return 0;
    }

    if (k === 0 || k === n) {
      return 1;
    }

    if (k === 1 || k === n - 1) {
      return n;
    }

    let res = n;
    for (let i = 2; i <= k; i++) {
      res *= (n - i + 1) / i;
    }

    return Math.round(res);
  }

  console.log(binomialCoefficient(10, 2));
</script>
```

## 输出

```
45
```