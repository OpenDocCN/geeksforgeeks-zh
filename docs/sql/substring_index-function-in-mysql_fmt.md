# MySQL 中的 `SUBSTRING_INDEX()` 函数

> 原文: [`https://www.geeksforgeeks.org/substring_index-function-in-mysql/`](https://www.geeksforgeeks.org/substring_index-function-in-mysql/)

`SUBSTRING_INDEX()` 函数在 MySQL 中用于返回分隔符出现指定次数之前的字符串中的子字符串。

## 语法:

```sql
SUBSTRING_INDEX( str, delim, count )
```

## 参数:

这个方法接受三个参数，如下所述：

*   `str`: 我们要从中创建子字符串的原始字符串。
*   `delim`: 作为分隔符的字符串。函数在搜索分隔符时执行区分大小写的匹配。
*   `count`: 标识分隔符的搜索次数。它可以是正数或负数。如果是正数，此函数返回分隔符左侧的所有内容。如果是负数，此函数将返回分隔符右侧的所有内容。

## 返回:

返回给定字符串的子串。

## 示例-1 :

`SUBSTRING_INDEX()` 函数，分隔符出现次数为正数。

```sql
SELECT SUBSTRING_INDEX("www.geeksforgeeks.org", ".", 2) as Sub_Str;
```

**输出:**

| Sub_Str |
| --- |
| www.geeksforgeeks |

## 示例-2 :

`SUBSTRING_INDEX()` 函数，分隔符出现次数为负数。

```sql
SELECT SUBSTRING_INDEX("www.geeksforgeeks.org", ".", -2) as Sub_Str;
```

**输出:**

| Sub_Str |
| --- |
| org |

## 示例-3 :

`SUBSTRING_INDEX()` 函数，带有表数据。

**表: 员工 (Employee):**

| Employee_Id | Address |
| --- | --- |
| 101 | 700000 Calcutta W.B. |
| 102 | 735102 Jalpaiguri W.B. |
| 103 | 71101 Midnapore W |

现在，我们将使用 `SUBSTRING_INDEX` 函数找到每个员工的 pin 码地址。

```sql
SELECT SUBSTRING_INDEX(Address, ' ', 1 ) AS Pin_Num FROM Employee;
```

**输出:**

| Pin_Num |
| --- |
| 700000 |
| 735102 |
| 71101 |