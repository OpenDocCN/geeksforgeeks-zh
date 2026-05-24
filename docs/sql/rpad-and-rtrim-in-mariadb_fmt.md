# MariaDB中的RPAD()和RTRIM()

> 原文: [https://www.geeksforgeeks.org/rpad-and-rtrim-in-mariadb/](https://www.geeksforgeeks.org/rpad-and-rtrim-in-mariadb/)

## 1. RPAD函数

在MariaDB中，`RPAD()`函数用于将字符串向右填充至指定长度。该函数的第一个参数是字符串，第二个参数是长度，第三个参数是填充字符串。此函数返回指定长度的右填充字符串。如果字符串长于指定长度，`RPAD()`函数将从字符串右侧删除字符，将其缩短为指定长度。

### 语法

```sql
RPAD( string, length, pad_string )
```

### 参数

*   `string` – 要向右填充的字符串。
*   `length` – 字符串右填充后的结果长度。
*   `pad_string` – 用于向右填充到`string`的指定字符串。

### 返回值

它返回一个用指定字符串右填充到一定长度的字符串。

### 示例-1

```sql
SELECT RPAD('geeksforgeeks.org', 20, 'A');
```

**输出:**

```sql
'geeksforgeeks.orgAAA'
```

### 示例-2

```sql
SELECT RPAD('Computer', 2, 'b');
```

**输出:**

```sql
'Co'
```

### 示例-3

```sql
SELECT RPAD('Database', 10, 'xyz');
```

**输出:**

```sql
'Databasexy'
```

### 示例-4

```sql
SELECT RPAD('Post', 7, ' ');
```

**输出:**

```sql
'Post   '
```

## 2. RTRIM()函数

在MariaDB中，`RTRIM()`函数用于删除字符串右侧的所有空格字符。该函数的第一个参数是字符串。这与`LTRIM()`功能相反，它将删除右侧的所有空格。

### 语法

```sql
RTRIM( string )
```

### 参数

*   `string` – 要从右侧修剪空格字符的字符串。

### 返回值

它会返回右侧没有空格的字符串。

### 示例-1

```sql
SELECT RTRIM('geeksforgeeks    ');
```

**输出:**

```sql
'geeksforgeeks'
```

### 示例-2

```sql
SELECT RTRIM('    gfg is the best portal    ');
```

**输出:**

```sql
'    gfg is the best portal'
```

### 示例-3

```sql
SELECT RTRIM('arti@cle@!!!');
```

**输出:**

```sql
'arti@cle@!!!'
```