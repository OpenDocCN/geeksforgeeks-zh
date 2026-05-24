# 基本 SQL 命令

> 原文：[https://www.geeksforgeeks.org/basic-sql-commands/](https://www.geeksforgeeks.org/basic-sql-commands/)

## 提问
考虑下面给出的表格 `ITEM`，将命令写在 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 中 1–10，输出 11–20。

### 表：`item`

| `s_no` | `item_name` | `company` | `cost` | `purchase_qty` | `dop` |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 3 | Mouse | FGH | 250 | 25 | 2010-08-04 |

## 编写的 SQL 命令为 1 到 10

**1. 显示“2010-08-05”之后购买的项目名称和成本。**

```sql
Select Item_Name,Cost from ITEM where DOP>"2010-08-05";
```

**2. 显示按采购日期排列的采购数量大于 10 的物料的信息。**

```sql
Select * from ITEM where Purchase_Qty>10 ORDER BY DOP;
```

**3. 显示“JKL”公司项目的平均成本价。**

```sql
Select avg(cost) from ITEM where Company="JKL";
```

**4. 显示名称以字母“M”开头的项目的所有信息。**

```sql
Select * from ITEM where Item_Name like "M%";
```

**5. 显示公司名称中包含字母“J”的项目的最高成本价。**

```sql
Select max(Cost) from ITEM where Company like '%J%;
```

**6. 显示采购数量大于 5 的物料的所有详细信息，按采购日期的降序排列。**

```sql
Select * from ITEM where Purchase_Qty>5 order by DOP desc;
```

**7. 显示物料号、物料名称和所有物料的成本，其中物料名称的第二位是字母“o”。**

```sql
Select S_No,Item_Name,Cost from ITEM where instr(Item_Name,'o')=2;
```

**8. 要显示公司，按购买月份分组的最小购买数量。**

```sql
Select Company,min(Purchase_Qty) from ITEM group by month(DOP);
```

**9. 显示表 `ITEM` 的结构。**

```sql
Desc ITEM;
```

**10. 将采购数量设置为“JKL”公司的 31。**

```sql
Update ITEM set Purchase_Qty=31 where Company='JKL';
```

## 为下面的 SQL 查询 11–20 写输出

**11. 从 `cost` > 6000 和 `purchase_qty` < 25 的项目中选择 `count(*)`；**

**OUTPUT:**

| `count(*)` |
| :--- |
| Two |

**12. 从 `cost` 为 < 5000 的项目中选择 `max(purchase_qty)`；**

**OUTPUT:**

| `max(purchase_qty)` |
| :--- |
| Twenty-five |

**13. 从 `purchase_qty` > 25 的项目中选择 `avg(cost)`；**

**OUTPUT:**

| `avg(cost)` |
| :--- |
| Eight thousand |

**14. 从 `item_name` = ‘Scanner’ 的项目中选择 `cost`+200 作为 “Sales_Price”；**

**OUTPUT:**

| `Sales_Price` |
| :--- |
| Four thousand seven hundred |

**15. 从 `purchase_qty` >= 10 的项目中选择 `s_no`、`item_name`、`purchase_qty`；**

**OUTPUT:**

| `s_no` | `item_name` | `purchase_qty` |
| :--- | :--- | :--- |
| one | monitor | Twenty |
| Two | | |

**16. 从项目中选择 `ucase(item_name)`、`lcase(company)`；**

**OUTPUT:**

| `ucase(item_name)` | `lcase(company)` |
| :--- | :--- |
| CPU | alphabet |
| CDF | |
| Mouse | |

**17. 从项目中选择 `s_no`，`dop`，其中 `month(dop)` = 8；**

**OUTPUT:**

| `s_no` | `dop` |
| :--- | :--- |
| T21 | 2010-08-04 |
| T27 | 2010-08-14 |

**18. 从项目中选择 `avg(cost)`、`max(purchase_qty)`；**

**OUTPUT:**

| `avg(cost)` | `max(purchase_qty)` |
| :--- | :--- |
| Four thousand nine hundred and twenty-five | Thirty |

**19. 从项目中选择 `item_name`，其中 `item_name` 像 “%e%”；**

**OUTPUT:**

| `item_name` |
| :--- |
| Mouse |
| Printer |
| Scanner |

**20. 从 `ITEM` 中选择 `*` 其中 `length(item_name)` = 3；**

**OUTPUT:**

| `s_no` | `item_name` | `company` | `cost` | `purchase_qty` | `dop` |
| :--- | :--- | :--- | :--- | :--- | :--- |