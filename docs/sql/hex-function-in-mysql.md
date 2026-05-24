# MySQL 中的 HEX()函数

> 原文:[https://www.geeksforgeeks.org/hex-function-in-mysql/](https://www.geeksforgeeks.org/hex-function-in-mysql/)

**HEX() :**

MySQL 中的这个函数用于返回字符串或数字输入的等效十六进制字符串值。如果输入是一个字符串，那么字符串中每个字符的每个字节都被转换为两个十六进制数字。该函数还返回数字参数 N 的十六进制字符串表示形式，被视为 longlong (BIGINT)数字。

**语法:**

```sql
HEX(string)
OR
HEX(N)
```

**参数:**

此方法只接受一个参数。

*   **String–** Each character in the input string will be converted into two hexadecimal digits.
*   **n–** Enter the number to be converted into hexadecimal.

**返回:**

它返回字符串或数字输入的等效十六进制字符串表示形式。

**示例-1 :**

使用十六进制函数对十进制数 0 进行十六进制表示，如下所示。

```sql
SELECT HEX(0) AS Hex_number ;
```

**输出:**

<figure class="table">T5】

| HEX _ NUMBER |
| --- |
| 0 |

</figure>

**示例-2 :**

使用十六进制函数对十进制数 2020 进行十六进制表示，如下所示。

```sql
SELECT HEX( 2020 ) AS Hex_number ;
```

**输出:**

<figure class="table">T5】

| HEX _ NUMBER |
| --- |
| 7e 4 |

</figure>

**示例-3 :**

使用十六进制函数的字符串“geeksforgeeks”的十六进制表示如下。

```sql
SELECT HEX( 'geeksforgeeks') AS Hex_string ;
```

**输出:**

<figure class="table">

| 十六进制字符串 |
| --- |
| 676566 b 73666 f 72676566 b 73 |

T17】</figure>

**示例-4 :**

使用十六进制函数查找列中所有十进制数字的十六进制表示，如下所示。

**创建玩家表:**

```sql
CREATE TABLE Player(

Player_id INT AUTO_INCREMENT,  
Player_name VARCHAR(100) NOT NULL,
Playing_team VARCHAR(20) NOT NULL,
Highest_Run_Scored INT NOT NULL,
PRIMARY KEY(Player_id )

);
```

**将数据插入表格:**

```sql
INSERT INTO  
Player(Player_name, Playing_team, Highest_Run_Scored)
VALUES
('Virat Kohli', 'RCB', 60 ),
('Rohit Sharma', 'MI', 45),
('Dinesh Karthik', 'KKR', 26 ),
('Shreyash Iyer', 'DC', 40 ),
('David Warner', 'SRH', 65),
('Steve Smith', 'RR', 52 ),
('Andre Russell', 'KKR', 70),
('Jasprit Bumrah', 'MI', 10),
('Risabh Panth', 'DC', 34 ) ;
```

使用如下命令进行验证。

```sql
SELECT * FROM Player;
```

**输出:**

<figure class="table">T19】RCBT21】60T24T27】罗希特沙尔马 T57】大卫·华纳 T59】SRHT61】65T63T65】6T67】史蒂夫·史密斯 T69】RRT71】52T73T75】7T77】安德烈·罗素 T79】KKRT81

| 玩家标识 | 玩家名称 | 正在播放 _ TEAM | most _ RUN _ SCORED |
| --- | --- | --- | --- |
| one | 维拉·科尔 |
| Two | MI 【T30 | five |

</figure>

现在，我们将使用十六进制函数找到每个玩家的最高得分。

```sql
SELECT  
Player_id, Player_name,
Playing_team, HEX(HIGHEST_RUN_SCORED) AS HighestRunInHexaDecimal
FROM Player ;
```

**输出:**

<figure class="table">

| 【玩家 _ id】 | 【玩家 _ 姓名】 | 【玩法 _ 团队】 |  | "Extremely high hexadecimal" |  | [David Warner] | 【srh】 |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
|  | Steve Smith |
| --- | --- |

</figure>