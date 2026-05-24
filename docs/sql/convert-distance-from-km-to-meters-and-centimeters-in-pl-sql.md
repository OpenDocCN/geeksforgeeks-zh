# PL/SQL 中公里到米厘米的转换距离

> 原文:[https://www . geesforgeks . org/convert-从千米到米和厘米的距离-in-pl-sql/](https://www.geeksforgeeks.org/convert-distance-from-km-to-meters-and-centimeters-in-pl-sql/)

**先决条件**–[PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)
在 PL/SQL 中，命令的代码组排列在一个块内。一组相关的声明或语句。在声明部分，我们声明变量，在开始和结束部分之间，我们执行操作。
以公里为单位给定距离，任务是将其转换为米和厘米。
**举例:**

```sql
Input: KM = 10
Output: 10 KM is equivalent to 10000 meters
        10 KM is equivalent to 1000000 centimeters
Input: KM = 2.5
Output: 2.5 KM is equivalent to 2500 meters
        2.5 KM is equivalent to 250000 centimeters
```

**方法**是将 KM 数据乘以 1000 换算成米，乘以 100000 换算成厘米。
以下是所需的实现:

## 结构化查询语言

```sql
--DECLARATION SECTION 
DECLARE
    --VARIABLE DECLARATION -KM, MET, CEM;
    km  NUMBER := 6.9;
    met NUMBER := 0;
    cem NUMBER := 0;
--CODE BLOCK 
BEGIN
    --CALCULATE METERS
    met := km * 1000;

    --CALCULATE CENTIMETERS
    cem := met * 100;

    --DISPLAY RESULT  
    dbms_output.Put_line('6.9KM is equivalent to meters: ' ||met);

    dbms_output.Put_line('6.9KM is equivalent to centimeters:' ||cem);

END;
--END PROGRAM
```

**输出:**

```sql
6.9KM is equivalent to meters: 6900
6.9KM is equivalent to centimeters:690000
```