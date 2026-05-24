# MySQL 中 INET_NTOA()函数

> 原文:[https://www.geeksforgeeks.org/inet_ntoa-function-in-mysql/](https://www.geeksforgeeks.org/inet_ntoa-function-in-mysql/)

inet _ ntoa():

MySQL 中的这个函数按照网络字节顺序获取 IPv4 地址，然后以点状四元字符串的形式返回该地址。如果输入地址是无效的 IPv4 地址，此函数返回空值。

**语法:**

```sql
INET_NTOA(expr)
```

**参数:**该函数只接受一个参数。

*   **expr–**
    输入以网络字节顺序表示的 IPv4 地址。

**返回:**

它返回给定 IPv4 地址的四点字符串表示形式。

**示例-1 :**

借助 INET_NTOA 函数，检查以下地址“17171712”的等效点四字符串表示形式。由于这是一个有效的 IPv4 地址，我们将得到一个点串的结果。

```sql
SELECT INET_NTOA(17171712)  
AS Address_In_DottedString ;
```

**输出:**

<figure class="table">

| 地址 _ 输入 _ 打点字符串 |
| --- |
| 1 . 6 . 5 . 0 |

</figure>

**示例-2 :**

借助 INET_NTOA 函数检查以下地址“-121”的等效点四字符串表示形式。由于它不是有效的 IPv4 地址，我们将得到空值。

```sql
SELECT INET_NTOA(-121)  
AS Address_In_DottedString ;
```

**输出:**

<figure class="table">null

| 【地址 _ in _ 虚线字符串】 |
| --- |

</figure>

**示例-3 :**

借助 INET_NTOA 函数检查以下十进制数字“171712.01223”的等效点四字符串表示形式。

```sql
SELECT INET_NTOA (171712.01223)  
AS Address_In_DottedString ;
```

**输出:**

<figure class="table">

| 地址 _ 输入 _ 打点字符串 |
| --- |
| 0 . 2 . 158 . 192 |

</figure>

**示例-4 :**

借助 INET_NTOA 函数，检查以下二进制数“101011001”的等效点四字符串表示形式。

```sql
SELECT INET_NTOA(b'101011001')  
AS Address_In_DottedString ;
```

**输出:**

<figure class="table">

| 地址 _ 输入 _ 打点字符串 |
| --- |
| 0 . 0 . 1 . 89 |

</figure>