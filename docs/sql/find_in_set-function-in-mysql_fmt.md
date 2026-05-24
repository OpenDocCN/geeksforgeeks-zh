# MySQL 中的 `FIND_IN_SET()` 函数

> 原文: [https://www.geeksforgeeks.org/find_in_set-function-in-mysql/](https://www.geeksforgeeks.org/find_in_set-function-in-mysql/)

`FIND_IN_SET()` 函数用于查找字符串在字符串列表中的位置。如果字符串重复多次，输出将是该字符串的第一个位置。

## 注意点

*   如果在字符串列表中找不到字符串，则结果为 `0`。
*   如果字符串或字符串列表为空，则结果为 `NULL`。
*   如果 `string_list` 是空字符串(`""`)，则结果为 `0`。

## 语法

```sql
FIND_IN_SET("string", "string_list")
```

**注意:** 参数 `string` 是搜索 `string_list` 的必选项；`string_list` 是字符串值的列表。

## 示例

### 示例-1
在字符串列表中搜索 `"a"`:

```sql
SELECT FIND_IN_SET("a", "g, e, e, k, s, f, o, r, g, e, e, k, s"); 
```

**结果–**

| FIND_IN_SET("a", "geeksforgeeks") |
| --- |
| 0 |

### 示例-2
在字符串列表中搜索 `"a"` (字符串列表为 `NULL`) :

```sql
SELECT FIND_IN_SET("a", null); 
```

**结果–**

| FIND_IN_SET("a", NULL) |
| --- |
| NULL |

### 示例-3
在字符串列表中搜索 `"g"`:

```sql
SELECT FIND_IN_SET("g", "g, e, e, k, s, f, o, r, g, e, e, k, s"); 
```

**结果–**

| FIND_IN_SET("g", "g, e, e, k, s, f, o, r, g, e, e, k, s") |
| --- |
| 1 |