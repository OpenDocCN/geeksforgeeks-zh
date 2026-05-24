# 移动台接入中的 IPmt()功能

> 原文:[https://www.geeksforgeeks.org/ipmt-function-in-ms-access/](https://www.geeksforgeeks.org/ipmt-function-in-ms-access/)

**MS Access 中的 IPmt()函数**用于返回一个 double，指定年金给定期间的利息支付，基于定期、固定支付和固定利率。

**语法:**

```sql
IPmt (rate, per, nper, pv [, fv ] [, type ])
```

**参数:**该方法在语法上接受六个参数，如上所述，描述如下:

*   **利率:**为双指定期利率。如果年百分比率(APR)为 5%，每月付款，则每个期间的比率为 0.05/12。
*   **per :** 在 1 到 nper 范围内的双指定支付期间。
*   **nper :** 为双精度，指定年金的支付周期总数。例如，如果五年汽车贷款按月付款，那么贷款总共有 5 * 12 = 60 个付款期。
*   **pv :** 在 Double 中指定一系列未来付款或收款的现值或今天的价值。
*   **fv :** 可选。它确定了你最终付款后想要的未来价值或现金余额。默认值为 0。
*   **类型:**可选。它规定了付款到期的时间。如果付款在付款期结束时到期，则使用 0；如果付款在付款期开始时到期，则使用 1。如果省略，则假定为 0。

**返回:**以双精度返回，指定利息支付。

**注:****费率**和 **nper** 参数必须使用以相同单位表示的付款期进行计算。例如:如果**费率**是用月计算的，那么 **nper** 也必须用月计算。

**示例-1 :**
以 10%卢比支付的利息。当年利率为 8 %且 TermInYears 为 5 时，为 100000。

```sql
SELECT IPMT(0.08/12, 10, 5*12, -100000, 0, 0) AS Interest_Paid ;
```

**输出:**

<figure class="table">

| Interest _ paid |
| --- |
| 582.796530417576 |

</figure>

**示例-2 :**
账户表中每个账户标识的利息支付计算。

**表─**

<figure class="table">

|  | [account id] | [Loan amount] | [Cancel] | End year] |
| --- | --- | --- | --- | --- |

</figure>

```sql
SELECT IPMT([AnnualRate]/12, 10, [TermInYears]*12, -[LoanAmount], 0, 0) AS INTPaid 
FROM Accounts;
```

**输出:**

<figure class="table">905.149502978079T20】1051.90923080389

| intpayed |
| --- |
| 733.18850390563 |
| Six thousand seven hundred and eighty-eight |

</figure>