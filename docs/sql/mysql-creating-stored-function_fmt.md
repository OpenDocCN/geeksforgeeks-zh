# MySQL |创建存储函数

> 原文:[https://www . geesforgeks . org/MySQL-creating-stored-function/](https://www.geeksforgeeks.org/mysql-creating-stored-function/)

`CREATE FUNCTION` 语句用于创建存储函数和用户定义函数。存储函数是一组执行某种操作并返回单个值的 SQL 语句。

就像 Mysql 内置函数一样，可以从 Mysql 语句内部调用。

默认情况下，存储函数与默认数据库相关联。

`CREATE FUNCTION`语句需要`CREATE ROUTINE`数据库权限。

## 语法:
Mysql 中 `CREATE FUNCTION` 语句的语法为:

```sql
CREATE FUNCTION function_name(func_parameter1, func_parameter2, ..)
          RETURN datatype [characteristics]
          func_body
```

## 使用的参数:

1.  **函数名:**
    是调用存储函数的名称。该名称不应与本机(内置)函数相同。为了将例程显式地与特定的数据库函数相关联，应该给定名称为 `database_name.func_name`。
2.  **func_parameter:**
    它是其值被其体内的函数使用的参数。您不能指定这些参数`IN`、`OUT`、`INOUT`。括号内的参数声明为 `func_parameter type`。这里，类型代表有效的 Mysql 数据类型。
3.  **数据类型:**
    是函数返回值的数据类型。
4.  **特征:**
    `CREATE FUNCTION`语句只有在其声明中指定了至少一个特征{`DETERMINISTIC`、`NO SQL`或`READS SQL DATA`}时才被接受。

`func_body` 是执行运算的一组 Mysql 语句。它的结构如下:

```sql
BEGIN
    Mysql Statements
    RETURN expression;
END
```

函数体必须包含一个 `RETURN` 语句。

## 示例:

考虑以下员工表:

| emp_id | fname | lname | start_date |
| --- | --- | --- | --- |
| 1 | Michael | Smith | 2001-06-22 |
| 2 | Susan | Barker | 2002-09-12 |
| 3 | Robert | Tyler | 2000-02-09 |
| 4 | Susan | Hawthorne | 2002-04-24 |

我们必须找到员工在公司的工作年限:

```sql
DELIMITER //

CREATE FUNCTION no_of_years(date1 date) RETURNS int DETERMINISTIC
BEGIN
    DECLARE date2 DATE;
    SELECT current_date() INTO date2;
    RETURN year(date2)-year(date1);
END
//

DELIMITER ;
```

上述函数的调用:

```sql
SELECT emp_id, fname, lname, no_of_years(start_date) as 'years' FROM employee;
```

**输出:**

| emp_id | fname | lname | years |
| --- | --- | --- | --- |
| 1 | Michael | Smith | 18 |
| 2 | Susan | Barker | 17 |
| 3 | Robert | Tyler | 19 |
| 4 | Susan | Hawthorne | 17 |