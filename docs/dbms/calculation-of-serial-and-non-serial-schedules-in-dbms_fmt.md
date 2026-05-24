# 数据库管理系统中串行和非串行计划的计算

> 原文: [https://www.geeksforgeeks.org/calculation-of-serial-and-non-serial-schedules-in-dbms/](https://www.geeksforgeeks.org/calculation-of-serial-and-non-serial-schedules-in-dbms/)

事务的连续执行被定义为调度。它由许多事务组成，每个事务由许多指令组成。

## 调度类型

*   串行计划
*   非串行计划

## 计划数的计算

考虑有 `N` 个交易 `T1`、`T2`、`T3`、…、`TN`，分别带有 `k1`、`k2`、`k3`、…、`kN` 次操作。

1.  **计划总数**

    ```
    (N1 + N2 + N3 + ..... + Nn)! / (N1! * N2! * N3! * ... * Nn!)
    ```

2.  **串行时间表的数量**

    ```
    It is all possible permutations of n transactions = N!
    ```

3.  **非串行计划数量**

    总计划 = 串行计划 + 非串行计划
    非串行计划数量 = 计划总数 – 串行计划数量

    ```
    ((N1 + N2 + N3 + ..... + Nn)! / (N1! * N2! * N3! * ... * Nn!)) - (N!)
    ```

## 示例

假设有三个交易，分别有 1、2 和 3 个操作。
我们必须找到：

*   可能的计划总数。
*   可能的串行计划和非串行计划的总数。

### 解决方案

计划总数：

```
= (1 + 2 + 3)! / (1! * 2! * 3!) = 6! / (1 * 2 * 6) = 720 / 12 = 60
```

串行计划数量：

```
= 3! = 6
```

非串行计划数量：

```
= 计划总数 - 串行计划数量
= 60 - 6
= 54
```