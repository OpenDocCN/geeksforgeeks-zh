# MySQL 中的 INET6_NTOA()函数

> 原文:[https://www.geeksforgeeks.org/inet6_ntoa-function-in-mysql/](https://www.geeksforgeeks.org/inet6_ntoa-function-in-mysql/)

inet 6 _ ntoa():

MySQL 中的这个函数将 IPv6 或 IPv4 网络地址以数字形式表示为二进制字符串，并将该地址的字符串表示形式作为连接字符集的字符串返回。如果地址无效，它将返回空值。

**语法:**

```sql
INET6_NTOA(expr)
```

**参数:**该函数只接受一个参数。

*   **expr–**
    输入 IPv4 或 IPv6 地址

**返回:**

它返回地址的字符串表示形式

**示例-1 :**

在 INET6_NTOA 和 UNHEX 函数的帮助下，检查以下地址“0A000511”的等效四点字符串表示形式。由于这是一个有效的 IPv4 地址，我们将得到一个点串的结果。

```sql
SELECT INET6_NTOA(UNHEX('0A000511')) 
AS Address_In_DottedString ;
```

**输出:**

<figure class="table">

| 地址 _ 输入 _ 打点字符串 |
| --- |
| 10 . 0 . 5 . 17 |

</figure>

**示例-2 :**

在 INET6_NTOA 和 UNHEX 函数的帮助下，检查以下地址“fcbe 00000000005 c34 abdfefa 6312”的等效四点字符串表示形式。因为它是一个有效的 IPv6 地址，所以我们将以点状字符串的形式得到结果。

```sql
SELECT INET6_NTOA(UNHEX('FCBE0000000000005C34CABDFEFA6312')) 
AS Address_In_DottedString ;
```

**输出:**

<figure class="table">

| 地址 _ 输入 _ 打点字符串 |
| --- |
| fcbe::5c 34:cabd:fefa:6312 |

</figure>

**示例-3 :**

借助 INET6_NTOA 和 UNHEX 函数，检查以下地址“456A”的等效点四字符串表示。由于它不是有效的 IPv6 或 IPv4 地址，我们将得到一个空结果。

```sql
SELECT INET6_NTOA(UNHEX('456A')) 
AS Address_In_DottedString ;
```

**输出:**

<figure class="table">null

| 【地址 _ in _ 虚线字符串】 |
| --- |

</figure>

**示例-4 :**

借助 INET6_NTOA 和 inet 6 _ 艾顿函数，检查以下地址“9.7.5.8”的等效四点字符串表示形式。由于它不是有效的 IPv6 或 IPv4 地址，我们将以点状字符串的形式获得结果。

```sql
SELECT INET6_NTOA(INET6_ATON('9.7.5.8')) 
AS Address_In_DottedString ;
```

**输出:**

<figure class="table">

| 地址 _ 输入 _ 打点字符串 |
| --- |
| 9.7.5.8 |

</figure>