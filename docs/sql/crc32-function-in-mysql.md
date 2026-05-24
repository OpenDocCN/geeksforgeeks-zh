# MySQL 中的 CRC32()函数

> 原文:[https://www.geeksforgeeks.org/crc32-function-in-mysql/](https://www.geeksforgeeks.org/crc32-function-in-mysql/)

MySQL 中的 CRC32() [函数用于计算循环冗余值。如果参数为空，则返回空值；否则，在计算冗余后，返回 32 位无符号值。](https://www.geeksforgeeks.org/sql-functions-aggregate-scalar-functions/)

**语法:**

```sql
CRC32(expr)

```

**参数:**
此方法只接受一个参数。

*   **expr–**是要检索其 CRC32 值的字符串。

**返回:**
返回循环冗余值。

**示例-1 :**
使用 CRC32 函数查找字符串的循环冗余值。

```sql
SELECT CRC32('geeksforgeeks') 
AS CRC_Value;

```

**输出:**

| 循环冗余校验值 |
| --- |
| One hundred and fourteen million seventy-nine thousand one hundred and seventy-four |

**示例-2 :**
使用 CRC32 函数查找数字的循环冗余值。

```sql
SELECT CRC32( 2020 ) 
AS CRC_Value;

```

**输出:**

| 循环冗余校验值 |
| --- |
| Two billion four hundred and ninety-three million eight hundred and four thousand one hundred and fifty-five |

**示例-3 :**
使用 CRC32 函数为空参数查找循环冗余值。

```sql
SELECT CRC32(NULL) 
AS CRC_Value;

```

**输出:**

| 循环冗余校验值 |
| --- |
| 空 |

**示例-4 :**
使用 CRC32 函数查找列数据的循环冗余值。为了演示，让我们创建一个名为 Player 的表。

```sql
CREATE TABLE Player
(
Player_id INT AUTO_INCREMENT,  
Player_name VARCHAR(100) NOT NULL,
Playing_team VARCHAR(20) NOT NULL,
PRIMARY KEY(Player_id )
);

```

现在，向播放器表中插入一些数据。

```sql
INSERT INTO  
Player(Player_name, Playing_team)
VALUES
('Virat Kohli', 'RCB' ),
('Rohit Sharma', 'MI' ),
('Dinesh Karthik', 'KKR'  ),
('Shreyash Iyer', 'DC'  ),
('David Warner', 'SRH' ),
('Steve Smith', 'RR'  ),
('Andre Russell', 'KKR' ),
('Jasprit Bumrah', 'MI' ),
('Risabh Panth', 'DC'  ) ;

```

所以，玩家表如下。

```sql
SELECT * FROM Player;

```

**输出:**

| 玩家 id | 玩家名称 | 正在玩团队游戏 |
| --- | --- | --- |
| one | 维拉·科尔 | 零售信贷局(Retail Credit Bureau) |
| Two | 罗希特·夏尔马 | 大调音阶的第三音 |
| three | Dinesh Karthik | KKR |
| four | Shreyash Iyer | 直流电 |
| five | 大卫·华纳 | SRH |
| six | 史蒂夫·史密斯 | 乡邮投递路线 |
| seven | 安德烈·拉塞尔 | KKR |
| eight | 贾斯帕·邦拉 | 大调音阶的第三音 |
| nine | 理纱波提 | 直流电 |

现在，我们将使用 CRC32 函数为 Player_name 和 Playing_team 列找到循环冗余值。

```sql
SELECT 
*, CRC32(Player_name),
CRC32(Playing_team)
FROM Player;

```

**输出:**

| 玩家 id | 玩家名称 | 正在玩团队游戏 | CRC32(玩家名称) | CRC32(游戏 _ 团队) |
| --- | --- | --- | --- | --- |
| one | 维拉·科尔 | 零售信贷局(Retail Credit Bureau) |  4234533515 | Three billion five hundred and fifty-six million seven hundred and twelve thousand three hundred and seventy-four |
| Two | 罗希特·夏尔马 | 大调音阶的第三音 |  2696911654 | One hundred and eighty-five million five hundred and twenty-two thousand eight hundred and nineteen |
| three | Dinesh Karthik | KKR | Seven hundred and three million three hundred and seven thousand eight hundred and thirty-two | Three hundred and fifty-nine million thirteen thousand six hundred and sixty-nine |
| four | Shreyash Iyer | 直流电 | Two billion eight hundred and seventeen million five hundred and forty-five thousand five hundred and ninety-three | Nine hundred and seventy-four million seven hundred and fifty-one thousand nine hundred and fifty-six |
| five | 大卫·华纳 | SRH | Three billion six hundred and forty-five million two hundred and fifty-six thousand and eighty-eight | One billion six hundred and thirty million six hundred and fifty thousand two hundred and fifty-five |
| six | 史蒂夫·史密斯 | 乡邮投递路线 | Seven hundred and seventy-seven million two hundred and two thousand two hundred and fifty-seven | One billion two hundred and seventy-eight million two hundred and eighty-seven thousand three hundred and forty-five |
| seven | 安德烈·拉塞尔 | KKR | Three billion ninety million three hundred and six thousand six hundred and ninety-eight | Three hundred and fifty-nine million thirteen thousand six hundred and sixty-nine |
| eight | 贾斯帕·邦拉 | 大调音阶的第三音 | One hundred and ninety-one million four hundred and sixty-one thousand and seventeen | One hundred and eighty-five million five hundred and twenty-two thousand eight hundred and nineteen |
| nine | 理纱波提 | 直流电 | One hundred and seventy-eight million nine hundred and ninety-eight thousand six hundred and eight | Nine hundred and seventy-four million seven hundred and fifty-one thousand nine hundred and fifty-six |