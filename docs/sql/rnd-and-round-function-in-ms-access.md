# MS 接入中的 Rnd()和 Round 函数

> 原文:[https://www . geesforgeks . org/rnd-and-round-function-in-ms-access/](https://www.geeksforgeeks.org/rnd-and-round-function-in-ms-access/)

**1。函数的作用是:返回随机数，如果我们想生成一个 0 到 1 之间的数字，那么只使用 Rnd。否则，如果我们想要生成一个介于一个范围之间的数字，那么我们将使用公式 Int((upper bound–lower bound+1)* Rnd+lower bound)。**

**语法:**

*   **如果我们想生成 0 到 1 之间的–**

    ```sql
    Rnd 
    ```

*   **如果我们想在一个范围内生成–**

    ```sql
    Int((upperbound - lowerbound + 1) * Rnd + lowerbound) 
    ```

**示例-1 :**

```sql
SELECT Int ((10 - 1 + 1) * Rnd + 1) AS RandNumBetween1and10;
```

**输出–**

| **随机数介于 1 和 10 之间** |
| eight |

**示例-2 :**

```sql
SELECT Rnd AS RandNumBetween0and1;
```

**输出–**

| **随机数介于 0 和 1 之间** |
| 0.705547511577606 |

**2。Round()函数:**
Round()函数将一个数字舍入到指定的小数位数。在这个函数中，我们将传递一个表达式，第二个参数将是小数位，直到数字被舍入。

**注意:**
如果数字以 5 结尾，则该函数将最后几个数字四舍五入为偶数。

**语法:**

```sql
Round(expression, decimal_places)
```

**示例-1 :**

```sql
SELECT Round(23.67, 1) As round;
```

**输出–**

| **轮** |
| Twenty-three point seven |

**示例-2 :**

```sql
SELECT Round(45.65, 1) As round;
```

**输出–**

| **轮** |
| Forty-five point six |