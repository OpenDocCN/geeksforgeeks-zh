# SQL COUNT()、AVG()和 SUM()

> 原文:[https://www.geeksforgeeks.org/sql-count-avg-and-sum/](https://www.geeksforgeeks.org/sql-count-avg-and-sum/)

## 1. SQL COUNT() 函数
`COUNT()` 函数提供符合指定条件的行数。

**`COUNT()` 语法：**
```sql
SELECT COUNT(column_name)
FROM table_name
WHERE condition;
```

## 2. SQL AVG() 函数
`AVG()` 函数提供数值列的平均值。

**`AVG()` 语法：**
```sql
SELECT AVG(column_name)
FROM table_name
WHERE condition;
```

## 3. SQL SUM() 函数
`SUM()` 函数提供数值列的总和。

**`SUM()` 语法：**
```sql
SELECT SUM(column_name)
FROM table_name
WHERE condition;
```

我们假设有一个表名为 `GeeksTab`。

| 名字 | 城市 | 薪水 | 身份证明 | (美)司法部(Department of Justice) |
| --- | --- | --- | --- | --- |
| 字母表 | 德里 | Four thousand five hundred | One hundred and thirty-four | 8 月 6 日 |
| 弥漫性嗜酸细胞增多性筋膜炎 | 无聊死了 | Six thousand five hundred | Two hundred and forty-five | 3 月 4 日至 |
| 极好的 | 斋浦尔 | Five thousand four hundred | Five hundred and forty-six | 7 月 2 日至 |
| Mno | 无聊死了 | Seven thousand eight hundred | Four hundred and thirty-two | 6 月 7 日至 |
| Jkl | 斋浦尔 | Five thousand four hundred | Seven hundred and sixty-eight | 7 月 9 日至 |
| 负载匹配网络（Load Matching Network） | 德里 | Seven thousand eight hundred | Nine hundred and eighty-seven | 6 月 8 日至 |
| Ijk | 斋浦尔 | Six thousand seven hundred | Six hundred and fifty-four | 6 月 5 日至 |

## 4. COUNT() 示例
以下 SQL 语句查找 `GeeksTab` 表中 `Name` 的数量：
```sql
SELECT COUNT(Name)
FROM GeeksTab;
```
**输出：**
```sql

```

## 5. AVG() 示例
以下 SQL 语句查找 `GeeksTab` 表中 `Salary` 的平均值：
```sql
SELECT AVG(Salary)
FROM GeeksTab;
```
**输出：**
```sql

```

## 6. SUM() 示例
以下 SQL 语句将查找 `GeeksTab` 表中 `Salary` 的总和：
```sql
SELECT SUM(Salary)
FROM GeeksTab;
```
**输出：**
```sql

```