# 如何从 SQL Server 的任意表中找到最后一个值

> 原文:[https://www . geeksforgeeks . org/如何从 SQL server 中的任何表中查找最后一个值/](https://www.geeksforgeeks.org/how-to-find-last-value-from-any-table-in-sql-server/)

我们可以在 [SQL Server](https://www.geeksforgeeks.org/introduction-of-ms-sql-server/) 中使用 LAST_VALUE()从任何表中查找最后一个值。**在 SQL server 中使用的 LAST_VALUE()** 函数是一种窗口函数，其结果是给定数据集的有序分区中的最后一个值。

**语法:**

```sql
SELECT *,
FROM tablename
LAST_VALUE ( scalar_value )  
OVER (  
  [PARTITION BY partition_expression ]
  ORDER BY sort_expression [ASC | DESC]
) 
AS columname ; 

```

其中术语描述如下。
**标量 _ 值–**
标量 _ 值是针对给定数据集的有序分区中最后一行的值进行分析的值。

**PARTITION BY–**
PARTITION BY 子句是可选的，它将给定数据集的行划分为使用 LAST_VALUE()函数的分区。

**ORDER BY–**
ORDER BY 子句定义了每个分区中使用 LAST_VALUE()函数的行的顺序。

**示例-1 :**
让我们假设我们有一个名为‘geek demo’的表；

```sql
SELECT Name, City, Year
FROM [geekdemo] ;
```

| 名字 | 城市 | 年 |
| --- | --- | --- |
| 鸭子！鸭子 | 德里 | Two thousand and nineteen |
| 巴比塔 | 无聊死了 | Two thousand and seventeen |
| 车坛 | 无聊死了 | Two thousand and eighteen |
| 迪帕克（男子名） | 德里 | Two thousand and eighteen |
| 伊莎！伊莎 | 德里 | Two thousand and nineteen |
| 库希 | 无聊死了 | Two thousand and nineteen |
| 非常 | 无聊死了 | Two thousand and seventeen |
| 毛 | 无聊死了 | Two thousand and seventeen |

**示例-2 :**
**不带 PARTITION BY 子句的 LAST_VALUE()**

```sql
SELECT TOP 1000 Name, 
Year, LAST_VALUE(City) 
OVER 
(ORDER BY City ASC ) AS Last_City
FROM geekdemo;

```

**输出:**

| 名字 | 年 | 最后 _ 城市 |
| --- | --- | --- |
| 迪帕克（男子名） | Two thousand and eighteen | 德里 |
| 伊莎！伊莎 | Two thousand and nineteen | 德里 |
| 鸭子！鸭子 | Two thousand and nineteen | 德里 |
| 巴比塔 | Two thousand and seventeen | 无聊死了 |
| 车坛 | Two thousand and eighteen | 无聊死了 |
| 库希 | Two thousand and nineteen | 无聊死了 |
| 非常 | Two thousand and seventeen | 无聊死了 |
| 毛 | Two thousand and seventeen | 无聊死了 |

**示例-3 :**
**LAST_VALUE()带 PARTITION BY 子句:**

```sql
SELECT Name, 
Year, 
LAST_VALUE(City) OVER 
(PARTITION BY Year
ORDER BY City ASC) AS Last_City
FROM geekdemo;
```

**输出:**

| 名字 | 年 | 最后 _ 城市 |
| --- | --- | --- |
| 巴比塔 | Two thousand and seventeen | 无聊死了 |
| 非常 | Two thousand and seventeen | 无聊死了 |
| 毛 | Two thousand and seventeen | 无聊死了 |
| 迪帕克（男子名） | Two thousand and eighteen | 德里 |
| 车坛 | Two thousand and eighteen | 无聊死了 |
| 伊莎！伊莎 | Two thousand and nineteen | 德里 |
| 鸭子！鸭子 | Two thousand and nineteen | 德里 |
| 库希 | Two thousand and nineteen | 无聊死了 |