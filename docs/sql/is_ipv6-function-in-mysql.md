# MySQL 中的 IS_IPV6()函数

> 原文:[https://www.geeksforgeeks.org/is_ipv6-function-in-mysql/](https://www.geeksforgeeks.org/is_ipv6-function-in-mysql/)

**IS _ IPV6():**
MySQL 中的这个函数用来检查指定的字符串是否是有效的 IPV6 地址。如果它是有效的 IPv6 地址，那么它将返回 1。否则，它将返回 0。

**语法:**

```sql
IS_IPV6(expr)
```

**参数:**
此方法只接受一个参数。

*   **expr–**输入我们要检查的字符串。

**返回:**
如果字符串是有效的 IPv6 地址，则返回 1。如果该字符串不是有效的 IPv6 地址，则它将返回 0。

**示例-1 :**
使用 IS_IPV6 函数检查给定地址是否有效。

```sql
SELECT IS_IPV6('10.4.2.256') 
AS ValidOrNot;
```

**输出:**

| 有效与否 |
| --- |
| Zero |

因此，我们可以看到给定的地址不是有效的 IPv6 地址。
**示例-2 :**
使用 IS_IPV6 函数检查给定地址是否有效。

```sql
SELECT IS_IPV6('::2') 
AS ValidOrNot;
```

**输出:**

| 有效与否 |
| --- |
| one |

因此，我们可以看到给定的地址是有效的 IPv6 地址。

**示例-3 :**
使用 IS_IPV6 功能检查 IPv4 地址是否为有效的 IPv6 地址。

```sql
SELECT IS_IPV6('2001:0db8:85a3:0000:0000:8a2e:0370:7334')  
IPv6ValidOrNot,
IS_IPV4('2001:0db8:85a3:0000:0000:8a2e:0370:7334') 
AS IPv4ValidOrNot;
```

**输出:**

| IPV6VALIDORNOT | IP v4 valid ot |
| --- | --- |
| one | Zero |