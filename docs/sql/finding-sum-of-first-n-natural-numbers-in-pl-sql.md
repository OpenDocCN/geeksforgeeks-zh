# 求 PL/SQL 中前 n 个自然数之和

> 原文:[https://www . geesforgeks . org/find-first-n-numbers-in-pl-SQL/](https://www.geeksforgeeks.org/finding-sum-of-first-n-natural-numbers-in-pl-sql/)

**先决条件**–[PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)
在 PL/SQL 中，命令的代码组排列在一个块内。一组相关的声明或语句。在声明部分，我们声明变量，在开始和结束部分之间，我们执行操作。
给定一个正整数 n，任务是求前 n 个自然数的和。
**示例:**

```sql
Input: n = 3
Output: 10

Input: n = 2
Output: 4

```

**方法**是从 1 到 n 取数字，然后像下面这样求和-

```sql
Sum of first natural number: 1
Sum of first and second natural number: 1 + 2 = 3
Sum of first, second and third natural number = 1 + 2 + 3 = 6
```

以下是所需的实现:

```sql
--declaration section 
DECLARE 
  x NUMBER; 
  n NUMBER; 
  i NUMBER; 

  --function for finding sum 
  FUNCTION Findmax(n IN NUMBER) 
    RETURN NUMBER 
  IS 
    sums NUMBER := 0; 
  BEGIN 

    --for loop for n times iteration 
    FOR i IN 1..n 
    LOOP 
      sums := sums + i*(i+1)/2; 
    END LOOP; 
    RETURN sums; 
  END; 
  BEGIN 

    --driver code 
    n := 4; 
    x := findmax(n); 
    dbms_output.Put_line('Sum: ' 
    || x); 
  END; 

  --end of Program
```

**输出:**

```sql
Sum: 20
```

时间复杂度= 0(n)

一个**有效的解决方案**是使用直接公式 n(n+1)(n+2)/6

数学上，我们需要找到，σ((I *(I+1))/2)，其中 1 <= i <= n
那么，让我们求解这个求和，

```sql
Sum = Σ ((i * (i + 1))/2), where 1 <= i <= n
    = (1/2) * Σ (i * (i + 1))
    = (1/2) * Σ (i2 + i)
    = (1/2) * (Σ i2 + Σ i)

We know Σ i2 = n * (n + 1) * (2*n + 1) / 6 and 
Σ i = n * ( n + 1) / 2.
Substituting the value, we get,
Sum = (1/2) * ((n * (n + 1) * (2*n + 1) / 6) + (n * ( n + 1) / 2))  
    = n * (n + 1)/2 [(2n + 1)/6 + 1/2]
    = n * (n + 1) * (n + 2) / 6
```

以下是所需的实现:

```sql
--declaration section 
DECLARE 
  x NUMBER; 
  n NUMBER; 

  --utility function 
  FUNCTION Findmax(n IN NUMBER) 
    RETURN NUMBER 
  IS 
    z NUMBER; 
  BEGIN 

    -- formula for finding sum 
    z := (n * (n + 1) * (n + 2)) / 6; 
    RETURN z; 
  END; 
  BEGIN 
    n := 4; 
    x := findmax(n); 
    dbms_output.Put_line(' Sum: ' 
    || x); 
  END; 

  --end of program
```

输出:

```sql
Sum: 20
```

时间复杂度= 0(1)