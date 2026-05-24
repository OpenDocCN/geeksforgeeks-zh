# MS Access 中的 FormatCurrency() 和 FormatDateTime() 函数

> 原文: [https://www.geeksforgeeks.org/formatcurrency-and-formatdatetime-function-in-ms-access/](https://www.geeksforgeeks.org/formatcurrency-and-formatdatetime-function-in-ms-access/)

## 1. FormatCurrency() 函数

MS Access 中的 `FormatCurrency()` 函数用于使用系统控制面板中定义的货币符号返回格式化为货币值的表达式。

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
`FormatCurrency()` 接受五个参数，如上所述，如下所述。

*   `Expression` – 它标识要格式化的表达式。
*   `NumDigitsAfterDecimal` – 在此参数中，`NumDigitsAfterDecimal` 标识指示小数点右侧显示多少位的数值。-1 是默认值，表示使用了计算机的区域设置。它是可选的。
*   `IncludeLeadingDigit` – 在此参数中，前导数字表示分数是否显示前导零。它是可选的。
*   `UseParensForNegativeNumbers` – 它指示是否在括号内放置负值。它是可选的。
*   `GroupDigits` – 它指示数字是否使用计算机区域设置中指定的组分隔符进行分组。它也是可选的。

**注意:**
`IncludeLeadingDigit`、`UseParensForNegativeNumbers` 和 `GroupDigits` 参数具有以下值。-1 表示真，0 表示假，2 表示默认值。

**返回:**
返回格式化后的货币值。

**示例-1:**
换算为正货币值。

```sql
Select FormatCurrency(1200.2) as New_Currency;
```

**输出:**

| New_Currency |
| --- |
| $1, 200.20 |

**示例-2:**
换算为负货币值。

```sql
Select Formatcurrency(-1000, 2, -1, -1, -1) 
AS New_Currency;
```

**输出:**

| New_Currency |
| --- |
| ($1, 000.00) |

## 2. FormatDateTime() 函数

函数的作用是: 返回一个格式化为日期或时间的表达式。

**语法:**

```sql
FormatDateTime( Date [, NamedFormat ] )
```

**参数:**
`FormatDateTime()` 接受上面提到的和下面描述的两个参数。

*   `Date` – 它标识要格式化的表达式。
*   `NamedFormat` – 它是一个数值，表示所使用的日期/时间格式。如果省略，则使用 `GeneralDate`。0 表示 `GeneralDate`，1 表示 `LongDate`，2 表示 `ShortDate`，3 表示 `ShortTime`，4 表示 `LongTime`。

**返回:**
返回一个格式化的 Datetime 表达式。

**示例-1:**
形成长日期。

```sql
SELECT FormatDateTime(#17/04/2004#, 1) 
as New_DFormat
```

**输出:**

| New_DFormat |
| --- |
| Saturday, April 17, 2004 |

**例-2:**
形成至长时间。

```sql
SELECT FormatDateTime(#12:30#, 4) 
as Long_Format;
```

**输出:**

| Long_Format |
| --- |
| 12:30:00 PM |