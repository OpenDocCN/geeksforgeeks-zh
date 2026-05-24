# 进行竞争性编程时需要重点关注的点

> 原文: [https://www.geeksforgeeks.org/points-to-focus-on-while-doing-competitive-programming/](https://www.geeksforgeeks.org/points-to-focus-on-while-doing-competitive-programming/)

[竞争性编程](https://www.geeksforgeeks.org/category/competitive-programming/)对于一个人在编码领域的发展至关重要。这篇文章将讨论一些在比赛中应该记住的基本要点。

*   制作一个函数列表来执行问题中经常遇到的任务，并以[模板](https://www.geeksforgeeks.org/templates-cpp/)的形式将其添加到您的代码中。这可以节省竞赛时间，并有助于快速提交解决方案。模板中需要添加的一些有价值的功能如下:
    *   [幂函数](https://www.geeksforgeeks.org/modular-exponentiation-power-in-modular-arithmetic/) (`a^N %M`，其中 `a`、`b`、`N` 为整数，`M` 为[素数](https://www.geeksforgeeks.org/prime-numbers/))
    *   [打印质因数](https://www.geeksforgeeks.org/print-all-prime-factors-of-a-given-number/)
    *   [打印质数](https://www.geeksforgeeks.org/sieve-of-eratosthenes/)
    *   [使用 mod 查找 nCr 的功能](https://www.geeksforgeeks.org/compute-ncr-p-set-3-using-fermat-little-theorem/)
    *   [计算 GCD 的功能](https://www.geeksforgeeks.org/c-program-find-gcd-hcf-two-numbers/)
*   在思考解决问题的方法时，关注约束。基于约束，通过计算方法的[时间复杂度](https://www.geeksforgeeks.org/knowing-the-complexity-in-competitive-programming/)，检查设计的解决方案是否能够通过所有的测试用例。
*   只有约束足够小(比如说 `2^N`)不超过时间限制的情况下，才能想到[位掩码](https://www.geeksforgeeks.org/bitmasking-and-dynamic-programming-set-1-count-ways-to-assign-unique-cap-to-every-person/)或者[蛮力](https://www.geeksforgeeks.org/most-important-type-of-algorithms/)。因此，该方法应该包括检查所有可能的结果组合。
*   如果有一个问题涉及到输入形式的排序数据，那么考虑一个使用[二分搜索法](https://www.geeksforgeeks.org/binary-search/)的方法。
*   如果有与[树](https://www.geeksforgeeks.org/binary-tree-data-structure/)、[图](https://www.geeksforgeeks.org/graph-and-its-representations/) ( [循环检测](https://www.geeksforgeeks.org/detect-cycle-in-a-graph/))等相关的问题，养成一种思维定势，想出一种围绕[深度优先搜索](https://www.geeksforgeeks.org/depth-first-search-or-dfs-for-a-graph/)或[广度优先搜索](https://www.geeksforgeeks.org/breadth-first-search-or-bfs-for-a-graph/)的方法，这是解决这类问题的基本要求。
*   [数论](https://www.geeksforgeeks.org/number-theory-competitive-programming/):
    *   两个或两个以上奇数素数的相加将始终是偶数(例如 `13 + 3 = 16`，`19 + 5 = 24`)。
    *   [哥德巴赫猜想](https://www.geeksforgeeks.org/program-for-goldbachs-conjecture-two-primes-with-given-sum/)是数学(更精确地说是数论)中众所周知的未解问题之一。注: 对于较大的数不证明。
    *   数论中还有其他几个概念需要掌握才能做好 CP。
*   如果一个状态依赖于未来状态，那么用[贪婪解](https://www.geeksforgeeks.org/greedy-algorithms/)解决问题是不可能的。此外，不能采用幼稚的方法，因为它会超过时间限制。因此，对于所有此类问题，请始终尝试使用[动态规划](https://www.geeksforgeeks.org/dynamic-programming/)解决方案。
    如果一个人能写出一个简单的[递归解](https://www.geeksforgeeks.org/recursion/)就非常简单了，这个解以指数复杂度运行。将访问过的每条路径存储在内存中，以便以后用于解决问题，这称为[记忆](https://www.geeksforgeeks.org/memoization-1d-2d-and-3d/)。一旦学习了记忆方法，逐渐学习[制表方法](https://www.geeksforgeeks.org/tabulation-vs-memoization/)。
*   如果有一个问题与[位运算符](https://www.geeksforgeeks.org/bitwise-operators-in-c-cpp/)如 `XOR`、`OR` 和 `AND` 相关，并且可以通过这些操作改变数组，那么有时朴素方法会起作用，因为最多只有 **64** 个具有不同最高有效位的数字 (`2^64`)。但在这个方法中，主要任务是确定基本情况。
    让我们举个例子，给定一个按升序排序的数组，任务是通过用两个相邻元素的**按位异或**替换它们，使数组变为非递增，要求操作次数最少。

    > **输入:** `arr[] = {2, 5, 6, 8}`
    > **输出:** `1`
    > **解释:**
    > **操作 1:** 选择元素 `2` 和 `5`，用 `2⊕5 = 7` 替换 `2`。
    > 现在，数组将为 `{7, 6, 8}`，不递增。
    > 因此，操作计数为 `1`。

    **方法:** 这个也可以用天真的方法解决，即找到一个子数组，它的 `XOR` 小于子数组起点前的元素，或者小于子数组终点后的元素。

    但是，在处理基本情况之前，即如果存在 3 个连续元素，则 `MSB` 是相同的(例如 `arr[i-1]`、`arr[i]`、`arr[i+1]` 的 `MSB` 相同)，然后通过用 `arr[i] ⊕ arr[i + 1]` 替换它来获得结果。

    所以，对于天真的阵中进场只有当 `N > 60` 因为 `2*(⌊log_2 10^9⌋+1)= 60`。(Let，`a[i] <= 10^9`)。乘以 `2`，因为这是唯一可能的最后一种情况。如果乘以 `3`，那么肯定会有 `3` 个连续元素具有相同的 `MSB`(最高有效位)。
*   数组元素的[GCD](https://www.geeksforgeeks.org/gcd-two-array-numbers/)也可以表示为:

    > `gcd(a_1, a_2, ⋯, a_{n-2}, a_{n-1}, a_n) = gcd(a_1, a_2-a_1, ⋯, a_{n-1}-a_{n-2}, a_n-a_{n-1})`

    **证明:**

    > `gcd(a, b) = gcd(a, b-a)`
    > `gcd(a, b, c) = gcd(a, gcd(b, c)) = gcd(gcd(a, b), c)`
    > 那么，可以概括为:
    > `gcd(a_1, a_2, ⋯, a_{n-1}, a_n) = gcd(a_1, a_n)`
    > `= gcd(a_1, a_2, ⋯, a_{n-2}, gcd(a_{n-1}, a_n-a_{n-1}))`
    > `= gcd(a_1, a_2, ⋯, gcd(a_{n-2}, a_{n-1}-a_{n-2}, a_n-a_{n-1}))`
    > `= gcd(a_1, a_2, ⋯, gcd(a_{n-2}, a_{n-1}-a_{n-2}, a_n-a_{n-1}))`
*   一些最常用的**位运算符**属性可以是:
    *   `a - b = a | b - a 和 b`
    *   `a + b = a - b + 2 * (a 和 b)`
    *   `a + b = a | b + a & b`

这里的 `a` 和 `b` 是整数，`⊕` 表示 `XOR`，`&` 表示 `AND`，`|` 表示 `OR`。