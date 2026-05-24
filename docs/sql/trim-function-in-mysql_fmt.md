# MySQL中的TRIM()函数

> 原文: [https://www.geeksforgeeks.org/trim-function-in-mysql/](https://www.geeksforgeeks.org/trim-function-in-mysql/)

## 介绍

MySQL中的`TRIM()`函数用于清理数据。它还用于删除字符串中不需要的前导和尾随字符。

## 语法

```sql
TRIM([{BOTH | LEADING | TRAILING} [remstr] FROM] str)
```

## 参数

此方法接受三个参数，如下所述：

*   **`BOTH | LEADING | TRAILING`**：这些选项明确指示`TRIM()`函数从字符串中删除前导、尾随或前导和尾随的不必要字符。默认情况下，`TRIM()`函数使用`BOTH`选项。
*   **`remstr`**：是我们要删除的字符串。如果未给出，则删除空格。
*   **`str`**：标识我们要从中移除`remstr`的字符串。

## 返回值

返回一个去掉了多余字符的字符串。

## 示例

### 示例-1
`TRIM()`函数仅删除前导空格。

```sql
SELECT TRIM(LEADING FROM "    www.geeksforgeeks.org    ") AS TrimmedString;
```

**输出:**

| TrimmedString |
| --- |
| www.geeksforgeeks.org    |

### 示例-2
`TRIM()`函数只删除尾随空格。

```sql
SELECT TRIM(TRAILING FROM "    www.geeksforgeeks.org    ") AS TrimmedString;
```

**输出:**

| TrimmedString |
| --- |
|     www.geeksforgeeks.org |

### 示例-3
`TRIM()`函数删除前导和尾随空格。

```sql
SELECT TRIM("    www.geeksforgeeks.org    ") AS TrimmedString;
```

**输出:**

| TrimmedString |
| --- |
| www.geeksforgeeks.org |

### 示例-4
带有表格数据的`TRIM()`函数。

**表: `Student_Details`**

| `student_id` | `student_name` |
| --- | --- |
| 101 | Rohit |
| 103 | Sika |

**输出:**

| Trimming string |
| --- |
| Rohit |
| Sika |