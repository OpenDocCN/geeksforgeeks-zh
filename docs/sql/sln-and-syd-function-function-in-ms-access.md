# MS 接入中的 SLN()和 SYD()功能功能

> 原文:[https://www . geesforgeks . org/SLN-and-syd-function-in-function-ms-access/](https://www.geeksforgeeks.org/sln-and-syd-function-function-in-ms-access/)

**1。SLN()函数:**
MS Access 中的 SLN()函数用于计算资产在单个期间的直线折旧。

**语法:**

```sql
SLN(cost, salvage, life)
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **成本**:指定资产的初始成本。
*   **残值**:规定资产使用寿命结束时的价值。
*   **寿命**:规定资产使用寿命的长度。

**返回:**返回资产的折旧。

**注:**折旧年限必须用与年限自变量相同的单位表示。所有参数必须是正数。

**例-1 :**
考虑到资产的使用寿命为 10 年，残值为 15%的资产折旧。

```sql
SELECT SLN(1500.0, 1500.0*0.15, 10) AS Amount;
```

**输出:**

| 数量 |
| --- |
| One hundred and twenty-seven point five |

**例-2 :**
考虑到使用寿命为 15 年，残值率为 10%的资产的折旧。

**表–**账户

| AccountId | 贷款额 |
| --- | --- |
| Eleven thousand and one | Fifteen thousand |
| Eleven thousand and two | Twelve thousand |
| Eleven thousand and three | Ten thousand |

```sql
SELECT SLN([LoanAmount], [LoanAmount]*.1, 15) AS Amt 
FROM Accounts;
```

**输出:**

| 手自一体 |
| --- |
| Nine hundred |
| Seven hundred |
| Six hundred |

**2。SYD()函数:**
MS Access 中的 SYD()函数用于计算某一资产在指定期间的年位数折旧之和。

**语法:**

```sql
SYD(cost, salvage, life, period)
```

**参数**:该方法接受上述四个参数，描述如下:

*   **成本**:指定资产的初始成本。
*   **残值**:规定资产使用寿命结束时的价值。
*   **寿命**:规定资产使用寿命的长度。
*   **期间**:指定计算资产折旧的期间。

**返回:**返回指定期间资产的折旧。

**注:**寿命和周期参数必须用相同的单位表示。例如，如果生命以月为单位，那么周期也必须以月为单位。所有参数必须是正数。

**例-1 :**
考虑到资产的使用寿命为 10 年，残值为 15%的资产折旧。计算第三年的折旧。

```sql
SELECT SYD(1500.0, 1500.0*0.15, 10, 3) AS Amount;
```

**输出:**

| 数量 |
| --- |
| 185.454545454545 |

**例-2 :**
考虑到使用寿命为 15 年，残值率为 10%的资产的折旧。计算第二年的折旧。

**表–**账户

| AccountId | 贷款额 |
| --- | --- |
| One hundred and one | Fifteen thousand |
| One hundred and two | Twelve thousand |
| One hundred and three | Ten thousand |

```sql
SELECT SYD([LoanAmount], [LoanAmount]*.10, 15, 2) AS Amt 
FROM Accounts;
```

**输出**:

| 手自一体 |
| --- |
| One thousand five hundred and seventy-five |
| One thousand two hundred and sixty |
| One thousand and fifty |