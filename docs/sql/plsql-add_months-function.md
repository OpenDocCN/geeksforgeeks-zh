# PLSQL | ADD_MONTHS 功能

> 原文:[https://www.geeksforgeeks.org/plsql-add_months-function/](https://www.geeksforgeeks.org/plsql-add_months-function/)

**PLSQL ADD_MONTHS** 函数用于返回添加了指定月数的日期。ADD _ MINUTES 函数接受两个参数，即初始日期和要添加到其中的月份数。
ADD _ MONTHS 函数返回日期数据类型的值。

date 参数可以是日期时间值，也可以是任何可以隐式转换为 DATE 的值。要添加的整数参数可以是整数或任何可以隐式转换为整数的值。返回类型始终是 DATE，不管数据类型是什么。如果参数中指定的日期是该月的最后一天，或者结果月的天数少于日期的天部分，则结果是结果月的最后一天。

**语法:**

```sql
ADD_MONTHS( init_date, add_months )
```

**使用的参数**

1.  **init _ date–**用于指定初始日期。
2.  **add _ months–**用于指定要添加到初始日期的月数。

**返回值:**
ADD _ MONTHS 函数返回一个日期数据类型的值。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例-1:** 在 add_months 函数的 ADD_MONTHS 参数中使用正数值。

```sql
DECLARE 
   Test_Date date := '01-Aug-18';
   Add_Month number := 3;

BEGIN 
   dbms_output.put_line(ADD_MONTHS(Test_Date, Add_Month)); 

END; 
```

**输出:**

```sql
01.12.18 
```

**示例-2:** 在 add_months 函数的 ADD_MONTHS 参数中使用负数值。

```sql
DECLARE 
   Test_Date date := '01-Aug-18';
   Add_Month number := -3;

BEGIN 
   dbms_output.put_line(ADD_MONTHS(Test_Date, Add_Month)); 

END; 
```

**输出:**

```sql
01.05.03 
```

**示例-3:** 在 add_months 函数的 ADD_MONTHS 参数中使用负数值。

```sql
DECLARE 
   Test_Date date := '31-Aug-18';
   Add_Month number := -4;

BEGIN 
   dbms_output.put_line(ADD_MONTHS(Test_Date, Add_Month)); 

END; 
```

**输出:**

```sql
30.04.18 
```

由于 4 月有 30 天，所以 ADD _ MONTHS 返回 30.04.18 作为最后一天。

**示例-4:** 在 add_months 函数的 ADD_MONTHS 参数中使用正数值。

```sql
DECLARE 
   Test_Date date := '31-Aug-18';
   Add_Month number := 3;

BEGIN 
   dbms_output.put_line(ADD_MONTHS(Test_Date, Add_Month)); 

END; 
```

**输出:**

```sql
30.11.18 
```

由于 11 月有 30 天，所以 ADD _ MONTHS 返回 30.11.18 作为最后一天。

**示例-5:** 使用带有 ADD _ MINUTES 函数的选择查询。

```sql
SELECT
  ADD_MONTHS( DATE '2016-02-29', 1 )
FROM
  dual; 
```

**输出:**

```sql
31-MAR-16 
```

**优势:**
要添加的整数参数可以是整数，也可以是任何可以隐式转换为整数的值。