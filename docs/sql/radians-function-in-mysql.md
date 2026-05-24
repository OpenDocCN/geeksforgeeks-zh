# MySQL 中的 RADIANS()函数

> 原文:[https://www.geeksforgeeks.org/radians-function-in-mysql/](https://www.geeksforgeeks.org/radians-function-in-mysql/)

**弧度()**函数在 MySQL 中用于将度数值转换为弧度。度数转换为弧度的公式为:

```sql
180 degrees = π radian
```

**语法:**

```sql
RADIANS(X)
```

**参数:**此方法只接受一个参数。
**X :** 我们换算成弧度的度数值。
**返回:**返回弧度的等值度数。

**示例-1 :**
使用弧度函数求 0 度的弧度值。

```sql
SELECT RADIANS(0) AS Radian_Value;
```

**输出:**

| 弧度 _ 值 |
| --- |
| Zero |

**示例-2 :**
使用弧度函数寻找 180 度的弧度值。

```sql
SELECT RADIANS(180) AS Radian_Value;
```

**输出:**

| 弧度 _ 值 |
| --- |
| 3.141592653589793 |

**示例-3 :**
使用弧度函数查找-90 度的弧度值。

```sql
SELECT RADIANS(-90) AS Radian_Value;
```

**输出:**

| 弧度 _ 值 |
| --- |
| -1.5707963267948966 |

**示例-4 :**
使用弧度函数将弧度从度数转换为列数据。为了演示，让我们创建一个名为多边形的表。

```sql
CREATE TABLE Polygon (
Shape VARCHAR(100) NOT NULL,
Sides INT NOT NULL,
Sum_of_Interior_Angles DECIMAL(10, 2) NOT NULL,
Each_Angle DECIMAL(10, 2) NOT NULL,
PRIMARY KEY(Sides)
);
```

现在，向多边形表中插入一些数据–

```sql
INSERT INTO  
Polygon(Shape, Sides, Sum_of_Interior_Angles, Each_Angle)
VALUES
('Triangle', 3, 180, 60),
('Quadrilateral', 4, 360, 90),
('Pentagon', 5, 540, 108),
('Hexagon', 6, 720, 120),
('Heptagon', 7, 900, 128.57),
('Octagon', 8, 1080, 135),
('Nonagon', 9, 1260, 140),
('Decagon', 10, 1440, 144);
```

因此，多边形表是–

```sql
SELECT * FROM Polygon;
```

| 形状 | 侧面 | 内角之和 | 每个角度 |
| --- | --- | --- | --- |
| 三角形 | three | One hundred and eighty | Sixty |
| 四边形 | four | Three hundred and sixty | Ninety |
| 五边形 | five | Five hundred and forty | One hundred and eight |
| 六边形 | six | Seven hundred and twenty | One hundred and twenty |
| 七边形 | seven | Nine hundred | One hundred and twenty-eight point five seven |
| 八角形 | eight | One thousand and eighty | One hundred and thirty-five |
| 九边形 | nine | One thousand two hundred and sixty | One hundred and forty |
| 十边形 | Ten | One thousand four hundred and forty | One hundred and forty-four |

我们可以看到内角和多边形的每个角都是以度数给出的。现在我们将在 RADIAN 函数的帮助下把这些转换成弧度。

```sql
SELECT Shape, Sides, 
RADIANS(Sum_of_Interior_Angles) AS Sum_of_Interior_Angles_InRadian, 
RADIANS(Each_Angle) AS Each_Angle_InRadian
FROM Polygon;
```

**输出:**

| 形状 | 侧面 | _ 内角之和 _ 径向 | 每一个角度 |
| --- | --- | --- | --- |
| 三角形 | three | 3.141592653589793 | 1.0471975511965976 |
| 四边形 | four | 6.283185307179586 | 1.5707963267948966 |
| 五边形 | five | 9.42477796076938 | 1.8849555921538759 |
| 六边形 | six | 12.566370614359172 | 2.0943951023931953 |
| 七边形 | seven | 15.707963267948966 | 2.2439698192891093 |
| 八角形 | eight | 18.84955592153876 | 2.356194490192345 |
| 九边形 | nine | 21.991148575128552 | 2.443460952792061 |
| 十边形 | Ten | 25.132741228718345 | 2.5132741228718345 |

所以，这里一个内角的和，和每个角都转换成等价的弧度值。