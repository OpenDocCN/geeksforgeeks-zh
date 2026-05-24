# MySQL 中的 DEGREES()函数

> 原文:[https://www.geeksforgeeks.org/degrees-function-in-mysql/](https://www.geeksforgeeks.org/degrees-function-in-mysql/)

**DEGREES()** 函数在 MySQL 中用于将弧度值转换为度数。弧度到度数的转换公式为:

```sql
π radian = 180 degrees 

```

**语法:**

```sql
DEGREES(X)

```

**参数:**此方法只接受一个参数。
**X :** 我们换算成度数的弧度值。
**返回:**以度为单位返回等值弧度值。

**示例-1 :** 使用 DEGREES 函数查找 0 弧度的度数值。

```sql
SELECT DEGREES(0) AS Degree_Value;

```

**输出:**

| 度值 |
| --- |
| Zero |

**示例-2 :** 使用 DEGREES 函数求 3.141592653589793 弧度的度数值。

```sql
SELECT DEGREES(3.141592653589793) AS Degree_Value;

```

**输出:**

| 度值 |
| --- |
| one hundred and eighty  |

**示例-3 :** 使用 DEGREES 函数求-1.5707963267948966 弧度的度数值。

```sql
SELECT DEGREES(-1.5707963267948966 ) AS Degree_Value;

```

**输出:**

| 度值 |
| --- |
| -90 |

**示例-4 :** 使用 RADIANS 函数将列数据的弧度转换为度数。为了演示，让我们创建一个名为多边形的表。

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
('Triangle', 3, 3.141592653589793, 1.0471975511965976),
('Quadrilateral', 4, 6.283185307179586, 1.5707963267948966),
('Pentagon', 5, 9.42477796076938, 1.8849555921538759),
('Hexagon', 6, 12.566370614359172, 2.0943951023931953),
('Heptagon', 7, 15.707963267948966, 2.2439698192891093),
('Octagon', 8, 18.84955592153876, 2.356194490192345),
('Nonagon', 9, 21.991148575128552, 2.443460952792061),
('Decagon', 10, 25.132741228718345, 2.5132741228718345);

```

因此，多边形表是–

```sql
SELECT * FROM Polygon;

```

| 形状 | 侧面 | 内角之和 | 每个角度 |
| --- | --- | --- | --- |
| 三角形 | three | 3.14159265358979300000 | 1.0471975511965976 |
| 四边形 | four | 6.28318530717958600000 | 1.5707963267948966 |
| 五边形 | five | 9.42477796076938 | 1.8849555921538759 |
| 六边形 | six | 12.566370614359172 | 2.0943951023931953 |
| 七边形 | seven | 15.707963267948966 | 2.2439698192891093 |
| 八角形 | eight | 18.84955592153876 | 2.356194490192345 |
| 九边形 | nine | 21.991148575128552 | 2.443460952792061 |
| 十边形 | Ten | 25.132741228718345 | 2.5132741228718345 |

我们可以看到内角和多边形的每个角都是以弧度给出的。现在我们将在 DEVELOPES 函数的帮助下把这些转换成度数。

```sql
SELECT Shape, Sides, 
DEGREES(Sum_of_Interior_Angles) AS Sum_of_Interior_Angles_InDegree, 
DEGREES(Each_Angle) AS Each_Angle_InDegree
FROM Polygon;

```

**输出:**

| 形状 | 侧面 | 内角内角之和 | 每一个角度 |
| --- | --- | --- | --- |
| 三角形 | three | one hundred and eighty  | 59.99999999999999 |
| 四边形 | four | Three hundred and sixty | Ninety |
| 五边形 | five | Five hundred and forty | One hundred and eight |
| 六边形 | six | Seven hundred and twenty | 119.99999999999999 |
| 七边形 | seven | Nine hundred | One hundred and twenty-eight point five seven |
| 八角形 | eight | One thousand and eighty | One hundred and thirty-five |
| 九边形 | nine | One thousand two hundred and sixty | One hundred and forty |
| 十边形 | Ten | One thousand four hundred and forty | One hundred and forty-four |

所以，这里所有内角之和，和每个角都换算成等价度值。