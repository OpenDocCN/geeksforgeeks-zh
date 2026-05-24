# SQL SERVER |在条件下

> 原文:[https://www.geeksforgeeks.org/sql-server-condition/](https://www.geeksforgeeks.org/sql-server-condition/)

IN 条件是 SELECT、INSERT、UPDATE 或 DELETE 语句中多个 OR 条件的替代条件。IN 运算符允许根据表达式测试多个值，因此减少了对每个测试值使用多个或条件。

**语法:**

```sql
expression IN (value1, value2, .... value_n);

```

**凡**T2**1。表达式:**待测值/属性。
**2。值 1，值 2，..value_n :** 根据表达式测试的值。

### 示例:

### 创建表格 GEEKS _ 6

![](img/a8682b3e4f109c5c971ed093b8c71d86.png)

### 将值插入表 GEEKS_6:

![](img/9908f5e9982659d9662a3d1e328c3cc1.png)

### 极客 6 内容:

![](img/5953a424394bcdc04d198bc2aff546eb.png)

**使用**【或】选择多个值。**** 必须使用多个或来检查表达式。
![](img/4ed60b23a79c2bbec046a9ee8f122137.png)

使用**‘IN’**可以回答相同的查询，这减少了必须写入条件的次数，并且所有测试值都出现在一个地方。
**在查询:**
![](img/5c6114ecff7bd749e976b04ba4b1d3ed.png)

### 示例 2:在两个表中使用“IN”>

### 创建表 GEEKS_7:

![](img/a4a73695485fd0544d25a66a338cb41a.png)

### 将值插入表 GEEKS_7:

![](img/9c3865599df6d8fb26700f792d157fc3.png)

### 极客 7 内容:

![](img/43aa9719d0c22357000efa2d81be1e44.png)

### 查询:使用“输入”从两个表中查找公共元素

![](img/11125fb9631dde1f2013cce60ba12eb2.png)

**说明:**
首先执行内部查询，选择 Table Geeks_7 的**【名称】**列中的所有值。然后外部查询将开始执行，它将使用内部查询值来过滤掉匹配的值。