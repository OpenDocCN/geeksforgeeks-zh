# SQL Server 中的 ASCII()函数

> 原文:[https://www.geeksforgeeks.org/ascii-function-in-sql-server/](https://www.geeksforgeeks.org/ascii-function-in-sql-server/)

**ASCII()** 函数返回字符表达式最左边字符的 ASCII 值。

**语法:**

```sql
ASCII(character_expression)
```

**参数:**
该方法接受如上所述的单参数，如下所述:
**character _ expression:**
可以是文字字符、字符串表达式或列。如果输入了多个字符，它将只返回最左边字符的值。
**返回:**
返回其最左边字符的 ASCII 码值。

**示例-1 :**
当参数包含单个大写和小写字母时。

```sql
SELECT ASCII('A') AS A, ASCII('a') AS a,
ASCII('Z') AS Z, ASCII('z') AS z;
```

**输出:**

| A | a | Z | z |
| Sixty-five | Ninety-seven | Ninety | One hundred and twenty-two |

**例-2 :**
当自变量为单个数字和特殊字符时。

```sql
SELECT ASCII('1') AS [1], ASCII('#') AS #,
ASCII(9) AS [9], ASCII('@') AS [@]; 
```

**输出:**

| one | # | nine | @ |
| forty-nine | Thirty-five | Fifty-seven | Sixty-four |

**例-3 :**
当自变量持有一个字符串的表达式时。

```sql
SELECT ASCII('GeeksForGeeks');
```

**输出:**

```sql
71
```

**例-4 :**
使用 ASCII()函数用表列。
**表–玩家 _ 详情**

| 球员 | 玩家名称 | 城市 |
| Forty-five | 罗希特·夏尔马 | 孟买 |
| Eighteen | 维拉·科尔 | 班加罗尔 |
| seven | 迪奥尼女士 | 金奈 |
| Thirty-three | 哈迪克·潘迪亚 | 孟买 |
| forty-two | 锡卡扎万 | 德里 |

```sql
SELECT PlayerName, ASCII(PlayerName) AS AsciiCodeOfFirstChar
FROM Player_Details;
```

**输出:**

| 玩家名称 | AsciiCodeOfFirstChar |
| 罗希特·夏尔马 | Eighty-two |
| 维拉·科尔 | Eighty-six |
| 迪奥尼女士 | Seventy-seven |
| 哈迪克·潘迪亚 | seventy-two |
| 锡卡扎万 | Eighty-three |