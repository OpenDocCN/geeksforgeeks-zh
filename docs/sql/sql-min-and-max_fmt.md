# SQL MIN()和 MAX()

> 原文:[https://www.geeksforgeeks.org/sql-min-and-max/](https://www.geeksforgeeks.org/sql-min-and-max/)

## SQL MIN() Functions
`MIN()`函数提供所选列的最小值。

**MIN()语法–**
```sql
SELECT MIN(column_name)
FROM table_name
WHERE condition;
```

## SQL MAX() Functions
`MAX()`函数提供所选列的最大值。

**MAX()语法–**
```sql
SELECT MAX(column_name)
FROM table_name
WHERE condition;
```

让我们假设，我们有下表`GeeksTable`:

| 名字 | 城市 | 数字 | 薪水 | 告发 |
| --- | --- | --- | --- | --- |
| 字母表 | 德里 | One hundred and twenty-three | Four thousand | 8 月 4 日 |
| 极好的 | 孟买 | Three hundred and thirty-five | Three thousand | 6 月 7 日至 |
| Mno | 德里 | Five hundred and sixty-seven | Two thousand nine hundred | 4 月 9 日至 |
| 字母表 | 无聊死了 | Four hundred and fifty-seven | Three thousand four hundred and fifty | 7 月 12 日至 |
| Xyz | 斋浦尔 | Eight hundred and seventy-six | Eight thousand seven hundred and fifty | 3 月 9 日至 |
| 荷航 | 德里 | Two hundred and thirty-four | Five thousand five hundred | 1 月 23 日至 |

### MIN() Example :
以下SQL语句查找最低薪资：
```sql
SELECT MIN(Salary) FROM GeeksTable;
```
**输出–**
```sql

```

### MAX() Example :
以下SQL语句查找最高薪资：
```sql
SELECT MAX(Price) FROM GeeksTable;
```
**输出–**
```sql

```