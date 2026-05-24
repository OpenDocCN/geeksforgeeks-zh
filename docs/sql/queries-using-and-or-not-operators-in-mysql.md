# 在 MySQL 中使用与、或、非运算符的查询

> 原文:[https://www . geeksforgeeks . org/query-使用-and-or-not-operator-in-MySQL/](https://www.geeksforgeeks.org/queries-using-and-or-not-operators-in-mysql/)

**AND，OR，NOT** 运算符基本上与[](https://www.geeksforgeeks.org/sql-where-clause/#:~:text=It%20is%20used%20to%20fetch%20filtered%20data%20in,range%20inclusive%20of%20two%20values.&text=result%20set.,-Queries&text=It%20is%20used%20to%20fetch%20filtered%20data%20by%20searching,particular%20pattern%20in%20where%20clause.)****子句一起使用，以便通过使用 [**MySQL**](https://www.geeksforgeeks.org/mysql-common-mysql-queries/) 中的 **AND，OR，NOT** 过滤某些条件来从表中检索数据。
在本文中，让我们逐步看到使用 **AND、OR、NOT** 运算符对学生表的不同查询。****

******第一步:创建数据库大学:******

```sql
****CREATE DATABASE** university;**
```

****![](img/affb0fa2dd7c5bbc306cd2a2a1d7be69.png)****

******第二步:使用数据库大学:******

```sql
****USE** university;**
```

****![](img/bab6cb28b40f1ce7e88a20a2cdf951cb.png)****

******第三步:创建表格学生:******

```sql
****CREATE TABLE** student(
student_id **INT**
student_name **VARCHAR**(20)
birth_date **DATE**
branch **VARCHAR**(20)
state **VARCHAR**(20));**
```

****![](img/c39f19cf4336da67c95fec48cd47b59d.png)****

******第 4 步:查看表格学生描述:******

```sql
****DESCRIBE** student;**
```

****![](img/68a922a199a3b72c3be417b148b86410.png)****

******第五步:在学生表中添加行:******

```sql
****INSERT INTO** student **VALUES**(194001,'PRANAB','1999-03-17','CSE','PUNJAB');
**INSERT INTO** student **VALUES**(194002,'PRAKASH','2000-08-07','ECE','TAMIL NADU');
**INSERT INTO** student **VALUES**(194003,'ROCKY','2000-03-10','ECE','PUNJAB');
**INSERT INTO** student **VALUES**(194004,'TRIBHUVAN','1999-03-15','CSE','ANDHRA PRADESH');
**INSERT INTO** student **VALUES**(194005,'VAMSI','2000-04-19','CSE','TELANGANA');**
```

****![](img/97bf56b561a2b785dd75074f7b5322ba.png)****

******第 6 步:查看表格中的行:******

```sql
****SELECT * FROM** student;**
```

****![](img/c59b19d24ac1144c2b49967a5996a271.png)****

> ******和**运算符的语法:
> **从**表中选择*名称
> **其中**条件 1 **和**条件 2 **和** …。CONDITIONn****

******示例-1:**
使用 MySQL 中的 and 运算符查询查找带有 CSE 分支和 PUNJAB 州的学生记录:****

```sql
****SELECT ***
   ** FROM** student
 **   WHERE** branch='CSE'**AND**state='PUNJAB'**
```

****![](img/dda2d52f43b2f0aa6138fb50f7ecd815.png)****

****所有有中央教育学院分校和旁遮普的学生。****

> ******或**运算符的语法:
> **从**表中选择*名称
> **其中**条件 1 **或**条件 2 **或** …。CONDITIONn****

******示例-2:**
在 MySQL 中使用 or 运算符查询查找带有 CSE 或 ECE 分支的学生记录:****

****![](img/3bd07121b352f8bfbfd92760af5618ef.png)****

****所有有分支的学生要么是 CSE，要么是 ECE。****

> ******NOT** 运算符的语法:
> **从**表中选择*名称
> **非**条件 1 **非**条件 2 **非。**..CONDITIONn****

******示例-3:**
使用 MySQL 中的 NOT 运算符查询查找不在旁遮普的学生记录:****

```sql
****SELECT ***
    **  FROM** student
     ** WHERE NOT** state='PUNJAB';**
```

****![](img/226faab9535988be62544b2ddf34e85d.png)****

****所有来自旁遮普以外的学生。****