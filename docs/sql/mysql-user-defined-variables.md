# Mysql |用户定义变量

> 原文:[https://www.geeksforgeeks.org/mysql-user-defined-variables/](https://www.geeksforgeeks.org/mysql-user-defined-variables/)

Mysql 还支持用户定义变量的概念，允许将一个值从一条语句传递到另一条语句。Mysql 中的用户定义变量被写成 **@var_name** ，其中， **var_name** 是变量的名称，可以由字母数字字符组成。，_，和$。

*   User-defined variables are session-specific, that is, variables defined by one client will not be shared with other clients, and these variables will automatically expire when the session ends.
*   These variables are case insensitive. Therefore, **@ mark** or **@ mark** all refer to the same value.
*   The maximum length of a variable can be 64 characters.
*   The variable name can contain other characters, such as-{! , #,-,...} are in their names, if they are referenced. E.g. @'var@1' or @ "var 2" or @' var @`.
*   These variables cannot be declared, they are only initialized, that is, they should be assigned values when declared.
*   Undeclared variables can also be accessed in SQL statements, but their values are set to **null value** .
*   These variables can take values from the following data types-{integer, floating point, decimal, binary, non-binary string or null value.

**语法:**

```sql
SET @var_name = expression 
```

**示例:**

1.使用**设置**命令为变量赋值。

```sql
mysql>SET @var1 = 2+6;
mysql>SET @var2 := @var1-2;
```

这些变量的值可以通过在 SELECT 语句中引用它们来显示-

```sql
mysql>SELECT @var1, @var2;
```

**输出:**

```sql
+-------+-------+
| @var1 | @var2 |
+-------+-------+
|   8   |   6   |
+-------+-------+
```

2.访问未声明的变量

```sql
mysql>SELECT @var3;
```

**输出:**

```sql
+-------+
| @var3 | 
+-------+
|  NULL |  
+-------+
```

这里变量 **@var3** 是未声明的，所以默认值为 NULL。

3.不使用**设置**为变量赋值。

```sql
mysql>SELECT @var3 := 4;
```

**输出:**

```sql
+----------+
| @var3:=4 | 
+----------+
|    4     |  
+----------+
```

在上例中-变量 **@var3** 应该只使用 **:=** 而不是 **=** 赋值，后者在非 **SET** 语句中被视为比较。就像-

```sql
mysql>SELECT @var4 = 5;
```

**输出:**

```sql
+----------+
| @var4=5  | 
+----------+
|   NULL   |  
+----------+
```

**这些变量是如何用来存储值的，这些值将在未来使用。**

考虑一下，下面的 Student 表-

<figure class="table">T13】沙贡 T15】15T18T21】塔鲁纳 T23】5T26T29】日亚 T31】11

| s _ id | s _ name | 标记 |
| --- | --- | --- |
| one |
| Two | three |

</figure>

现在，我们要用用户定义的变量找到这些学生的**排名**。

为此，我们初始化两个变量- **@rank** 和 **@prev_mark** 。

```sql
mysql>SET @rank=0, @prev_mark=0;
```

**查询:**

```sql
mysql>Select s_name, if (@prev_mark != mark, @rank:=@rank+1, @rank) as 'rank',
                    @prev_mark:=mark as 'marks' from student order by mark desc;
```

这里，变量 **@rank** 用于存储学生的排名， **@prev_mark** 用于存储之前学生成绩的分数。

对分数进行比较，以便在两个学生分数相等的情况下，可以避免增加 **@rank** 变量。

在学生表按“标记”列降序排序后，两个变量都发生了变化。

**输出:**

<figure class="table">

| 【s _ name】 | ranking |
| --- | --- |
| 【加里马】 |

</figure>

因此，我们得到的学生表按照“分数”列按照学生的排名降序排列。

**注意:**在上面的查询中，注意 select 语句中列的顺序。如果“标记”列写在“排名”列之前，那么我们得不到想要的输出。因为每次 **@prev_mark** 被分配当前学生的分数，结果评价@prev_mark！=标记为**假**。因此，每个学生的排名都显示为不递增，即它将保持为 0。