# MS Access 中的 FormatCurrency()和 FormatDateTime()函数

> 原文:[https://www . geesforgeks . org/format currency-and-format datetime-function-in-ms-access/](https://www.geeksforgeeks.org/formatcurrency-and-formatdatetime-function-in-ms-access/)

**1。FormatCurrency()函数:**
MS Access 中的 FormatCurrency()函数用于使用系统控制面板中定义的货币符号返回格式化为货币值的表达式。

**语法:**

```sql
FormatCurrency 
( 
Expression [, NumDigitsAfterDecimal ] 
           [, IncludeLeadingDigit ] 
           [, UseParensForNegativeNumbers ] 
           [, GroupDigits ] // It represent group digit.
)

```

**参数:**
FormatCurrency()接受五个参数，如上所述，如下所述。

*   **表达式–**
    它标识要格式化的表达式。
*   **numdigitsfertedcimal–**
    在此参数中，numdigitsfertedcimal 标识指示小数点右侧显示多少位的数值。-1 是默认值，表示使用了计算机的区域设置。它是可选的。
*   **包括前导数字–**
    在此参数中，前导数字表示分数是否显示前导零。它是可选的。
*   **使用参数值–**
    它指示是否在括号内放置负值。它是可选的。
*   **组数字–**
    它指示数字是否使用计算机区域设置中指定的组分隔符进行分组。它也是可选的

**注意:**
include elementdigit、UseParensForNegativeNumbers 和 GroupDigits 参数具有以下值。-1 表示真，0 表示假，2 表示默认值。

**返回:**
返回格式化后的货币值。

**示例-1 :**
换算为正货币值。

```sql
Select FormatCurrency(1200.2) as New_Currency;

```

**输出:**

| 新货币 |
| --- |
| $1, 200.20 |

**示例-2 :**
换算为负货币值。

```sql
Select Formatcurrency(-1000, 2, -1, -1, -1) 
AS New_Currency;

```

**输出:**

| 新货币 |
| --- |
| ($1, 000.00) |

**2。函数的作用是:返回一个格式化为日期或时间的表达式。**

**语法:**

```sql
FormatDateTime( Date [, NamedFormat ] )

```

**参数:**
FormatDateTime()接受上面提到的和下面描述的两个参数。

*   **日期–**
    它标识要格式化的表达式。
*   **名称格式–**
    它是一个数值，表示所使用的日期/时间格式。如果省略，则使用 GeneralDate。0 表示一般日期，1 表示长日期，2 表示短日期，3 表示短时间，4 表示长时间。

**返回:**
返回一个格式化的 Datetime 表达式。

**示例-1 :**
形成长日期。

```sql
SELECT FormatDateTime(#17/04/2004#, 1) 
as New_DFormat

```

**输出:**

| 新建 _ dformat |
| --- |
| 2004 年 4 月 17 日星期六 |

**例-2 :**
形成至长时间。

```sql
SELECT FormatDateTime(#12:30#, 4) 
as Long_Format;

```

**输出:**

| 长格式 |
| --- |
| 中午 12:30:00 |