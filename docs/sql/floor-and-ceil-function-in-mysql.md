# MySQL 中的 FLOOR()和 CEIL()函数

> 原文:[https://www . geesforgeks . org/floor-and-ceil-function-in-MySQL/](https://www.geeksforgeeks.org/floor-and-ceil-function-in-mysql/)

**1。FLOOR()函数:**
**()函数在 MySQL 中用于返回最大的整数值，该整数值等于或小于给定输入数。**

****语法:****

```sql
FLOOR(X)
```

****参数:**必选。
**X :** 我们要计算其楼层值的数字。
**返回:**返回最接近的整数< =X，所以如果 X 是大于 X 的整数，则返回 X，否则返回小于 X 的最大整数**

****示例-1 :**
将 FLOOR()函数应用于+ve 整数。**

```sql
SELECT FLOOR(4) AS Floor_Value;
```

****输出:****

| 楼层值 |
| --- |
| four |

 ****示例-2 :**
将 FLOOR()函数应用于-ve 整数。**

```sql
SELECT FLOOR(-6) AS Floor_Value;
```

****输出:****

| 楼层值 |
| --- |
| -6 |

 ****示例-3 :**
对+ve 浮点数应用 FLOOR()函数。**

```sql
SELECT FLOOR(1.5) AS Floor_Value;
```

****输出:****

| 楼层值 |
| --- |
| one |

 ****示例-4 :**
对-ve 浮点数应用 FLOOR()函数。**

```sql
SELECT FLOOR(-1.5) AS Floor_Value;
```

****输出:****

| 楼层值 |
| --- |
| -2 |

 ****示例-5 :**
表中数值列的 FLOOR 值。**

****表–**数字**

| X |
| --- |
| Ninety point five five |
| Zero |
| -2 |
| -45.76 |
| Zero point two five |

```sql
SELECT X, FLOOR(X) AS X_Floor FROM Number;
```

****输出:****

| X | 十 _ 楼层 |
| --- | --- |
| Ninety point five five | Ninety |
| Zero | Zero |
| -9 | -9 |
| -45.76 | -46 |
| Zero point two five | Zero |

****2。CEIL()函数:**
MySQL 中的 CEIL()函数用于返回大于或等于给定输入数的最小整数值。**

****语法:****

```sql
CEIL(X)
```

****参数:**必选。
**X :** 我们要计算其上限值的数字。
**返回:**返回最接近的整数> =X，所以如果 X 是大于 X 的整数，则返回 X，否则返回下一个大于 X 的整数**

****示例-1 :**
将 CEIL()函数应用于+ve 整数。**

```sql
SELECT CEIL(5) AS Ceil_Value;
```

****输出:****

| 上限 _ 值 |
| --- |
| five |

 ****示例-2 :**
将 CEIL()函数应用于-ve 整数。**

```sql
SELECT CEIL(-8) AS Ceil_Value;
```

****输出:****

| 上限 _ 值 |
| --- |
| -8 |

 ****示例-3 :**
将 CEIL()函数应用于+ve 浮点数。**

```sql
SELECT CEIL(1.5) AS Ceil_Value;
```

****输出:****

| 上限 _ 值 |
| --- |
| Two |

 ****示例-4 :**
将 CEIL()函数应用于-ve 浮点数。**

```sql
SELECT CEIL(-1.5) AS Ceil_Value;
```

****输出:****

| 上限 _ 值 |
| --- |
| -1 |

 ****示例-5 :**
表中数值列的 CEIL 值。**

****表–**数字**

| X |
| --- |
| Eight point five |
| one |
| Zero |
| -1 |
| -1.5 |

```sql
SELECT X, CEIL(X) AS X_Ceil FROM Number;
```

****输出:****

| X | X _ Ceil |
| --- | --- |
| Eight point five | nine |
| one | one |
| Zero | Zero |
| -1 | -1 |
| -1.5 | -1 |