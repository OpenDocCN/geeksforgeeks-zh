# MySQL 中的 POWER()函数

> 原文:[https://www.geeksforgeeks.org/power-function-in-mysql/](https://www.geeksforgeeks.org/power-function-in-mysql/)

**POWER** ()函数在 MySQL 中用来求一个数的值升到另一个数的幂。它返回 X 的值乘以 y 的幂

**语法:**

```sql
POWER(X, Y)

```

**参数:**该方法接受两个参数，描述如下:

*   **X:** Specify the cardinality.
*   **Y:** Specify the index number.

**返回:**返回 X 的值乘以 y 的幂

**示例-1 :** 使用幂()函数求基数和指数都为正时的幂值。

```sql
SELECT POWER( 5, 4) AS Power_Value ;

```

**输出:**T5】

| power _ Value |
| --- |
| 625 |

**示例-2 :** 使用 Power()函数求基数和为正但指数为负时的幂值。

```sql
SELECT POWER( 2, -4) AS Power_Value ;

```

**输出:**T5】

| power _ Value |
| --- |
| 0.0625 |

**示例-3 :** 使用 Power()函数，当基数和为负但指数为正时，求幂值。

```sql
SELECT POWER( -3, 3) AS Power_Value ;

```

**输出:**

| power _ Value |
| --- |
| -27 |

**示例-4 :** 使用幂()函数求基数和指数都为负时的幂值。

```sql
SELECT POWER( -3, -4) AS Power_Value ;

```

**输出:**

| power _ Value |
| --- |
| 0.012345679012345678 |

**例-5:**POWER 函数也可以用来求列数据之间的幂值。演示创建一个名为。

**三角形。**

```sql
CREATE TABLE Triangle(

    Type VARCHAR(25) NOT NULL,
    NoOfSides INT NOT NULL,
    Base INT NOT NULL,
    Height INT NOT NULL
);

```

现在在三角形表中插入一些数据:

```sql
INSERT INTO  
    Triangle(Type, NoOfSides, Base, Height )
VALUES
    ('Right-angled Triangle', 3, 4, 3  ),
    ('Right-angled Triangle', 3, 2, 5  ),
    ('Right-angled Triangle', 3, 1, 7  ),
    ('Right-angled Triangle', 3, 7, 9  ),
    ('Right-angled Triangle', 3, 4, 6  ),
    ('Right-angled Triangle', 3, 8, 3  ),
    ('Right-angled Triangle', 3, 10, 10  ) ;

```

显示三角表–

```sql
Select * from Triangle ;

```

T27】2T31 T62T67】8T69】3T73】直角三角形 T75】3【T77

| type | NoOfSides | 基础 | 高度 |
| --- | --- | --- | --- |
| right triangle | three | four | three |
| right triangle | three | five |
| right triangle | three | four | six |
| right triangle | three |

现在，我们要找到每个直角三角形的斜边和面积。

```sql
SELECT 
    *,
    sqrt(POWER(Base, 2) + POWER(Height, 2))  AS Hypotenuse,
    0.5 * Base * Height as Area  
FROM Triangle;    

```

**输出:** T18】直角三角形T24】3T28】6.0T77

| type | NoOfSides | base | height | hypotenuse | area |
| --- | --- | --- | --- | --- | --- |
| three | four | five |
|  | 7.0710678118654755 | Three point five |
| right triangle | three | seven | nine | 11.40175425099138 | Thirty-one point five |