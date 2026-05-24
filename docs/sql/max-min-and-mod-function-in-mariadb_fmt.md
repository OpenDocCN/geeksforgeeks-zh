# MariaDB中的MAX()、MIN()和MOD()函数

> 原文：[https://www.geeksforgeeks.org/max-min-and-mod-function-in-mariadb/](https://www.geeksforgeeks.org/max-min-and-mod-function-in-mariadb/)

## 1. MAX()函数
在MariaDB中，`MAX()`函数用于返回表达式的最大值。在这个函数中，传递一个查询，在符合条件的记录中，哪个值最大，将返回一个结果。它在已处理的查询中像最大函数一样工作。表达式将作为参数传递，并将返回表达式中的最大值。

### 语法
```sql
MAX(expression)
```

### 参数
必选。一个表达式。

### 表达式
输入值。

### 返回
表达式中的最大值。

表：`IPL`

| 团队ID | 团队名称 | 得分 |
| :--- | :--- | :--- |
| one | 乡邮投递路线 | 140 |
| Two | 码移键控 | 210 |
| three | 大调音阶的第三音 | 160 |
| four | 直流电 | 170 |

### 示例-1
```sql
SELECT MAX(Score) AS MAX_Score
FROM IPL;
```

**输出：**

| MAX_Score |
| :--- |
| 210 |

### 示例-2
```sql
SELECT MAX(Score) AS MAX_Score
FROM IPL
WHERE Score < 190;
```

**输出：**

| MAX_Score |
| :--- |
| 170 |

### 示例-3
```sql
SELECT MAX(Score) AS MAX_Score
FROM IPL
WHERE Score < 160;
```

**输出：**

| MAX_Score |
| :--- |
| 140 |

## 2. MIN()函数
在MariaDB中，`MIN()`函数用于返回表达式的最小值。在这个函数中，传递一个查询，在符合条件的记录中，哪个值是最小值，将返回一个结果。它的工作方式类似于已处理查询中的最小函数。表达式将作为参数传递，并将返回表达式中的最小值。

### 语法
```sql
MIN(expression)
```

### 参数
必选。一个表达式。

### 表达式
输入值。

### 返回
表达式中的最小值。

### 示例-1
```sql
SELECT MIN(Score) AS Min_Score
FROM IPL;
```

**输出：**

| Min_Score |
| :--- |
| 140 |

### 示例-2
```sql
SELECT MIN(Score) AS Min_Score
FROM IPL
WHERE Score > 150;
```

**输出：**

| Min_Score |
| :--- |
| 160 |

### 示例-3
```sql
SELECT MIN(Score) AS Min_Score
FROM IPL
WHERE Score > 170;
```

**输出：**

| Min_Score |
| :--- |
| 210 |

## 3. MOD()函数
在MariaDB中，`MOD()`函数用于返回`n`除以`m`的余数。在这个函数中，将传递两个参数，第一个是`n`（一个将被`m`除的值），第二个是`m`（一个将被`n`除的值）。该函数使用`n / m`公式，并返回没有任何舍入的余数。

### 语法
```sql
MOD(n, m)
-- 或者
n MOD m
-- 或者
n % m
```

### 参数
必选。两个数值。

*   **n**：分数值（将被划分的值）。
*   **m**：除数（被除数除以的值）。

### 返回
作为除法结果的余数值（没有任何舍入）。

### 示例-1
```sql
SELECT MOD(20, 5);
```

**输出：**
```sql
0
```

### 示例-2
```sql
SELECT 21 MOD 4;
```

**输出：**
```sql
1
```

### 示例-3
```sql
SELECT 51 % 7;
```

**输出：**
```sql
2
```