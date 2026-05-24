# MySQL 中的 OCT()函数

> 原文:[https://www.geeksforgeeks.org/oct-function-in-mysql/](https://www.geeksforgeeks.org/oct-function-in-mysql/)

**使用 MySQL 中的 OCT()** 函数将十进制数转换为八进制数。它返回十进制数的等效八进制值。

**语法:**

```sql
OCT(number)

```

**参数:**此方法只接受一个参数。

*   **数字:**我们要转换的十进制数。

**返回:**返回十进制数的八进制值。

**示例-1 :**
使用 OCT 函数对十进制数 0 进行八进制表示。

```sql
SELECT OCT(0) AS Oct_number ;

```

**输出:**

| 十月号 |
| --- |
| Zero |

**示例-2 :**
使用 OCT 函数对十进制数 2020 进行八进制表示。

```sql
SELECT OCT( 2020 ) AS Oct_number ;

```

**输出:**

| 十月号 |
| --- |
| Three thousand seven hundred and forty-four |

**示例-3 :**
使用 OCT 函数查找列中所有十进制数的八进制表示。为了演示，让我们创建一个名为 Player 的表。

```sql
CREATE TABLE Player(

Player_id INT AUTO_INCREMENT,  
Player_name VARCHAR(100) NOT NULL,
Playing_team VARCHAR(20) NOT NULL,
Run_Scored INT NOT NULL,
PRIMARY KEY(Player_id )

);

```

现在，向玩家表中插入一些数据–

```sql
INSERT INTO  
Player(Player_name, Playing_team, Run_Scored)
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

因此，玩家表是–

```sql
SELECT * FROM Player;

```

| 玩家 id | 玩家名称 | 正在玩团队游戏 | 运行得分 |
| --- | --- | --- | --- |
| one | 维拉·科尔 | 零售信贷局(Retail Credit Bureau) | Sixty |
| Two | 罗希特·夏尔马 | 大调音阶的第三音 | Forty-five |
| three | Dinesh Karthik | KKR | Twenty-six |
| four | Shreyash Iyer | 直流电 | Forty |
| five | 大卫·华纳 | SRH | Sixty-five |
| six | 史蒂夫·史密斯 | 乡邮投递路线 | fifty-two |
| seven | 安德烈·拉塞尔 | KKR | Seventy |
| eight | 贾斯帕·邦拉 | 大调音阶的第三音 | Ten |
| nine | 理纱波提 | 直流电 | Thirty-four |

现在，我们将使用华侨城函数找到每个玩家在八进制数中的得分。

```sql
SELECT  
Player_id, Player_name,
Playing_team, OCT(Run_Scored) AS RunInOctal
FROM Player ;

```

**输出:**

| 玩家 id | 玩家名称 | 正在玩团队游戏 | RunInOctal |
| --- | --- | --- | --- |
| one | 维拉·科尔 | 零售信贷局(Retail Credit Bureau) | Seventy-four |
| Two | 罗希特·夏尔马 | 大调音阶的第三音 | Fifty-five |
| three | Dinesh Karthik | KKR | Thirty-two |
| four | Shreyash Iyer | 直流电 | Fifty |
| five | 大卫·华纳 | SRH | One hundred and one |
| six | 史蒂夫·史密斯 | 乡邮投递路线 | Sixty-four |
| seven | 安德烈·拉塞尔 | KKR | One hundred and six |
| eight | 贾斯帕·邦拉 | 大调音阶的第三音 | Twelve |
| nine | 理纱波提 | 直流电 | forty-two |