# 嵌套子查询、相关子查询和连接操作的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-nested-subquery-correlated-subquery-and-join-operation/](https://www.geeksforgeeks.org/difference-between-nested-subquery-correlated-subquery-and-join-operation/)

## Join 操作

Join 操作是一种二进制操作，用于根据两个或多个表之间的公共字段来组合它们的数据或行。`内部连接`、`左连接`、`右连接`、`完全连接`是不同类型的连接。

**示例–**

```sql
Orders (OrderID, CustomerID, OrderDate);
Customers (CustomerID, CustomerName, ContactName, Country);
```

查找已订购客户的详细信息。

```sql
SELECT * from Customers JOIN Orders 
ON Orders.CustomerID=Customers.CustomerID;
```

## 子查询

当一个查询包含在另一个查询中时，外部查询称为主查询，内部查询称为子查询。

### 嵌套查询

在嵌套查询中，内部查询首先运行，并且只运行一次。外部查询使用内部查询的结果来执行。

**示例 –**

```sql
Orders (OrderID, CustomerID, OrderDate);
Customers (CustomerID, CustomerName, ContactName, Country);
```

查找已订购客户的详细信息。

```sql
SELECT * FROM Customers WHERE 
CustomerID IN (SELECT CustomerID FROM Orders);
```

### 相关查询

在相关查询中，外部查询首先执行，对于外部查询的每一行，内部查询都会执行一次。因此，内部查询会使用来自外部查询的值。

**示例 –**

```sql
Orders (OrderID, CustomerID, OrderDate);
Customers (CustomerID, CustomerName, ContactName, Country);
```

查找已订购客户的详细信息。

```sql
SELECT * FROM Customers where 
EXISTS (SELECT CustomerID FROM Orders 
WHERE Orders.CustomerID=Customers.CustomerID);
```

## 连接操作和子查询的应用

要了解嵌套子查询、相关子查询和连接操作之间的区别，首先我们必须了解在哪里使用子查询以及在哪里使用连接。

*   当我们想要从多个表中获取数据时，我们使用连接操作。
    示例：考虑两个关系：

```sql
Employee (eId, eName, eSalary, dId);
Department (dId, dName, dLocation);
```

现在，我们必须找到在伦敦工作的员工姓名和部门名称。在这里，我们必须显示员工表中的姓名和部门表中的姓名。因此，我们必须使用连接操作。

```sql
SELECT e.eName, d.dName from Employee e, 
Department d 
where e.dId=d.dId and d.dLocation="London";
```

*   当我们想要从一个表中获取数据，而条件基于另一个表时，我们可以使用连接或子查询。现在，我们必须找到在伦敦工作的员工姓名。

这里，我们必须只显示雇员表中的`eName`，因此我们可以使用连接操作或子查询。

**使用连接操作–**

```sql
SELECT e.eName from Employee e, Department d 
where e.dId=d.dId and d.dLocation="London";
```

**使用子查询–**

```sql
SELECT eName from Employee 
where dId=(SELECT dId from Department where dLocation="London");
```

了解了联接与子查询的基本区别之后，现在我们将了解嵌套子查询、相关子查询和联接操作之间的区别。

## 嵌套查询、关联查询和连接操作的区别

| 因素 | 嵌套查询 | 相关查询 | 加入操作 |
| --- | --- | --- | --- |
| 定义 | 在嵌套查询中，一个查询写在另一个查询中，内部查询的结果用于外部查询的执行。 | 在相关查询中，一个查询嵌套在另一个查询中，内部查询使用外部查询的值。 | 联接操作用于根据两个或多个表之间的公共字段组合它们的数据或行。内部连接、左连接、右连接、完全连接是不同类型的连接。 |
| 方法 | 自下而上的方法，即内部查询首先运行，并且只运行一次。使用内部查询的结果执行外部查询。 | 自上而下的方法，即首先执行外部查询，对于每个外部查询行，执行内部查询。 | 它基本上是满足一个条件的叉积。 |
| 属国 | 内部查询的执行不依赖于外部查询。 | 内部查询依赖于外部查询。 | 没有内部查询或外部查询。因此，不存在依赖性。 |
| 表演 | 性能优于相关查询，但慢于连接操作。 | 对于每个外部查询，执行嵌套查询和连接操作的速度都比执行内部查询的速度慢。 | 通过使用联接，我们最大限度地增加了数据库的计算负担，但是服务器更好地优化了联接，因此使用联接的查询检索时间几乎总是比子查询快。 |