# MySQL 中的 `INET_ATON()` 函数

> 原文: [https://www.geeksforgeeks.org/inet_aton-function-in-mysql/](https://www.geeksforgeeks.org/inet_aton-function-in-mysql/)

`INET_ATON()` 函数将 IPv4 地址的四点表示作为字符串，并以整数的形式返回给定 IP 地址的数值。如果输入地址不是有效的 IPv4 地址，该函数返回空值。返回地址由以下公式计算：

如果给定的输入 IPv4 地址是 `a.b.c.d`，则返回值 `a×256³ + b×256² + c×256¹ + d`。

## 语法

```sql
INET_ATON(expr)
```

## 参数

此方法只接受一个参数。

*   `expr` – 输入由字符串表示的 IPv4 地址。

## 返回

它返回给定 IPv4 地址的数值。

## 示例-1

借助 `INET_ATON` 函数检查以下地址“1.6.5.0”的等效整数表示。由于这是一个有效的 IPv4 地址，我们将得到一个整数的结果。

```sql
SELECT INET_ATON('1.6.5.0') AS AddressInInteger;
```

### 输出

| AddressInInteger |
| :--------------- |
| 17171712         |

## 示例-2

借助 `INET_ATON` 函数检查以下地址“::1.6”的等效整数表示。由于它不是有效的 IPv4 地址，我们将得到空值。

```sql
SELECT INET_ATON('::1.6') AS AddressInInteger;
```

### 输出

| AddressInInteger |
| :--------------- |
| NULL             |

## 示例-3

借助 `INET_ATON` 函数检查以下地址“115.16.55.255”的等效整数表示。由于这是一个有效的 IPv4 地址，我们将得到一个整数的结果。

```sql
SELECT INET_ATON('15.16.55.255') AS AddressInInteger;
```

### 输出

| AddressInInteger |
| :--------------- |
| 252721151        |

## 示例-4

借助 `INET_ATON` 函数检查以下 IPv6 地址“fdfe::5a55:caff:fefa:9089”的等效整数表示形式。

```sql
SELECT INET_ATON('fdfe::5a55:caff:fefa:9089') AS AddressInInteger;
```

### 输出

| AddressInInteger |
| :--------------- |
| NULL             |