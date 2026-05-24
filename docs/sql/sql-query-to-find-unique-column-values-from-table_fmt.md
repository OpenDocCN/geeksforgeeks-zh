# 从表中查找唯一列值的 SQL 查询

> 原文：[https://www.geeksforgeeks.org/sql-query-to-find-unique-column-values-from-table/](https://www.geeksforgeeks.org/sql-query-to-find-unique-column-values-from-table/)

我们取了一个名为 `Geeks` 的示例表，并通过对其应用各种 SQL 查询来返回唯一的列值。

**Table –** `Geeks`

| `G_ID` | `FIRST_NAME` | `LAST_NAME` | `JOINING_DATE` | `DEPARTMENT` |
| --- | --- | --- | --- | --- |
| one | 莫汉 | 阿罗拉 | 7-08-2019 | 工商管理学博士(Doctor of Business Administration) |
| Two | 妮莎 | 维尔马 | 25-03-2017 | 管理 |
| three | 他在钓鱼 | 笈多王朝 | 9-01-2020 | 工商管理学博士(Doctor of Business Administration) |
| four | 前岛亚美 | 辛格 | 5-12-2017 | 作者 |
| five | 他在钓鱼 | 巴蒂 | 3-05-2018 | 管理 |
| six | Vinod | 地万 | 19-04-2018 | 回顾 |
| seven | 片状 | 库马尔 | 5-01-2017 | 回顾 |
| eight | 吉塔 | Chauan | 5-02-2019 | 管理 |
| nine | 白腹长尾猴 | 米什拉 | 15-01-2018 | 作者 |

## 从 `Geeks` 表中查找列 `DEPARTMENT` 唯一值的 SQL 查询

```sql
SELECT DISTINCT DEPARTMENT 
FROM Geeks;
```

**输出–**

| `DEPARTMENT` |
| --- |
| 管理 |
| 工商管理学博士(Doctor of Business Administration) |
| 回顾 |
| 作者 |

## SQL 查询找到列 `DEPARTMENT` 所在名称为“DBA”的明细

```sql
SELECT * 
FROM Geeks 
WHERE DEPARTMENT LIKE 'DBA%';
```

**输出–**

| `G_ID` | `FIRST_NAME` | `LAST_NAME` | `JOINING_DATE` | `DEPARTMENT` |
| --- | --- | --- | --- | --- |
| one | 莫汉 | 阿罗拉 | 7-08-2019 | 工商管理学博士(Doctor of Business Administration) |
| three | 他在钓鱼 | 笈多王朝 | 9-01-2020 | 工商管理学博士(Doctor of Business Administration) |

## SQL 查询找到部门‘Admin’中的行数

```sql
SELECT COUNT(*) 
FROM Geeks 
WHERE DEPARTMENT = 'Admin';
```

**输出–**

| `(No column name)` |
| --- |
| three |