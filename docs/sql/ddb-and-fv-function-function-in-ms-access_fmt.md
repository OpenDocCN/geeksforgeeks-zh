# MS Access中的DDB()和FV()函数

> 原文: [https://www.geeksforgeks.org/ddb-and-fv-function-function-in-ms-access/](https://www.geeksforgeks.org/ddb-and-fv-function-function-in-ms-access/)

## 1. DDB()函数
MS Access中的`DDB()`函数用于使用双倍余额递减法或其他方法计算特定时间段内资产的折旧。`DDB`函数使用以下公式计算给定期间的折旧：

```sql
Depreciation / period = ((cost – salvage) * factor) / life
```

**语法：**

```sql
DDB(cost, salvage, life, period, [factor])
```

**参数：** 该方法接受五个参数，如上所述，如下所述：

*   `cost`：指定资产的初始成本。
*   `salvage`：规定资产使用寿命结束时的价值。
*   `life`：规定资产使用寿命的长度。
*   `period`：指定计算资产折旧的期间。
*   `factor`：指定余额下降的速率。如果省略，则假设为2（双倍递减法）。

**返回：** 返回特定时间段内资产的折旧。

**注：** 折旧年限必须用与`life`自变量相同的单位表示。所有参数必须是正数。

**例-1：**
考虑到资产的使用寿命为10年，残值率为15%的资产折旧按第2年计算。

```sql
SELECT DDB(1500.0, 1500.0*0.15, 10, 2) AS Amount;
```

**输出：**

| Amount |
| --- |
| Two hundred and forty |

**例-2：**
考虑到使用寿命为15年，残值为10%的资产的折旧表，计算第3年的折旧。

**表–** `Accounts`

| AccountId | LoanAmount |
| --- | --- |
| Eleven thousand and one | Fifteen thousand |
| Eleven thousand and two | Twelve thousand |
| Eleven thousand and three | Ten thousand |

```sql
SELECT DDB([LoanAmount], [LoanAmount]*.1, 15, 3) AS Amt 
FROM Accounts;
```

**输出：**

| Amt |
| --- |
| 1502.22222222222 |
| 1201.77777777778 |
| 1001.48148148148 |

## 2. FV()函数
MS Access中的`FV()`函数用于根据定期、固定付款和固定利率计算年金的未来价值。年金是在一段时间内支付的一系列固定现金。年金可以是贷款，也可以是投资。

**语法：**

```sql
FV(rate, nper, pmt, pv, type)
```

**参数：** 该方法接受五个参数，如上所述，如下所述：

*   `rate`：规定每期利率。
*   `nper`：指定年金中的支付期数合计。
*   `pmt`：指定每期付款。付款通常包含本金和利息，在年金的生命周期内不会改变。
*   `pv`：可选。它规定了一系列未来付款的现值（或一次付清）。
*   `type`：指定付款到期时间。如果付款在付款期结束时到期，则使用0；如果付款在付款期开始时到期，则使用1。

**返回：** 返回年金的未来值。

**注：** `rate`和`nper`参数必须使用以相同单位表示的付款期进行计算。例如，如果利率是用月份来计算的，`nper`也必须用月份来计算。收到的现金（如股息支票）用正数表示。

**示例-1：**
根据6%的年利率、“每月支付2次”和“每期支付50次”计算“贷款金额1000”的未来值。

```sql
SELECT FV(0.06/12, 2*12, -50, 1000, 0) AS FutureValue ;
```

**输出：**

| FutureValue |
| --- |
| 144.4379858485 |

**示例-2：**
根据6%的年利率、“每月支付1次”和“每期支付100次”计算贷款金额表的未来值。

**表–** `Accounts`

| AccountId | LoanAmount |
| --- | --- |
| One hundred and one | Five hundred |
| One hundred and two | One thousand |
| One hundred and three | One thousand two hundred |

```sql
SELECT FV(0.06/12, 1*12, -100, [LoanAmount], 0) AS Amt 
FROM Accounts;
```

**输出：**

| Amt |
| --- |
| 702.304600220726 |
| 176.723651279859 |
| -33.5087282964875 |