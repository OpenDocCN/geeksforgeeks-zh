# PL/SQL 中的弗洛伊德三角形

> 原文:[https://www.geeksforgeeks.org/floyds-triangle-in-pl-sql/](https://www.geeksforgeeks.org/floyds-triangle-in-pl-sql/)

**先决条件**–[PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)
在 PL/SQL 中，命令的代码组排列在一个块内。一组相关的声明或语句。在声明部分，我们声明变量，在开始和结束部分之间，我们执行操作。

弗洛伊德的三角形是自然数的直角三角形数组。它是通过用连续的数字填充三角形的行来定义的，从左上角的 1 开始。

给定一个数字范围，任务是形成弗洛伊德的三角形。
**例:**

```sql
Input: 1-29
Output:
 1
 2 3
 4 5 6
 7 8 9 10
 11 12 13 14 15
 16 17 18 19 20 21
 22 23 24 25 26 27 28

```

**下面是需要的实现:**

```sql

--floyd's triangle in PL/SQL 
DECLARE 
    --num, var_num variable declare 
    --num assign 1 
    num     NUMBER := 1; 
    var_num VARCHAR2(200); 
BEGIN 
    --loop  from 1 to 16 
    FOR i IN 1..16 LOOP 
        FOR j IN 1..i LOOP 
            var_num := var_num 
                       ||' ' 
                       ||num; 

            num := num + 1; 

            exit WHEN num = 16; 
        END LOOP; 

        --result print 
        dbms_output.Put_line(var_num); 

        exit WHEN num = 16; 

        var_num := NULL; 
    END LOOP; 
--end lop 
END; 
--end program 
```

**输出:**

```sql
 1
 2 3
 4 5 6
 7 8 9 10
 11 12 13 14 15

```