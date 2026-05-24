# MySQL 中的 INET6_ATON()函数

> 原文:[https://www.geeksforgeeks.org/inet6_aton-function-in-mysql/](https://www.geeksforgeeks.org/inet6_aton-function-in-mysql/)

MySQL 中的这个[函数采用 IPv4 或 IPv6 地址的点状表示，并返回一个二进制字符串，该字符串以网络字节顺序表示地址的数值。如果输入地址不是有效的 IPv4 或 IPv6 地址，此函数返回空值。](https://www.geeksforgeeks.org/mysql-creating-stored-function/#:~:text=The%20CREATE%20FUNCTION%20statement%20is,from%20within%20a%20Mysql%20statement.)

**语法:**

```sql
INET6_ATON(expr)
```

**参数:**
此方法只接受一个参数。

*   **expr–**
    输入用字符串表示的 IPv4 或 IPv6 地址。

**返回:**
返回 VARBINARY 数据类型中地址的数值:IPv6 地址为 VARBINARY(16)，IPv4 地址为 VARBINARY(4)。

**示例-1 :**
借助 INET6_ATON 函数，检查以下地址‘10 . 16 . 25 . 0’的等价 VARBINARY 表示。由于这是一个有效的 IPv4 地址，我们将得到 VARBINARY 形式的结果。

```sql
SELECT INET6_ATON('10.16.25.0')  
AS EquivalentAddressValue ;
```

**输出:**

| EQUIVALENTADDRESSVALUE |
| --- |
| 0x0A101900 |

**示例-2 :**
在 INET6_ATON 函数的帮助下，检查以下地址的等效 VARBINARY 表示“2001:0db 8:85 a3:0000:0000:8a2e:0370:7334”。因为它是一个有效的 IPv6 地址，所以我们会得到一个 VARBINARY 形式的结果。

```sql
SELECT INET6_ATON('2001:0db8:85a3:0000:0000:8a2e:0370:7334')  
AS EquivalentAddressValue ;
```

**输出:**

| EQUIVALENTADDRESSVALUE |
| --- |
| 0x 20010 db 885 a 3000000008 a2 e 0370734 |

**示例-3 :**
借助 INET6_ATON 函数检查以下地址的等价 VARBINARY 表示:::0.5’。由于它不是有效的 IPv4 或 IPv6 地址，我们将得到空值。

```sql
SELECT INET6_ATON('::0.5')  
AS EquivalentAddressValue ;
```

**输出:**

| EQUIVALENTADDRESSVALUE |
| --- |
| 0x |