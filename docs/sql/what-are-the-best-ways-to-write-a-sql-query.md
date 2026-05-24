# 编写 SQL 查询的最佳方法是什么？

> 原文:[https://www . geesforgeks . org/什么是编写 sql 查询的最佳方法/](https://www.geeksforgeeks.org/what-are-the-best-ways-to-write-a-sql-query/)

一个 **[SQL](https://www.geeksforgeeks.org/sql-tutorial/)** 查询用于从数据库中检索所需的数据。但是，可能有多个 SQL 查询产生相同的结果，但效率水平不同。低效的查询可能会耗尽数据库资源，降低数据库速度，或者导致其他用户失去服务。因此优化查询以获得最佳的数据库性能是非常重要的。

让我们考虑一些示例表来理解优化查询的这些不同方法。

**客户:**客户表包含一家店铺的潜在客户的详细信息。

| CustomerID | 姓 | 西方人名的第一个字 | 地址 | 年龄 |
| --- | --- | --- | --- | --- |
| Seventy-three thousand and one | 史密斯（姓氏） | 约翰 | 跳跃街 45 号 | Twenty-one |
| Seventy-three thousand and two | 帕克 | 安娜；安那（anna 旧时印度货币名） | 狂野大道 83 号 | Forty-five |
| Seventy-three thousand and three | 詹姆斯 | 乔茜（女子名） | 栗子大道 99 号 | Twenty-five |
| Seventy-three thousand and four | 怀特（姓氏） | 安娜；安那（anna 旧时印度货币名） | 纸街 55 号 | seventy-two |
| Seventy-three thousand and five | （船或飞机上的）无线电通信师 | （英、瑞）哈里（人名） | 紫藤巷 11 号 | Twenty-three |
| Seventy-three thousand and six | 帕克 | 简（女子名） | 昆汀路 12 号 | Fifty |

**产品:**产品表包含店铺内可售产品的详细信息。

| 产品 id | 产品名称 | 产品价格 |
| --- | --- | --- |
| One thousand and one | 洗涤剂 | One hundred |
| One thousand and two | 牙膏 | Twenty |
| One thousand and three | 肥皂 | Fifteen |
| One thousand and four | 洗手液 | Fifty |
| One thousand and five | 除臭剂 | One hundred |

**订单:**订单表包含顾客从店铺订购产品的详细信息。

| CustomerID | 产品 id | 产品数量 |
| --- | --- | --- |
| Seventy-three thousand and one | One thousand and three | five |
| Seventy-three thousand and one | One thousand and one | one |
| Seventy-three thousand and three | One thousand and two | one |
| Seventy-three thousand and four | One thousand and three | Two |
| Seventy-three thousand and four | One thousand and five | one |

现在我们已经分析了表*客户*、*产品*和*订单*，下面给出了优化查询的不同方法，并从这些表中给出了查询示例:

### 1.为查询提供正确的格式

编写查询时提供正确的格式非常重要。这增强了查询的可读性，也使检查和故障排除变得更加容易。下面给出了一些格式化查询的规则:

*   将查询中的每个语句放在新的一行中。
*   将查询中的 SQL 关键字大写。
*   在查询中使用大小写，避免下划线(写产品名而不是产品名)。

**示例:**这是一个显示当前已订购产品且年龄小于 50 岁的客户的 CustomerID 和 LastName 的查询。

```sql
Select distinct Customers.CustomerID, Customers.LastName from Customers INNER join Orders on Customers.CustomerID = Orders.CustomerID where Customers.Age < 50;

```

上面的查询看起来不可读，因为所有语句都在一行中，并且关键字都是小写的。因此，下面给出了一个优化版本，使用了前面指定的格式化规则。

```sql
SELECT DISTINCT Customers.CustomerID, Customers.LastName
FROM Customers INNER JOIN Orders
ON Customers.CustomerID = Orders.CustomerID
WHERE Customers.Age < 50;

```

### 2.指定选择字段，而不是使用选择*

**SELECT *** 用于从表中获取所有数据。因此，除非给定条件实际上需要所有数据，否则不应使用它，因为它效率很低，并且会减慢查询的执行时间。最好将 SELECT 与优化查询所需的特定字段一起使用。

**示例:**当只需要 *CustomerID* 和*姓氏*时，这是一个显示客户表中所有数据的查询。

```sql
SELECT * 
FROM Customers;

```

最好使用带有字段 *CustomerID* 和*姓氏*的 select 语句来获得所需的结果。

```sql
SELECT CustomerID, LastName 
FROM Customers;

```

### 3.如果不需要，删除相关子查询

相关子查询是一种嵌套查询，其值依赖于外部查询。如果数据库中有数百万用户，相关的子查询效率很低，并且需要花费大量时间，因为它需要运行数百万次。在这种情况下，内部连接更有效。

**示例:**这是一个使用相关子查询显示当前已订购产品的客户的*客户标识*的查询。

```sql
SELECT CustomerID
FROM Customers
WHERE EXISTS (SELECT * FROM Orders
              WHERE Customers.CustomerID = Orders.CustomerID);

```

在这种情况下，最好使用内部连接来获得相同的结果。

```sql
SELECT DISTINCT Customers.CustomerID
FROM Customers INNER JOIN Orders
ON Customers.CustomerID = Orders.CustomerID;

```

**注意:**如果数据库中几乎所有的行都需要，最好避免相关的子查询。然而，在某些情况下，它们是不可避免的，必须使用。

### 4.限制通过查询获得的结果

如果只需要有限的结果，最好使用 LIMIT 语句。此语句限制记录，仅显示指定的记录数。*例如:*如果有一个有一百万条记录的大型数据库，并且只需要前十条，那么最好使用 LIMIT 语句，因为这样可以确保只获取相关记录，而不会使系统负担过重。

**示例:**这是一个显示限额为 3 的客户详细信息的查询:

```sql
SELECT *
FROM Customers 
LIMIT 3;

```

### 5.如果不需要，删除 DISTINCT 子句

DISTINCT 子句用于通过消除重复项从查询中获得不同的结果。但是，这增加了查询的执行时间，因为所有重复的字段都被分组在一起。所以，最好尽量避免 DISTINCT 子句。作为替代，GROUP BY 子句可用于获得不同的结果。

**示例:**这是一个使用 distinct 子句显示所有客户的 distinct LastName 的查询。

```sql
select distinct LastName
from Customers;

```

客户的不同姓氏也可以使用 GROUP BY 子句获得，如下面的示例所示:

```sql
SELECT LastName
FROM  CUSTOMERS
GROUP BY LastName;

```

### 6.避免谓词中的函数

SQL 中的函数用于执行特定的操作。但是，它们效率很低，因为它们不允许使用索引，而索引又会减慢查询的执行时间。所以最好尽量避免函数出现在查询中，以保证其最优化。

**示例:**这是一个显示名称以“【沙】开头的产品详细信息的查询。

```sql
SELECT *
FROM Products
WHERE SUBSTR(ProductName, 1, 3) = 'Sha';

```

最好避免函数，而使用 LIKE 子句来获得相同的结果。

```sql
SELECT *
FROM Products
WHERE ProductName LIKE 'Sha%';

```

### 7.尽可能避免“或”、“与”、“非”运算符

当使用“或”、“与”、“非”运算符时，很可能没有使用索引。在大型数据库的情况下，最好找到这些数据库的替代数据库，以加快查询的执行时间。

*OR 和 and 运算符的例子如下:*

**示例 1:** 这是一个使用 OR 运算符显示 CustomerID 为 73001、73004 和 73005 的客户的详细信息的查询。

```sql
SELECT * 
FROM Customers
WHERE CustomerID = 73001
OR CustomerID = 73004
OR CustomerID = 73005;

```

在这种情况下，最好使用 IN 运算符来获得相同的结果。

```sql
SELECT * 
FROM Customers
WHERE CustomerID IN (73001, 73004, 73005);

```

**示例 2:** 这是一个使用 and 运算符显示年龄在 25 至 50 岁之间的客户的详细信息的查询。

```sql
SELECT * 
FROM Customers
WHERE age >= 25 AND age <= 50; < pre>在这种情况下，最好使用 BENT 运算符来获得相同的结果。

```
SELECT * 
FROM Customers
WHERE age BETWEEN 25 AND 50;

```sql

8.尽可能使用 WHERE 子句而不是 HAVING 子句HAVING 子句与 GROUP BY 子句一起使用来强制条件，因为 WHERE 子句不能与聚合函数一起使用。但是，HAVING 子句不允许使用索引，这会降低查询的执行时间。所以最好尽可能使用 WHERE 子句而不是 HAVING 子句。**示例:**这是一个显示客户名字的查询，其中包含年龄超过 25 岁的客户的名字计数。这是使用 HAVING 子句完成的。

```
SELECT FirstName, COUNT(*)
FROM Customers
GROUP BY FirstName
HAVING Age > 25;

```sql

在这种情况下，最好使用 WHERE 子句，因为它将条件应用于单独的行，而不是使用 HAVING 子句将条件应用于 GROUP BY 子句的结果。

```
SELECT FirstName, COUNT(*)
FROM Customers
where Age > 25
GROUP BY FirstName;

```sql

9.使用 INNER JOIN 而不是 WHERE 子句来创建联接使用 WHERE 子句创建联接会产生笛卡尔乘积，其中行数是两个表的行数的乘积。这对于大型数据库来说显然是有问题的，因为需要更多的数据库资源。因此，最好使用 INNER JOIN，因为它只组合两个表中满足所需条件的行。**示例:**这是一个使用 WHERE 子句显示当前已订购产品的客户的 CustomerID 的查询。

```
SELECT DISTINCT Customers.CustomerID
FROM Customers, Orders
WHERE Customers.CustomerID = Orders.CustomerID;

```sql

在这种情况下，最好使用内部连接来获得相同的结果。

```
SELECT DISTINCT Customers.CustomerID
FROM Customers INNER JOIN Orders
ON Customers.CustomerID = Orders.CustomerID;

```sql

10.避免在 LIKE 子句模式的开头使用通配符像%和 _ 这样的通配符用于过滤掉 LIKE 子句的结果。但是，它们不应该在模式的开头使用，因为这会禁止数据库使用索引。在这种情况下，需要进行全表扫描来匹配消耗更多数据库资源的模式。因此，最好避免在模式的开头使用通配符，如果可能的话，只在结尾使用它们。**示例:**

```
SELECT * FROM Customers
WHERE FirstName LIKE '%A%'

```sql

上面的查询效率很低，因为它在模式的开头使用了通配符% 1。下面给出了避免这种情况的更有效的查询版本:

```
SELECT * FROM Customers
WHERE FirstName LIKE 'A%'

```sql

=>
```