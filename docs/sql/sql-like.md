# SQL | LIKE

> 原文:[https://www.geeksforgeeks.org/sql-like/](https://www.geeksforgeeks.org/sql-like/)

有时我们可能需要数据库中匹配特定模式的元组。例如，我们可能希望检索元组以字母“y”开头的所有列，或者以“b”开头、以“l”结尾的所有列，或者更复杂、更严格的字符串模式。这就是 LIKE 子句的用处，通常与 SQL 中的 where 子句结合使用。

过滤出结果的通配符有两种:

*   %: used to match zero or more characters. (variable length)
*   _: Used to exactly match a character. (Fixed length)

以下是 LIKE 子句的模式匹配规则:

| model | intend |
| 【a %】 | Match with "a" |
| % a | Match with "a" |
| 【a %】【t】 | Ending string of |
| “% wow %” | Match the string containing the substring "wow" at any position. |
| _ wow % ' | Match the string containing the substring "wow" to the second position. |
| _ a % ' | Match the string with' a' in the second position. |
| 【a _ _ %】 | Matches a string that begins with "a" and contains at least 2 characters. |

**示例:**

假设我们有关系，供应商。我们希望使用 LIKE 子句测试各种模式:

**供应商表:** T42T44】S5T46】哈里什父子 T48】古尔冈、NCRT50T52】S6T54】Om 供应商 T56】2/1、法里达巴德、哈里亚纳 T58

| Supplier ID | name | address |
| S1 | Paragon supplier | 21-3, Okola, Delhi |
| S2 | Mango | 21\. Faridabad and Haryana |
| S3 Delhi |

**示例查询和输出:**

```sql
SELECT SupplierID, Name, Address
FROM Suppliers
WHERE Name LIKE 'Ca%';

```

**输出:**T13】S4

| 【S3】 | Biz Canada | 6/7, Okra II, Delhi |
| Caravan merchant | 2-A, Pitampura, Delhi |

T0】

**产量:**

| 【S1】 | Paragon supplier | 21-3, Okra, Delhi |
| S3 | Biz Canada | 6/7, Okra II, Delhi |

T0】

**输出:**

| 【S2】 | Mango | 21\. Faridabad and Haryana |

**应用:**LIKE 运算符在地址过滤等情况下资源极其丰富，在这些情况下，我们只知道整个地址的一部分或一部分(如地点或城市)，并希望基于此检索结果。可以根据需要利用通配符来产生更好、更过滤的元组。

本文由 **Anannya Uberoi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。