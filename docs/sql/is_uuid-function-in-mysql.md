# MySQL 中的 IS_UUID()函数

> 原文:[https://www.geeksforgeeks.org/is_uuid-function-in-mysql/](https://www.geeksforgeeks.org/is_uuid-function-in-mysql/)

MySQL 中的这个函数用于检查给定的通用唯一标识符(UUID)是否有效。如果参数是有效的字符串格式 UUID，则返回 1；如果参数不是有效的 UUID，则返回 0；如果参数为空，则返回空。

以下是 MySQL 中有效的字符串格式 UUID:

```sql
aaaaaaaa-bbbb-cccc-dddd-eeeeeeeeeeee
aaaaaaaabbbbccccddddeeeeeeeeeeee
{aaaaaaaa-bbbb-cccc-dddd-eeeeeeeeeeee}

```

**语法:**

```sql
IS_UUID(string_uuid) 
```

**参数:**该方法接受一个参数。

*   **string _ uuid–**输入我们要检查的 uuid。

**返回:**
如果 UUID 有效则返回 1，如果无效则返回 0。

**示例-1 :**
借助 UUID 函数检查给定的通用唯一标识符值是否有效。因为它是 3 种有效字符串格式之一，所以我们将得到 1 的结果。我们可以看到给定的 UUID 是‘aaaaaaaaaa-bbbb-cccc-dddd-eeeeeeeeee’格式。

```sql
SELECT IS_UUID('3aad549b-acbd-4318-6498-3b0a656024bc') 
AS ValidOrNot;

```

**输出:**

| 有效与否 |
| --- |
| one |

**示例-2 :**
借助 UUID 函数检查给定的通用唯一标识符值是否有效。因为它是 3 种有效字符串格式之一，所以我们将得到 1 的结果。我们可以看到给定的 UUID 是“aaaaaaaabbbbccccddddeeeeeeeeeeee”格式。

```sql
SELECT IS_UUID('1cda554accab231487411a9a656824cc') 
AS ValidOrNot;

```

**输出:**

| 有效与否 |
| --- |
| one |

**示例-3 :**
借助 UUID 函数检查给定的通用唯一标识符值是否有效。因为它是 3 种有效字符串格式之一，所以我们将得到 1 的结果。我们可以看到，给定的 UUID 采用的是“{ aaaaaaaa-bbbb-cccc-dddd-eeeeeeee }”格式。

```sql
SELECT IS_UUID('{9dcd767a-ccaa-1532-3245-5b8c874124aa}') 
AS ValidOrNot;

```

**输出:**

| 有效与否 |
| --- |
| one |

**示例-4 :**
借助 UUID 函数检查给定的通用唯一标识符值是否有效。因为它不是 3 种有效字符串格式中的一种，所以我们将在结果中得到 0。

```sql
SELECT IS_UUID('7acd798c-daba-6731-4123-8b8c7751') 
AS ValidOrNot;

```

**输出:**

| 有效与否 |
| --- |
| Zero |

**例-5 :**
借助 UUID 函数检查 RAND()函数给出的结果是否为有效的通用唯一标识符。

```sql
SELECT IS_UUID(RAND()) 
AS ValidOrNot;

```

**输出:**

| 有效与否 |
| --- |
| Zero |

所以，我们可以看到 RAND()函数给出的结果不是有效的 UUID。