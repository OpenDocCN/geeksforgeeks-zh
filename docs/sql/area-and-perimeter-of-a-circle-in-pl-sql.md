# PL/SQL 中圆的面积和周长

> 原文:[https://www . geeksforgeeks . org/pl-SQL 中的面积和周长/](https://www.geeksforgeeks.org/area-and-perimeter-of-a-circle-in-pl-sql/)

**先决条件**–[PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)
在 PL/SQL 中，命令的代码组排列在一个块内。一组相关的声明或语句。在声明部分，我们声明变量，在开始和结束部分之间，我们执行操作。

给定圆的半径，任务是找到圆的面积和周长。
**例:**

```sql
Input: 3
Output: Area = 28.26
        Perimeter = 18.84

Input: 7
Output: Area = 153.86
        Perimeter = 43.96

```

圆的面积和周长公式:
**面积:**

```sql
pi * radius * radius 
```

**周长:**

```sql
2 * pi * radius
```

其中 pi = 3.14

以下是所需的实现:

```sql
--Find the area and perimeter of circle
DECLARE 

    -- Variables to store area and perimeter
    area   NUMBER(6, 2)  ;  
    perimeter   NUMBER(6, 2)  ; 

    --Assigning the value of radius 
    radius NUMBER(1) := 3; 

    --Constant value of  PI 
    pi CONSTANT NUMBER(3, 2) := 3.14; 

BEGIN 

        --Formula for area and perimeter of a circle 
        area := pi * radius * radius; 
        perimeter := 2 * pi * radius;
        dbms_output.Put_line('Area = ' || area); 
        dbms_output.Put_line(' Perimeter = ' || perimeter); 

END; 
```

**输出:**

```sql
Area = 28.26
Perimeter = 18.84

```