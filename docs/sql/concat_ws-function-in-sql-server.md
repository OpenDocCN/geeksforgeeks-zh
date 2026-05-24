# SQL Server 中的 CONCAT_WS()函数

> 原文:[https://www . geesforgeks . org/concat _ ws-function-in-SQL-server/](https://www.geeksforgeeks.org/concat_ws-function-in-sql-server/)

**CONCAT_WS() :**
这个函数用一个分隔符将两个或多个字符串连接在一起。

**语法:**

```sql
CONCAT_WS(separator, input_string1, input_string2, [...input_stringN]);

```

**参数:**
该方法接受如上所述的双参数，描述如下。

*   **分隔符–**
    它是任何字符类型的表达式，如 char、nchar、nvarchar 或 varchar。
*   **input _ string–**
    它是任何类型的表达式。要加在一起的 input_strings。

**返回:**
返回一个串联的字符串值。

**示例-1 :**
使用“–”分隔串联的字符串值。

```sql
SELECT CONCAT_WS(' - ', 'GeeksforGeeks', 'computer', 'science', 'portal');

```

**输出:**

```sql
GeeksforGeeks - computer - science - portal

```

**示例-2 :**
使用“”分隔串联的字符串值。

```sql
SELECT CONCAT_WS(' ', 'Hardik', 'Pandya') Your_Name;

```

**输出:**

| 您的 _ 姓名 |
| 哈迪克·潘迪亚 |

**示例-3 :**
使用带有空值的 CONCAT_WS()。

```sql
SELECT CONCAT_WS(', ','DN Block', 'Bidhannagar', 
                      NULL, 'Kolkata', NULL, 700091) 
AS Your_Address;

```

**输出:**

| 您的 _ 地址 |
| DN Block，bidhannagar，加尔各答，7000091 |

**示例-4 :**
使用带有表列的 CONCAT_WS()。
**表-玩家 _ 详情–**

| 球员 | 玩家名 | 绰号 |
| Forty-five | 罗希特·夏尔马 | 职业杀手 |
| Eighteen | 维拉·科尔 | Chiku |
| seven | 迪奥尼女士 | 最高有效位(most significant digit) |

```sql
SELECT 
    PLAYERNAME, 
    NICKNAME, 
    CONCAT_WS(' - ', PLAYERNAME, NICKNAME) Name_with_NickName
FROM 
    Player_Details

```

**输出:**

| 玩家名 | 绰号 | 带 _ 昵称的名称 |
| 罗希特·夏尔马 | 职业杀手 | 罗希特·夏尔马——杀手 |
| 维拉·科尔 | Chiku | virat kohli–chiku |
| 迪奥尼女士 | 最高有效位(most significant digit) | 多尼女士-MSD |