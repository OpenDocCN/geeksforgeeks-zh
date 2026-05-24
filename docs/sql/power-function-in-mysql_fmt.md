# MySQL 中的 POWER() 函数

> 原文: [https://www.geeksforgeeks.org/power-function-in-mysql/](https://www.geeksforgeeks.org/power-function-in-mysql/)

`POWER()` 函数在 MySQL 中用来求一个数的值升到另一个数的幂。它返回 X 的值乘以 y 的幂。

### 语法

```sql
POWER(X, Y)
```

### 参数

该方法接受两个参数，描述如下：

*   `X`: Specify the cardinality.
*   `Y`: Specify the index number.

### 返回

返回 X 的值乘以 y 的幂。

## 示例-1

使用 `POWER()` 函数求基数和指数都为正时的幂值。

```sql
SELECT POWER( 5, 4) AS Power_Value ;
```

输出：

| Power_Value |
| --- |
| 625 |

## 示例-2

使用 `POWER()` 函数求基数和为正但指数为负时的幂值。

```sql
SELECT POWER( 2, -4) AS Power_Value ;
```

输出：

| Power_Value |
| --- |
| 0.0625 |

## 示例-3

使用 `POWER()` 函数，当基数和为负但指数为正时，求幂值。

```sql
SELECT POWER( -3, 3) AS Power_Value ;
```

输出：

| Power_Value |
| --- |
| -27 |

## 示例-4

使用 `POWER()` 函数求基数和指数都为负时的幂值。

```sql
SELECT POWER( -3, -4) AS Power_Value ;
```

输出：

| Power_Value |
| --- |
| 0.012345679012345678 |

## 示例-5

`POWER()` 函数也可以用来求列数据之间的幂值。演示创建一个名为 `Triangle` 的表。

```sql
CREATE TABLE Triangle(
    Type VARCHAR(25) NOT NULL,
    NoOfSides INT NOT NULL,
    Base INT NOT NULL,
    Height INT NOT NULL
);
```

现在在 `Triangle` 表中插入一些数据：

```sql
INSERT INTO Triangle(Type, NoOfSides, Base, Height )
VALUES
    ('Right-angled Triangle', 3, 4, 3  ),
    ('Right-angled Triangle', 3, 2, 5  ),
    ('Right-angled Triangle', 3, 1, 7  ),
    ('Right-angled Triangle', 3, 7, 9  ),
    ('Right-angled Triangle', 3, 4, 6  ),
    ('Right-angled Triangle', 3, 8, 3  ),
    ('Right-angled Triangle', 3, 10, 10  ) ;
```

显示 `Triangle` 表：

```sql
Select * from Triangle ;
```

| Type | NoOfSides | Base | Height |
| --- | --- | --- | --- |
| Right-angled Triangle | 3 | 4 | 3 |
| Right-angled Triangle | 3 | 2 | 5 |
| Right-angled Triangle | 3 | 1 | 7 |
| Right-angled Triangle | 3 | 7 | 9 |
| Right-angled Triangle | 3 | 4 | 6 |
| Right-angled Triangle | 3 | 8 | 3 |
| Right-angled Triangle | 3 | 10 | 10 |

现在，我们要找到每个直角三角形的斜边和面积。

```sql
SELECT 
    *,
    sqrt(POWER(Base, 2) + POWER(Height, 2))  AS Hypotenuse,
    0.5 * Base * Height as Area  
FROM Triangle;
```

输出：

| Type | NoOfSides | Base | Height | Hypotenuse | Area |
| --- | --- | --- | --- | --- | --- |
| Right-angled Triangle | 3 | 4 | 3 | 5.0 | 6.0 |
| Right-angled Triangle | 3 | 2 | 5 | 5.385164807134504 | 5.0 |
| Right-angled Triangle | 3 | 1 | 7 | 7.0710678118654755 | 3.5 |
| Right-angled Triangle | 3 | 7 | 9 | 11.40175425099138 | 31.5 |
| Right-angled Triangle | 3 | 4 | 6 | 7.211102550927978 | 12.0 |
| Right-angled Triangle | 3 | 8 | 3 | 8.54400374531753 | 12.0 |
| Right-angled Triangle | 3 | 10 | 10 | 14.142135623730951 | 50.0 |