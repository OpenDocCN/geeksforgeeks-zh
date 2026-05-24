# 在 PL/SQL 中求直角三角形的面积和周长

> 原文:[https://www . geeksforgeeks . org/find-面积和周长的直角三角形 in-pl-sql/](https://www.geeksforgeeks.org/find-the-area-and-perimeter-of-right-triangle-in-pl-sql/)

**先决条件**–[PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)

在 PL/SQL 代码中，命令组排列在一个块中。一组相关的声明或语句。在声明部分，我们声明变量，在开始和结束部分之间，我们执行操作。

给定直角三角形的斜边、底边和高度，任务是找出三角形的面积和周长。

示例:

```sql
Input: hypotenuse = 10, base = 4, height = 14
Output:  Area = 28, Perimeter = 28
Input: hypotenuse = 30,  base = 10, height = 25
Output: Area = 125, Perimeter = 65

```

面积和周长计算公式:
**直角三角形面积:**

```sql
 1/2 * base * height
```

**三角形周长:**

```sql
len of hypotenuse + len of base + len of height
```

以下是所需的实现:

```sql
DECLARE
    -- declare variable side1, side2,
    -- base, height, area and perimeter
    -- and these six variable datatype
    -- are float
    hypotenuse     FLOAT;
    base      FLOAT;
    height    FLOAT;
    area      FLOAT;
    perimeter FLOAT;
BEGIN
    -- here we assign the value in
    -- side1, side2, base, height  
    hypotenuse := 10;

    base := 4;

    height := 14;

    area := .5 * base * height;

    perimeter := hypotenuse + height + base;

    dbms_output.Put_line(' Area of triangle is '
                         || area);

    dbms_output.Put_line(' Perimeter of triangle is '
                         || perimeter);
END;
-- Program End 
```

**输出:**

```sql
 Area of triangle is 28
 Perimeter of triangle is 28

```