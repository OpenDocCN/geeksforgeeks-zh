# SQL | LIKE

> 原文: [https://www.geeksforgeeks.org/sql-like/](https://www.geeksforgeeks.org/sql-like/)

有时我们可能需要数据库中匹配特定模式的元组。例如，我们可能希望检索元组以字母“y”开头的所有列，或者以“b”开头、以“l”结尾的所有列，或者更复杂、更严格的字符串模式。这就是 `LIKE` 子句的用处，通常与 SQL 中的 `where` 子句结合使用。

## 通配符

过滤出结果的通配符有两种：

*   `%`: 用于匹配零个或多个字符。（可变长度）
*   `_`: 用于精确匹配一个字符。（固定长度）

## 模式匹配规则

以下是 `LIKE` 子句的模式匹配规则：

| 模式 | 含义 |
| :--- | :--- |
| `'a%'` | 匹配以 "a" 开头的字符串。 |
| `'%a'` | 匹配以 "a" 结尾的字符串。 |
| `'%a%`' | 匹配包含 "a" 的字符串。 |
| `'_a%'` | 匹配第二个字符是 "a" 的字符串。 |
| `'a__%'` | 匹配以 "a" 开头且至少包含 2 个字符的字符串。 |
| `'%wow%'` | 匹配在任何位置包含子串 "wow" 的字符串。 |
| `'_wow%'` | 匹配 "wow" 从第二个位置开始的字符串。 |

## 示例

假设我们有关系 `Suppliers`。我们希望使用 `LIKE` 子句测试各种模式：

**供应商表：**

| Supplier ID | Name | Address |
| :--- | :--- | :--- |
| S1 | Paragon supplier | 21-3, Okola, Delhi |
| S2 | Mango | 21, Faridabad and Haryana |
| S3 | Biz Canada | 6/7, Okra II, Delhi |
| S4 | Caravan merchant | 2-A, Pitampura, Delhi |

### 示例查询和输出

```sql
SELECT SupplierID, Name, Address
FROM Suppliers
WHERE Name LIKE 'Ca%';
```

**输出：**

| Supplier ID | Name | Address |
| :--- | :--- | :--- |
| S4 | Caravan merchant | 2-A, Pitampura, Delhi |

```sql
SELECT SupplierID, Name, Address
FROM Suppliers
WHERE Address LIKE '%Delhi';
```

**输出：**

| Supplier ID | Name | Address |
| :--- | :--- | :--- |
| S1 | Paragon supplier | 21-3, Okola, Delhi |
| S3 | Biz Canada | 6/7, Okra II, Delhi |
| S4 | Caravan merchant | 2-A, Pitampura, Delhi |

```sql
SELECT SupplierID, Name, Address
FROM Suppliers
WHERE SupplierID LIKE '_2';
```

**输出：**

| Supplier ID | Name | Address |
| :--- | :--- | :--- |
| S2 | Mango | 21, Faridabad and Haryana |

## 应用

`LIKE` 运算符在地址过滤等情况下极其有用，在这些情况下，我们只知道整个地址的一部分或一部分（如地点或城市），并希望基于此检索结果。可以根据需要利用通配符来产生更好、更精确的过滤结果。

本文由 **Anannya Uberoi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。