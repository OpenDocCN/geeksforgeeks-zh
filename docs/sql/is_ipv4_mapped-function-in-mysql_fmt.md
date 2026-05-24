# MySQL 中的 `IS_IPV4_MAPPED()` 函数

> 原文: [https://www.geeksforgeeks.org/is_ipv4_mapped-function-in-mysql/](https://www.geeksforgeeks.org/is_ipv4_mapped-function-in-mysql/)

`IS_IPV4_MAPPED()` 函数将 IPv6 地址（以数字形式表示为二进制字符串，由 `INET6_ATON` 函数返回）作为输入。如果参数是有效的 IPv4 映射的 IPv6 地址，则返回 1，否则返回 0。IPv4 映射地址的一般形式是 `::ffff:IPv4_address`。

## 语法

```sql
IS_IPV4_MAPPED(expr)
```

## 参数

该函数接受一个参数。

*   `expr` – 表示 IPv6 地址的字符串。

## 返回值

*   如果字符串是有效的 IPv4 映射 IPv6 地址，则返回 1。
*   如果字符串不是有效的 IPv4 映射 IPv6 地址，则返回 0。

## 示例

### 示例 1

使用 `IS_IPV4_MAPPED` 函数检查给定地址 `'::12.10.15.8'` 是否有效。由于给定的输入不是有效的 IPv4 映射地址，它将返回 0。

```sql
SELECT IS_IPV4_MAPPED(INET6_ATON('::12.10.15.8')) AS IS_IPV4_MAPPED;
```

**输出:**

| IS_IPV4_MAPPED |
| :------------- |
| 0              |

### 示例 2

使用 `IS_IPV4_MAPPED` 函数检查给定地址 `'::ffff:8.7.12.3'` 是否有效。由于这里给定的输入是有效的 IPv4 映射地址，它将返回 1。

```sql
SELECT IS_IPV4_MAPPED(INET6_ATON('::ffff:8.7.12.3')) AS IS_IPV4_MAPPED;
```

**输出:**

| IS_IPV4_MAPPED |
| :------------- |
| 1              |

### 示例 3

使用 `IS_IPV4_MAPPED` 函数检查给定地址 `'ff::9.6.10.11'` 是否有效。由于给定的输入不是有效的 IPv4 映射地址，它将返回 0。

```sql
SELECT IS_IPV4_MAPPED(INET6_ATON('ff::9.6.10.11')) AS IS_IPV4_MAPPED;
```

**输出:**

| IS_IPV4_MAPPED |
| :------------- |
| 0              |

### 示例 4

使用 `IS_IPV4_MAPPED` 函数检查给定的 IPv6 地址 `'::1'` 是否有效。

```sql
SELECT IS_IPV4_MAPPED(INET6_ATON('::1')) AS IS_IPV4_MAPPED;
```

**输出:**

| IS_IPV4_MAPPED |
| :------------- |
| 0              |