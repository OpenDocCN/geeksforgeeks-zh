# 基本 SQL 命令

> 原文: [https://www.geeksforgeeks.org/basic-sql-commands/](https://www.geeksforgeeks.org/basic-sql-commands/)

**提问:** 考虑下面给出的表格 `ITEM`，将命令写在 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 中 1–10，输出 11–20

## 表: 项目

| **S_No** | **项目名称** | **公司** | **成本** | **采购_数量** | **DOP** |
| :--- | :--- | :--- | :--- | :--- | :--- |
| one | 班长 | 字母表 | Six thousand three hundred | Twenty | 2010-05-30 |
| Two | 中央处理器 | 累积分布函数（Cumulative Distribution Function 的缩写） | Eight thousand | Thirty | 2010-07-23 |
| three | 老鼠 | 菲兹西蒙综合医院 | Two hundred and fifty | Twenty-five | 2010-08-04 |
| four | 不间断电源 | HIJ | Two thousand one hundred | Ten | 2010-06-19 |
| five | 打印机 | JKL | Eight thousand four hundred | four | 2010-11-27 |
| six | 扫描仪 | JKL | Four thousand five hundred | six | 2010-08-14 |

## 编写的 SQL 命令为 1 到 10

### 1. 显示“2010-08-05”之后购买的项目名称和成本。

```sql
Select Item_Name, Cost from ITEM where DOP > "2010-08-05";
```

### 2. 显示按采购日期排列的采购数量大于 10 的物料的信息。

```sql
Select * from ITEM where Purchase_Qty > 10 ORDER BY DOP;
```

### 3. 显示“JKL”公司项目的平均成本价。

```sql
Select avg(cost) from ITEM where Company = "JKL";
```

### 4. 显示名称以字母“M”开头的项目的所有信息。

```sql
Select * from ITEM where Item_Name like "M%";
```

### 5. 显示公司名称中包含字母“J”的项目的最高成本价。

```sql
Select max(Cost) from ITEM where Company like '%J%';
```

### 6. 显示采购数量大于 5 的物料的所有详细信息，按采购日期的降序排列。

```sql
Select * from ITEM where Purchase_Qty > 5 order by DOP desc;
```

### 7. 显示物料号、物料名称和所有物料的成本，其中物料名称的第二位是字母“o”。

```sql
Select S_No, Item_Name, Cost from ITEM where instr(Item_Name, 'o') = 2;
```

### 8. 要显示公司，按购买月份分组的最小购买数量。

```sql
Select Company, min(Purchase_Qty) from ITEM group by month(DOP);
```

### 9. 显示表 `ITEM` 的结构。

```sql
Desc ITEM;
```

### 10. 将采购数量设置为“JKL”公司的 31。

```sql
Update ITEM set Purchase_Qty = 31 where Company = 'JKL';
```

## 为下面的 SQL 查询 11–20 写输出

### 11. 从 `ITEM` 中 `select count(*)` 其中 `Cost > 6000` 和 `Purchase_Qty < 25`；

*输出:*

| **count(*)** |
| :--- |
| Two |

### 12. 从 `ITEM` 中 `select max(Purchase_Qty)` 其中 `Cost < 5000`；

*输出:*

| **max(Purchase_Qty)** |
| :--- |
| Twenty-five |

### 13. 从 `ITEM` 中 `select avg(Cost)` 其中 `Purchase_Qty > 25`；

*输出:*

| **avg(Cost)** |
| :--- |
| Eight thousand |

### 14. 从 `ITEM` 中 `select Cost + 200 as "销售价格"` 其中 `Item_Name = '扫描仪'`；

*输出:*

| **售价** |
| :--- |
| Four thousand seven hundred |

### 15. 从 `ITEM` 中 `select S_No, Item_Name, Purchase_Qty` 其中 `Purchase_Qty >= 10`；

*输出:*

| **S_No** | **项目名称** | **采购_数量** |
| :--- | :--- | :--- |
| one | 班长 | Twenty |
| Two | 中央处理器 | Thirty |
| three | 老鼠 | Twenty-five |
| four | 不间断电源 | Ten |

### 16. 从 `ITEM` 中 `select UCASE(Item_Name), LCASE(Company)`；

*输出:*

| **ucase(item_name)** | **lcase(company)** |
| :--- | :--- |
| 班长 | 字母表 |
| 中央处理器 | 累积分布函数（Cumulative Distribution Function 的缩写） |
| 老鼠 | 菲兹西蒙综合医院 |
| 不间断电源 | hij |
| 打印机 | jkl |
| 扫描仪 | jkl |

### 17. 从 `ITEM` 中 `select S_No, DOP` 其中 `month(DOP) = 8`；

*输出:*

| **S_No** | **DOP** |
| :--- | :--- |
| three | 2010-08-04 |
| six | 2010-08-14 |

### 18. 从 `ITEM` 中 `select avg(Cost), max(Purchase_Qty)`；

*输出:*

| **avg(Cost)** | **max(Purchase_Qty)** |
| :--- | :--- |
| Four thousand nine hundred and twenty-five | Thirty |

### 19. 从 `ITEM` 中 `select Item_Name` 其中 `Item_Name like '%e%'`；

*输出:*

| **项目名称** |
| :--- |
| 老鼠 |
| 打印机 |
| 扫描仪 |

### 20. 从 `ITEM` 中 `select *` 其中 `length(Item_Name) = 3`；

*输出:*

| **S_No** | **项目名称** | **公司** | **成本** | **采购_数量** | **DOP** |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Two | 中央处理器 | 累积分布函数（Cumulative Distribution Function 的缩写） | Eight thousand | Thirty | 2010-07-23 |
| four | 不间断电源 | HIJ | Two thousand one hundred | Ten | 2010-06-19 |