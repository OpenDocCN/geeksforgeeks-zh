# SQL Server 中的 `CONCAT_WS()` 函数

> 原文: [https://www.geeksforgeeks.org/concat_ws-function-in-sql-server/](https://www.geeksforgeeks.org/concat_ws-function-in-sql-server/)

**`CONCAT_WS()` :**
这个函数用一个分隔符将两个或多个字符串连接在一起。

**语法:**

```sql
CONCAT_WS(separator, input_string1, input_string2, [...input_stringN]);
```

**参数:**
该方法接受如上所述的参数，描述如下。

*   **`separator` –**
    它是任何字符类型的表达式，如 `char`、`nchar`、`nvarchar` 或 `varchar`。
*   **`input_string` –**
    它是任何类型的表达式。要加在一起的 `input_strings`。

**返回:**
返回一个串联的字符串值。

**示例-1 :**
使用 `' - '` 分隔串联的字符串值。

```sql
SELECT CONCAT_WS(' - ', 'GeeksforGeeks', 'computer', 'science', 'portal');
```

**输出:**

```sql
GeeksforGeeks - computer - science - portal
```

**示例-2 :**
使用 `' '` 分隔串联的字符串值。

```sql
SELECT CONCAT_WS(' ', 'Hardik', 'Pandya') Your_Name;
```

**输出:**

| Your_Name |
| Hardik Pandya |

**示例-3 :**
使用带有空值的 `CONCAT_WS()`。

```sql
SELECT CONCAT_WS(', ','DN Block', 'Bidhannagar', 
                      NULL, 'Kolkata', NULL, 700091) 
AS Your_Address;
```

**输出:**

| Your_Address |
| DN Block, Bidhannagar, Kolkata, 700091 |

**示例-4 :**
使用带有表列的 `CONCAT_WS()`。

**表-`Player_Details` –**

| Player | PlayerName | Nickname |
| 45 | Rohit Sharma | Hitman |
| 18 | Virat Kohli | Chiku |
| 7 | Dhoni | MSD |

```sql
SELECT 
    PLAYERNAME, 
    NICKNAME, 
    CONCAT_WS(' - ', PLAYERNAME, NICKNAME) Name_with_NickName
FROM 
    Player_Details;
```

**输出:**

| PlayerName | Nickname | Name_with_NickName |
| Rohit Sharma | Hitman | Rohit Sharma - Hitman |
| Virat Kohli | Chiku | Virat Kohli - Chiku |
| Dhoni | MSD | Dhoni - MSD |