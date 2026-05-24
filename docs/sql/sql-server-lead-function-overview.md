# SQL Server LEAD()功能概述

> 原文:[https://www . geesforgeks . org/SQL-server-lead-function-overview/](https://www.geeksforgeeks.org/sql-server-lead-function-overview/)

在许多情况下，用户确实希望检查当前行的价值和后续行的价值。为了解决这个问题，经常使用 SQL Server 的 LEAD()窗口函数。

**LEAD() :**
函数提供对一行的访问，该行之后有一个设置的物理偏移量。 **LEAD()** 功能将允许访问下一行的数据，或后续行之后的行，并继续。

**语法:**

```sql
LEAD(return_value, offset [, default])  
OVER (
   [PARTITION BY partition_expression]
   ORDER BY sort_expression [ASC | DESC]
)
```

**其中:**

1.  **返回值–**
    后续行的返回值支持指定的偏移量。return_value 必须是一个值。
2.  **偏移量–**
    偏移量是从当前行向前访问数据的行数。偏移量应该是正整数。如果不定义，偏移量的默认值是 1。
3.  **默认值–**
    如果偏移量超出分区范围，则 LEAD()函数将导致默认值。如果未定义，默认值为空。
4.  **PARTITION BY 子句–**
    PARTITION BY 子句是可选的，它将结果集的行划分为使用 LEAD()函数的分区。
5.  **ORDER BY 子句–**
    ORDER BY 子句定义了使用 LEAD()函数的每个分区中的行的逻辑顺序。

**示例-1:**
假设我们有一个名为“CompanySales”的下表:

```sql
Select * 
from CompanySales;

```

| 公司 | 年 | 数量 |
| --- | --- | --- |
| 中航有限公司 | Two thousand and fifteen | Five thousand |
| XYZ 有限公司。 | Two thousand and fifteen | Four thousand six hundred |
| 中航有限公司 | Two thousand and seventeen | Five thousand five hundred |
| 中航有限公司 | Two thousand and sixteen | Five thousand four hundred |
| XYZ 有限公司。 | Two thousand and sixteen | Six thousand five hundred |
| 中航有限公司 | Two thousand and eighteen | Five thousand four hundred |
| XYZ 有限公司。 | Two thousand and seventeen | Four thousand seven hundred |
| XYZ 有限公司。 | Two thousand and eighteen | Five thousand four hundred |

**示例-2:**

```sql
SELECT TOP 10 [Company], [Year], [Amount],
LEAD(Amount, 1) OVER (
PARTITION BY Company
ORDER BY Year DESC
) AS Lead_amount
FROM [CompanySales] ;

```

**输出–**

| 公司 | 年 | 数量 | 潜在顾客数量 |
| --- | --- | --- | --- |
| 中航有限公司 | Two thousand and eighteen | Five thousand four hundred | Five thousand five hundred |
| 中航有限公司 | Two thousand and seventeen | Five thousand five hundred | Five thousand four hundred |
| 中航有限公司 | Two thousand and sixteen | Five thousand four hundred | Five thousand |
| 中航有限公司 | Two thousand and fifteen | Five thousand | 空 |
| XYZ 有限公司。 | Two thousand and eighteen | Five thousand four hundred | Four thousand seven hundred |
| XYZ 有限公司。 | Two thousand and seventeen | Four thousand seven hundred | Six thousand five hundred |
| XYZ 有限公司。 | Two thousand and sixteen | Six thousand five hundred | Four thousand six hundred |
| XYZ 有限公司。 | Two thousand and fifteen | Four thousand six hundred | 空 |