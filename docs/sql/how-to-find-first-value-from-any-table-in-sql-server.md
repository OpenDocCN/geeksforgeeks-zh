# 如何从 SQL Server 的任意表中找到第一个值

> 原文:[https://www . geesforgeks . org/如何从 SQL server 中的任何表中找到第一个值/](https://www.geeksforgeeks.org/how-to-find-first-value-from-any-table-in-sql-server/)

我们可以在 [SQL Server](https://www.geeksforgeeks.org/introduction-of-ms-sql-server/) 中使用 FIRST_VALUE()从任何表中查找第一个值。**在 SQL server 中使用的 FIRST_VALUE()** 函数是一种窗口函数，它在给定数据集的有序分区中产生第一个值。

**语法:**

```sql
SELECT *,
FROM tablename;
FIRST_VALUE ( scalar_value ) 
OVER ( 
 [PARTITION BY partition_value ]
 ORDER BY sort_value [ASC | DESC]
 ) AS columname ; 

```

**语法描述:**

*   **标量 _ 值–**
    标量 _ 值是对所提供数据集的有序分区中第一行的值进行检查的值。
*   **PARTITION BY–**
    PARTITION BY 是可选的，它将提供的数据集的行与使用 FIRST_VALUE()函数的分区不同。
*   **ORDER BY–**
    ORDER BY 表示使用 FIRST_VALUE()函数的每个分区中的行的顺序。

**示例:**

让我们假设我们有一个名为“geek_demo”的表:

```sql
SELECT TOP 1000 [Name]
     ,[City], [Year]
FROM [geek_demo];
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

**示例-1 :**

**在没有 PARTITION BY 子句的情况下查找第一个值。**

要查找表“极客演示”的第一个城市，请使用以下查询:

```sql
SELECT [Name],   [Year],
        FIRST_VALUE(City) OVER (
          ORDER BY City ASC
      ) AS  First_City
FROM geek_demo;
```

**输出:**

| 名字 | 年 | 第一城市 |
| --- | --- | --- |
| 巴比塔 | Two thousand and seventeen | 无聊死了 |
| 车坛 | Two thousand and eighteen | 无聊死了 |
| 库希 | Two thousand and nineteen | 无聊死了 |
| 非常 | Two thousand and seventeen | 无聊死了 |
| 毛 | Two thousand and seventeen | 无聊死了 |
| 迪帕克（男子名） | Two thousand and eighteen | 德里 |
| 伊莎！伊莎 | Two thousand and nineteen | 德里 |
| 鸭子！鸭子 | Two thousand and nineteen | 德里 |

**示例-2 :**

**使用 PARTITION BY 子句查找第一个值。**

要根据年份为表“极客-演示”找到第一个城市，请使用以下查询:

```sql
SELECT TOP 1000 [Name] , [Year] ,
        FIRST_VALUE(City) OVER (
        PARTITION BY Year
          ORDER BY City ASC
      ) AS  First_City
FROM geek_demo;
```

**输出:**

| 名字 | 年 | 第一城市 |
| --- | --- | --- |
| 巴比塔 | Two thousand and seventeen | 无聊死了 |
| 非常 | Two thousand and seventeen | 无聊死了 |
| 毛 | Two thousand and seventeen | 无聊死了 |
| 迪帕克（男子名） | Two thousand and eighteen | 德里 |
| 车坛 | Two thousand and eighteen | 德里 |
| 伊莎！伊莎 | Two thousand and nineteen | 德里 |
| 鸭子！鸭子 | Two thousand and nineteen | 德里 |
| 库希 | Two thousand and nineteen | 德里 |