# MySQL 中的 IS_IPV4_MAPPED()函数

> 原文:[https://www . geesforgeks . org/is _ IP v4 _ mapped-function-in-MySQL/](https://www.geeksforgeeks.org/is_ipv4_mapped-function-in-mysql/)

**IS_IPV4_MAPPED() :**

MySQL 中的这个函数将 IPv6 地址以数字形式表示为二进制字符串，由 INET6_ATON 函数返回。如果参数是有效的 IPv4 映射的 IPv6 地址，则返回 1，否则返回 0。IPv4 映射地址的一般形式是**:ffff:IP v4 _ address。**

**语法:**

```sql
IS_IPV4_MAPPED(expr)
```

**参数:**

这个函数接受一个参数。

*   **expr–** Enter the IPv6 address represented by a string.

**返回:**

*   Returns 1 if the string is a valid IPv6 address for IPv4 mapping.
*   If the string is not a valid IPv4 mapped IPv6 address, it will return 0.

**示例-1 :**

使用 IS_IPV4_MAPPED 函数检查给定地址“:12.10.15.8”是否有效。由于给定的输入不是有效的 IPv4 映射地址，它将返回 0。

```sql
SELECT IS_IPV4_MAPPED(INET6_ATON('::12.10.15.8')) AS IS_IPV4_MAPPED ;
```

**输出:**

<figure class="table">T5】

| IS _ IP v4 _ MAPPED |
| --- |
| 0 |

</figure>

**示例-2 :**

使用 IS_IPV4_MAPPED 函数检查给定地址“::ffff:8.7.12.3”是否有效。由于这里给定的输入是有效的 IPv4 映射地址，它将返回 1。

```sql
 SELECT IS_IPV4_MAPPED(INET6_ATON('::ffff:8.7.12.3')) AS IS_IPV4_MAPPED;
```

**输出:**

<figure class="table">T5】

| IS _ IP v4 _ MAPPED |
| --- |
| 1 |

</figure>

**示例-3 :**

使用 IS_IPV4_MAPPED 函数检查给定地址“ff::9.6.10.11”是否有效。由于给定的输入不是有效的 IPv4 映射地址，它将返回 0。

```sql
SELECT IS_IPV4_MAPPED(INET6_ATON('ff::9.6.10.11')) AS IS_IPV4_MAPPED ;
```

**输出:**

<figure class="table">T5】

| IS _ IP v4 _ MAPPED |
| --- |
| 0 |

</figure>

**示例-4 :**

使用 IS_IPV4_MAPPED 函数

```sql
SELECT IS_IPV4_MAPPED(INET6_ATON('::1')) AS IS_IPV4_MAPPED;
```

检查给定的 IPv6 地址“::1”是否有效

**输出:**

<figure class="table">T5】

| IS _ IP v4 _ MAPPED |
| --- |
| 0 |

</figure>