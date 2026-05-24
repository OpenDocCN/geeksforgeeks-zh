# MySQL 中的 `INET6_NTOA()` 函数

> 原文：[https://www.geeksforgeeks.org/inet6_ntoa-function-in-mysql/](https://www.geeksforgeeks.org/inet6_ntoa-function-in-mysql/)

`INET6_NTOA()` 函数将 IPv6 或 IPv4 网络地址的数字形式（二进制字符串）转换为其可读的字符串表示形式，并以连接字符集的字符串返回。如果地址无效，它将返回 `NULL`。

## 语法

```sql
INET6_NTOA(expr)
```

## 参数

该函数只接受一个参数。

*   `expr`：输入的 IPv4 或 IPv6 地址。

## 返回值

它返回地址的字符串表示形式。

## 示例-1

在 `INET6_NTOA()` 和 `UNHEX()` 函数的帮助下，检查地址 `'0A000511'` 的等效点分字符串表示形式。由于这是一个有效的 IPv4 地址，我们将得到一个点分字符串的结果。

```sql
SELECT INET6_NTOA(UNHEX('0A000511')) 
AS Address_In_DottedString ;
```

**输出：**

| Address_In_DottedString |
| --- |
| 10.0.5.17 |

## 示例-2

在 `INET6_NTOA()` 和 `UNHEX()` 函数的帮助下，检查地址 `'FCBE0000000000005C34CABDFEFA6312'` 的等效点分字符串表示形式。由于这是一个有效的 IPv6 地址，我们将以点分字符串的形式得到结果。

```sql
SELECT INET6_NTOA(UNHEX('FCBE0000000000005C34CABDFEFA6312')) 
AS Address_In_DottedString ;
```

**输出：**

| Address_In_DottedString |
| --- |
| fcbe::5c34:cabd:fefa:6312 |

## 示例-3

借助 `INET6_NTOA()` 和 `UNHEX()` 函数，检查地址 `'456A'` 的等效点分字符串表示。由于它不是有效的 IPv6 或 IPv4 地址，我们将得到一个空结果。

```sql
SELECT INET6_NTOA(UNHEX('456A')) 
AS Address_In_DottedString ;
```

**输出：**

| Address_In_DottedString |
| --- |
| NULL |

## 示例-4

借助 `INET6_NTOA()` 和 `INET6_ATON()` 函数，检查地址 `'9.7.5.8'` 的等效点分字符串表示形式。由于它是一个有效的 IPv4 地址，我们将以点分字符串的形式获得结果。

```sql
SELECT INET6_NTOA(INET6_ATON('9.7.5.8')) 
AS Address_In_DottedString ;
```

**输出：**

| Address_In_DottedString |
| --- |
| 9.7.5.8 |