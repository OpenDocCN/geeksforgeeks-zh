# 排列组的顺序

> 原文:[https://www.geeksforgeeks.org/order-of-permutation-group/](https://www.geeksforgeeks.org/order-of-permutation-group/)

## 排列顺序

对于给定的排列 `P`，如果 `P^n = I` (同一性排列)，那么 `n` 就是排列顺序。

让一个排列 `P=\begin{pmatrix} a & b & c\\ d & d & e \end{pmatrix}` 和 `P^n= I`，那么 `n` 就是排列的顺序。

### 例 1

`\begin{pmatrix} 1 & 2 & 3&4\\ 1 & 3 & 4&2 \end{pmatrix}` 被自身相乘多少次产生 `\begin{pmatrix} 1 & 2 & 3&4\\ 1 & 2 & 3&4 \end{pmatrix}`？

**解：**
让 `P = \begin{pmatrix} 1 & 2 & 3&4\\ 1 & 3 & 4&2 \end{pmatrix}`。

然后 `P^2 = P.P = \begin{pmatrix} 1 & 2 & 3&4\\ 1 & 3 & 4&2 \end{pmatrix}\begin{pmatrix} 1 & 2 & 3&4\\ 1 & 3 & 4&2 \end{pmatrix} = \begin{pmatrix} 1 & 2 & 3&4\\ 1 & 4 & 2&3 \end{pmatrix}`。

`P^3 = P^2 . P = \begin{pmatrix} 1 & 2 & 3&4\\ 1 & 4 & 2&3 \end{pmatrix}\begin{pmatrix} 1 & 2 & 3&4\\ 1 & 3 & 4&2 \end{pmatrix} = \begin{pmatrix} 1 & 2 & 3&4\\ 1 & 2 & 3&4 \end{pmatrix} = I`。

因此所需的数字是 3。

**订单=3**

### 例 2

求排列 `\begin{pmatrix} 1 & 4 & 2&6\\ \end{pmatrix}` 的顺序。

**解：**
让给定的排列为 `P= \begin{pmatrix} 1 & 4 & 2&6\\ \end{pmatrix}`。

我们可以把 `P` 写成 `P= \begin{pmatrix} 1 & 4 & 2&6\\ 4 & 2 & 6&1 \end{pmatrix}`。

`P^2 = \begin{pmatrix} 1 & 4 & 2&6\\ 4 & 2 & 6&1 \end{pmatrix} \begin{pmatrix} 1 & 4 & 2&6\\ 4 & 2 & 6&1 \end{pmatrix} = \begin{pmatrix} 1 & 4 & 2&6\\ 2 & 6 & 1&4 \end{pmatrix}`。

`P^3 = P^2 . P = \begin{pmatrix} 1 & 4 & 2&6\\ 2 & 6 & 1&4 \end{pmatrix}\begin{pmatrix} 1 & 4 & 2&6\\ 4 & 2 & 6&1 \end{pmatrix} = \begin{pmatrix} 1 & 4 & 2&6\\ 6 & 1 & 4&2 \end{pmatrix}`。

`P^4 = P^3 . P = \begin{pmatrix} 1 & 4 & 2&6\\ 6 & 1 & 4&2 \end{pmatrix}\begin{pmatrix} 1 & 4 & 2&6\\ 4 & 2 & 6&1 \end{pmatrix} = \begin{pmatrix} 1 & 4 & 2&6\\ 1 & 4& 2&6 \end{pmatrix}`。

`P^4 = I` (身份置换)。

**因此，顺序为 4。**