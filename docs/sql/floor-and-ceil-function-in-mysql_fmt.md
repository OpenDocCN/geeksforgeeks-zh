# MySQL 中的 `FLOOR()` 和 `CEIL()` 函数

> 原文: [https://www.geeksforgeeks.org/floor-and-ceil-function-in-mysql/](https://www.geeksforgeeks.org/floor-and-ceil-function-in-mysql/)

## 1. `FLOOR()` 函数

`FLOOR()` 函数在 MySQL 中用于返回最大的整数值，该整数值等于或小于给定输入数。

### 语法

```sql
FLOOR(X)
```

### 参数

必选。
`X`：我们要计算其楼层值的数字。

### 返回

返回最接近的整数 `<= X`，所以如果 `X` 是整数，则返回 `X`，否则返回小于 `X` 的最大整数。

### 示例-1

将 `FLOOR()` 函数应用于正整数。

```sql
SELECT FLOOR(4) AS Floor_Value;
```

### 输出

| Floor_Value |
| --- |
| 4 |

### 示例-2

将 `FLOOR()` 函数应用于负整数。

```sql
SELECT FLOOR(-6) AS Floor_Value;
```

### 输出

| Floor_Value |
| --- |
| -6 |

### 示例-3

对正浮点数应用 `FLOOR()` 函数。

```sql
SELECT FLOOR(1.5) AS Floor_Value;
```

### 输出

| Floor_Value |
| --- |
| 1 |

### 示例-4

对负浮点数应用 `FLOOR()` 函数。

```sql
SELECT FLOOR(-1.5) AS Floor_Value;
```

### 输出

| Floor_Value |
| --- |
| -2 |

### 示例-5

表中数值列的 `FLOOR` 值。

**表：** `Number`

| X |
| --- |
| 90.55 |
| 0 |
| -9 |
| -45.76 |
| 0.25 |

```sql
SELECT X, FLOOR(X) AS X_Floor FROM Number;
```

### 输出

| X | X_Floor |
| --- | --- |
| 90.55 | 90 |
| 0 | 0 |
| -9 | -9 |
| -45.76 | -46 |
| 0.25 | 0 |

## 2. `CEIL()` 函数

MySQL 中的 `CEIL()` 函数用于返回大于或等于给定输入数的最小整数值。

### 语法

```sql
CEIL(X)
```

### 参数

必选。
`X`：我们要计算其上限值的数字。

### 返回

返回最接近的整数 `>= X`，所以如果 `X` 是整数，则返回 `X`，否则返回下一个大于 `X` 的整数。

### 示例-1

将 `CEIL()` 函数应用于正整数。

```sql
SELECT CEIL(5) AS Ceil_Value;
```

### 输出

| Ceil_Value |
| --- |
| 5 |

### 示例-2

将 `CEIL()` 函数应用于负整数。

```sql
SELECT CEIL(-8) AS Ceil_Value;
```

### 输出

| Ceil_Value |
| --- |
| -8 |

### 示例-3

将 `CEIL()` 函数应用于正浮点数。

```sql
SELECT CEIL(1.5) AS Ceil_Value;
```

### 输出

| Ceil_Value |
| --- |
| 2 |

### 示例-4

将 `CEIL()` 函数应用于负浮点数。

```sql
SELECT CEIL(-1.5) AS Ceil_Value;
```

### 输出

| Ceil_Value |
| --- |
| -1 |

### 示例-5

表中数值列的 `CEIL` 值。

**表：** `Number`

| X |
| --- |
| 8.5 |
| 1 |
| 0 |
| -1 |
| -1.5 |

```sql
SELECT X, CEIL(X) AS X_Ceil FROM Number;
```

### 输出

| X | X_Ceil |
| --- | --- |
| 8.5 | 9 |
| 1 | 1 |
| 0 | 0 |
| -1 | -1 |
| -1.5 | -1 |