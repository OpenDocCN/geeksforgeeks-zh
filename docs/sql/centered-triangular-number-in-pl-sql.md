# PL/SQL 中居中的三角数

> 原文:[https://www . geesforgeks . org/centered-trial-number-in-pl-SQL/](https://www.geeksforgeeks.org/centered-triangular-number-in-pl-sql/)

**先决条件**–[PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)
在 PL/SQL 中，命令的代码组排列在一个块内。一组相关的声明或语句。在声明部分，我们声明变量，在开始和结束部分之间，我们执行操作。

给定 n，任务是找到第 n 个[居中的三角形](https://www.geeksforgeeks.org/centered-triangular-number/)数。居中的三角形数是一个居中的数，它表示一个三角形，在连续的三角形层中，中心有一个点，所有其他点都围绕着中心。
**例:**

```sql
Input: n = 6 
Output: 64

Input: n = 10
Output: 166

```

**前几个居中的三角数**系列为:
1、4、10、19、31、46、64、85、109、136、166、199、235、274、316、361、409、460……

**逼近**
第 n 项中心三角数由下式给出:

**下面是需要的实现:**

```sql
--PL/SQL Program to find the nth Centered triangular number 
-- declaration section 
DECLARE 
  x NUMBER; 
  n NUMBER; 

  --utility function 
  FUNCTION Centered_triangular_num(n IN NUMBER) 
    RETURN NUMBER 
  IS 
    z NUMBER; 
  BEGIN 

    --formula applying 
    z := (3 * n * n + 3 * n + 2) / 2; 
    RETURN z; 
  END; 

  --driver code 
  BEGIN 
    n := 3; 
    x := centered_triangular_num(n); 
    dbms_output.Put_line(x); 
    n := 12; 
    x := centered_trigunal_num(n); 
    dbms_output.Put_line(x); 
  END; 
  --End of program
```

**输出:**

```sql
19
235
```

**参考文献:**
[https://en.wikipedia.org/wiki/Centered_triangular_number](https://en.wikipedia.org/wiki/Centered_triangular_number)