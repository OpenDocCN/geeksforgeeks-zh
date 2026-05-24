# MySQL 中的 PI()函数

> 原文:[https://www.geeksforgeeks.org/pi-function-in-mysql/](https://www.geeksforgeeks.org/pi-function-in-mysql/)

MySQL 中的 PI() [函数用于返回 PI 值。默认显示的小数位数是 7，但是 MySQL 在内部使用完整的双精度值。](https://www.geeksforgeeks.org/sql-functions-aggregate-scalar-functions/)

**语法:**

```sql
PI()
```

**参数:**
此方法不接受任何参数。

**返回:**
返回圆周率值，即 3.141593。

**示例-1 :**
使用 PI 函数返回 Pi 的默认值。

```sql
SELECT PI() AS DefaultPiValue;

```

**输出:**

| 默认值 |
| --- |
|   3.141593 |

**示例-2 :**

使用 PI 函数返回最多 18 位小数的 Pi 值。

```sql
SELECT PI()+0.000000000000000000 
AS PiValue;

```

**输出:**

| PiValue(价值) |
| --- |
| 3.141592653589793000 |

**例-3 :**
用 PI 函数计算一列中所有圆的面积和周长。为了演示，让我们创建一个名为 Circle 的表。

```sql
CREATE TABLE Circle(
Circle_id INT AUTO_INCREMENT,  
Radius DECIMAL(10, 3) NOT NULL,
PRIMARY KEY(Circle_id )
);

```

现在，向圆形表中插入一些数据。

```sql
INSERT INTO Circle(Radius )
VALUES
(2 ),(3),(10 ),(12.5 ),(6.80),
(4.60 ),(6),(20),(25) ;

```

所以，圆表如下。

```sql
SELECT * FROM Circle;

```

| 圆圈 _id | 半径 |
| --- | --- |
| one | Two |
| Two | Three |
| three | Ten |
| four | Twelve point five |
| five | Six point eight |
| six | Four point six |
| seven | Six |
| eight | Twenty |
| nine | Twenty-five |

现在，我们将使用 PI 函数计算每个圆的面积和周长。

```sql
SELECT Circle_id, Radius,
PI() * Radius * Radius  AS Area,
2 * PI() * Radius AS Perimeter
FROM Circle;

```

**输出:**

| 圆圈 _id | 半径 | 面积 | 周长 |
| --- | --- | --- | --- |
| one | Two | 12.566371 | 12.566371 |
| Two | Three | 28.274334 | 18.849556 |
| three | Ten | 314.159265 | 62.831853 |
| four | Twelve point five | 490.873852 | 78.539816 |
| five | Six point eight | 145.267244 | 42.725660 |
| six | Four point six | 66.476101 | 28.902652 |
| seven | Six | 113.097336 | 37.699112 |
| eight | Twenty | 1256.637061 | 125.663706 |
| nine | Twenty-five | 1963.495408 | 157.079633 |