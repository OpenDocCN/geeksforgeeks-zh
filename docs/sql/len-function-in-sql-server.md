# SQL Server 中的 LEN()函数

> 原文:[https://www.geeksforgeeks.org/len-function-in-sql-server/](https://www.geeksforgeeks.org/len-function-in-sql-server/)

**LEN()** 函数计算输入字符串的字符数，不包括尾随空格。

**语法:**

```sql
LEN(input_string)
```

**参数–**
该方法接受如上所述的单参数，描述如下:

**input _ string–**
它是一个表达式，可以是常量、变量或字符或二进制数据列。

**返回:**

它返回输入字符串的字符数，不包括尾随空格。

**示例-1:** 返回字符串的长度

```sql
SELECT LEN('Geeksforgeeks');
```

**输出:**

```sql
13
```

**示例-2:** 检查 LEN()函数是否计算尾随空格

```sql
SELECT LEN('GFG       ') 
As Length_with_trailing_spaces;
```

**输出:**

| **长度 _ 带 _ 尾随 _ 空格** |
| three |

**示例-3:** 检查 LEN()函数是否计算前导空格

```sql
SELECT LEN('       GFG') 
As Length_with_leading_spaces;
```

**输出:**

| **长度 _ 带 _ 前导 _ 空格** |
|   10 |

**示例-4:** 使用带列的 LEN()函数

**表-玩家 _ 详情**

| **PlayerId** | **玩家姓名** | >**城市** |
| Forty-five | 罗希特·夏尔马 | 孟买 |
| Eighteen | 维拉·科尔 | 孟加拉鲁 |
| seven | M S Dhoni | 金奈 |

```sql
SELECT
    PlayerName,
    LEN(PlayerName) PlayerName_Length
FROM
    Player_Details
```

**输出:**

| **玩家姓名** | **PlayerName_Length** |
| 罗希特·夏尔马 | Twelve |
| 维拉·科尔 | Eleven |
| 迪奥尼女士 | eight |