# LOG()&SQL Server

中的 LOG10()

> 原文:[https://www.geeksforgeeks.org/log-log10-in-sql-server/](https://www.geeksforgeeks.org/log-log10-in-sql-server/)

**LOG()** 函数可以用来计算特定数字的自然对数。

**1。LOG() :**

**语法:**

```sql
SELECT LOG(number);
```

**注意:**参数号为必填项。该数字必须大于 0。

**示例–**

选择日志(2)；
**输出–**

```sql
0.69314718055994529
```

**2。LOG10():**
**LOG10()**函数可用于计算特定数字以 10 为底的自然对数。

**语法:**

```sql
SELECT LOG10(number);
```

**注意:**参数号为必填项。该数字必须大于 0。

**示例–**
选择 LOG10(2)；

**输出–**

```sql
0.3010299956639812
```