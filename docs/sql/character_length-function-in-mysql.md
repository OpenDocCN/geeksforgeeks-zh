# MySQL 中的 CHARACTER_LENGTH()函数

> 原文:[https://www . geesforgeks . org/character _ length-function-in-MySQL/](https://www.geeksforgeeks.org/character_length-function-in-mysql/)

**CHARACTER_LENGTH() :**
这个函数在 MySQL 中帮助找到给定字符串的长度。长度是以字符的形式来衡量的。而且，CHARACTER_LENGTH()也是 [CHAR_LENGTH()函数](https://www.geeksforgeeks.org/char_length-function-in-mysql/)的同义词。

**语法:**

```sql
CHARACTER_LENGTH(string)
```

**参数:**
该函数只接受一个参数，如下所示。

*   **弦–**
    长度待定的弦。

**返回:**
返回给定字符串的长度。

**示例-1 :**
使用 CHARACTER_LENGTH()函数计算给定字符串的长度，如下所示。

```sql
SELECT CHARACTER_LENGTH("GeeksforGeeks") AS LenOfStr
```

**输出:**

| LenOfStr |
| Thirteen |

**示例-2 :**
使用 CHARACTER_LENGTH()函数计算给定字符串的长度，如下所示。

```sql
SELECT CHARACTER_LENGTH("//  GeeksforGeeks  //") 
AS LenOfStr
```

**输出:**

| LenOfStr |
| Twenty-one |

**示例-3 :**
使用 CHARACTER_LENGTH()函数计算给定表中每一列的长度，如下所示。
**表-板球运动员 _ 详情:**

| 玩家标识 | 玩家名称 | 运行得分 |
| Eleven | 尤瓦拉杰·辛格 | One hundred and forty-four thousand |
| Forty-one | Dinesh Kartik | One hundred thousand |
| 05 | 维拉·科尔 | Five hundred thousand |
| Ninety-nine | 克里斯·盖尔 | Four hundred and ten thousand |
| 07 | 米（meter 的缩写））S Dhoni | Seven hundred thousand |

现在，使用下面给出的命令来计算字符长度。

```sql
SELECT CHARACTER_LENGTH(PLAYER_NAME) AS LenOfCol  
FROM Cricketers_details;
```

**输出:**

| LenOfCol |
| Twelve

 |
| Thirteen |
| Eleven |
| Ten |
| nine |

**示例-4 :**
使用 CHARACTER_LENGTH()函数计算给定字符串的长度，如下所示。

```sql
SELECT CHARACTER_LENGTH("//  @#$#@  //") 
AS LenOfStr
```

**输出:**

| LenOfStr |
| Fourteen |