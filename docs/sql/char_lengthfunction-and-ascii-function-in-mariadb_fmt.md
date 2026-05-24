# MariaDB 中的 `CHAR_LENGTH()` 函数和 `ASCII()` 函数

> 原文: [https://www.geeksforgeeks.org/char_length-function-and-ascii-function-in-mariadb/](https://www.geeksforgeeks.org/char_length-function-and-ascii-function-in-mariadb/)

## 1. `CHAR_LENGTH()` 函数
在 MariaDB 中，`CHAR_LENGTH()` 函数用于计算字符串的总字符长度。该函数接受一个字符串作为参数，并返回该字符串的长度，返回值为数字类型。

### 语法
```sql
CHAR_LENGTH(string)
```

### 参数
- `string`：必选。需要计算长度的字符串。

### 示例-1
```sql
SELECT CHAR_LENGTH('GEEKSFORGEEKS');
```
**输出:**
```sql

```

### 示例-2
```sql
SELECT CHAR_LENGTH(' ');
```
**输出:**
```sql

```

### 示例-3
```sql
SELECT CHAR_LENGTH('');
```
**输出:**
```sql

```

### 示例-4
```sql
SELECT CHAR_LENGTH(NULL);
```
**输出:**
```sql
NULL
```

## 2. `ASCII()` 函数
在 MariaDB 中，`ASCII()` 函数用于查找字符串中最左边字符的 ASCII 值。该函数接受一个字符串作为参数，并返回其最左边字符的 ASCII 值。

### 语法
```sql
ASCII(single_character)
```

### 参数
- `single_character`：必选。如果传入超过一个字符，函数将忽略除第一个字符之外的所有字符。

### 示例-1
```sql
SELECT ASCII('GeeksForGeeks');
```
**输出:**
```sql

```

### 示例-2
```sql
SELECT ASCII('G');
```
**输出:**
```sql

```

### 示例-3
```sql
SELECT ASCII('g');
```
**输出:**
```sql

```

### 示例-4
```sql
SELECT ASCII('7');
```
**输出:**
```sql

```