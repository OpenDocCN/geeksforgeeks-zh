# MS Access中的`Left()`和`Right()`功能

> 原文：`https://www.geeksforgeeks.org/left-and-right-function-in-ms-access/`

## `Left()`函数：
在 MS Access 中，`Left()`函数从字符串的左边提取字符串。在`Left()`函数中，将传递字符串和字符串的编号。它将从字符串的左边返回大小为传递号的字符串。

**语法：**

```sql
Left(string, number_of_chars)
```

**示例-1：**

```sql
SELECT Left("GEEKSFORGEEKS", 3) AS ExtractString;
```

**输出：**

| `ExtractString` |
| :--- |
| `GEE` |

**示例-2：**

```sql
SELECT Left("GEEKSFORGEEKS", 10) AS ExtractString;
```

**输出：**

| `ExtractString` |
| :--- |
| `GEEKSFORGE` |

## `Right()`函数：
`Right()`函数的工作方式与`Left()`函数类似，但它从字符串的右端提取字符串。在这种情况下，将提取的字符串和字符串大小将作为参数传递。

**语法：**

```sql
Right(string, number_of_chars)
```

**示例-1：**

```sql
SELECT Right("GEEKSFORGEEKS", 4) AS ExtractString;
```

**输出：**

| `ExtractString` |
| :--- |
| `EEKS` |

**示例-2：**

```sql
SELECT Right("GEEKSFORGEEKS", 8) AS ExtractString;
```

**输出：**

| `ExtractString` |
| :--- |
| `SFORGEEKS` |