# SQL |连接运算符

> 原文:[https://www.geeksforgeeks.org/sql-concatenation-operator/](https://www.geeksforgeeks.org/sql-concatenation-operator/)

先决条件:[基本选择语句](https://www.geeksforgeeks.org/sql-select-clause/)、[插入子句](https://www.geeksforgeeks.org/sql-insert-statement/)、 [SQL 创建子句](https://www.geeksforgeeks.org/sql-create/)、 [SQL 别名](https://www.geeksforgeeks.org/sql-aliases/)

**||或串联运算符**用于**链接列**或**字符串**。我们也可以用**字面**。文字是包含在 SELECT 语句中的**字符**、**数字**或**日期**。

让我们通过一个例子来演示一下:

**语法**:

```sql
SELECT id, first_name, last_name, first_name || last_name, 
               salary, first_name || salary FROM myTable
```

```sql
Output (Third and Fifth Columns show  values concatenated by operator ||)
id  first_name  last_name    first_name||last_name  salary   first_name||salary    
1   Rajat        Rawat          RajatRawat          10000    Rajat10000                                                               
2   Geeks        ForGeeks      GeeksForGeeks        20000    Geeks20000                    
3   Shane        Watson         ShaneWatson         50000    Shane50000                           
4   Kedar        Jadhav         KedarJadhav         90000     Kedar90000                           

```

**注意**:在上面这里我们使用了 **||** ，它被称为**连接运算符**，用于在选择查询中根据需要链接 2 列或多个**列**，它是**独立于列的数据类型**。在上面我们链接了 2 列，即**名+姓**和**名+薪**。

我们也可以在**串联**运算符中使用**文字**。让我们看看:

**例 1** :使用文字
**语法**:

```sql
SELECT id, first_name, last_name, salary, 
      first_name||' has salary '||salary as "new"  FROM myTable

```

```sql
Output : (Concatenating three values and giving a name 'new')
id  first_name  last_name  salary            new
1   Rajat        Rawat     10000      Rajat has salary 10000
2   Geeks        ForGeeks  20000      Geeks has salary 20000
3   Shane        Watson    50000      Shane has salary 50000
4   Kedar        Jadhav    90000      Kedar has salary 90000

```

**注意**:上面这里我们在 select 语句中使用了**有工资**作为字符文字。同样，我们可以根据需要使用数字文字或日期文字。

**例 2** :使用字符和数字文字
**语法**:

```sql
SELECT id, first_name, last_name, salary, first_name||100||' 
                          has id '||id AS "new" FROM myTable

```

```sql
Output (Making readable output by concatenating a string
with values)

id  first_name   last_name     salary     new
1    Rajat       Rawat         10000    Rajat100 has id 1
2    Geeks       ForGeeks      20000    Geeks100 has id 2
3    Shane       Watson        50000    Shane100 has id 3
4    Kedar       Jadhav        90000    Kedar100 has id 4
```

我们在上面的 select 语句中使用了**有工资**作为字符文字以及 **100** 作为数字文字。

**参考文献** :
1)关于串联运算符: [Oracle 文档](https://docs.oracle.com/cd/B19306_01/server.102/b14200/operators003.htm)T5)2)在线执行 SQL 查询: [Oracle 实时 SQL](https://livesql.oracle.com/apex/livesql/file/index.html)

**注**:在线执行 SQL 查询，必须在 Oracle 上有账号，如果没有，可以打开上面的链接进行。