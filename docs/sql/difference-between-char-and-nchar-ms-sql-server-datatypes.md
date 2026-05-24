# char 和 n char 的区别:MS SQL Server 数据类型

> 原文:[https://www . geesforgeks . org/char-and-nchar-ms-SQL-server-data types/](https://www.geeksforgeeks.org/difference-between-char-and-nchar-ms-sql-server-datatypes/)

一个数据库有大量以有组织的格式存储的数据。数据库可能包含存储在其中的各种数据值。为了避免混淆，数据值根据其类型被赋予一个名称。这些被称为数据类型。**数据类型**帮助用户区分不同类别的数据。 [MS SQL Server](https://www.geeksforgeeks.org/introduction-of-ms-sql-server/) 支持多种数据类型，用户可以轻松识别各种类别的数据并据此使用。

**1。字符:**
字符是由单引号引起来的一串单词。在微软的 SQL Server 中，字符被缩短为字符。它是一种只存储非 unicode 数据的数据类型。非 unicode 数据是一种不支持 unicode 标准的格式。它需要 1 字节的数据，最大存储容量为 8000 字节。

**语法–**

```sql
column_name char(number _of_bytes);

```

**2。n-char:**
n-char 也是可以存储 unicode 数据的字符串。nchar 代表民族性格。存储数据需要两个字节，最多可以存储 4000 个字符。Unicode 数据是指字母和其他数据的通用编码标准。每一个都通过指定一个数值来唯一标识。

**语法–**

```sql
column_name nchar(number_of_bytes);

```

**char 和 n char 的区别:MS SQL Server 数据类型:**

<center>

| **充电** | **n-char** |
| 字符存储固定长度的非 unicode 字符。 | n-char 存储固定长度的 unicode 字符。 |
| 一个字节存储数据。 | 两个字节存储数据。 |
| char 最多存储 8000 字节。 | n-char 最多存储 4000 字节。 |
| 它是广泛首选的数据类型。 | 它不太受欢迎。 |
| 它使用 Unicode 标准来存储数据。 | 它使用 ASCII 标准来存储数据。 |
| **语法:**

```sql
col_name char(n); 
```

*n 是字节数。 | **语法:**

```sql
col_name nchar(n); 
```

*n 是字节数。 |
| 字节数不是必须指定的。它会自动采用默认值 1，并将其转换为 ASCII 格式。 | 为了将数据转换为 Unicode 格式，必须指定 nchar 中的字母 n(国家)。 |

</center>