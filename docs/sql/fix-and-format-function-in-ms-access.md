# 在 MS 访问中固定()和格式化()功能

> 原文:[https://www . geesforgeks . org/fix-and-format-function-in-ms-access/](https://www.geeksforgeeks.org/fix-and-format-function-in-ms-access/)

**1。Fix()函数:**
在 MS Access 中，fix()函数返回一个数的整数部分。在这个函数中，一个数字将作为参数传递，它将返回该数字的整数部分。

**语法:**

```sql
Fix(number) 
```

**示例-1 :**

```sql
SELECT Fix(-75.43) AS FixNum;
```

**输出–**

| **固定 Num** |
| -75 |

**示例-2 :**

```sql
SELECT Fix(23.93) AS FixNum;
```

**输出–**

| **固定 Num** |
| Twenty-three |

**2。Format()函数:**
在 MS Access 中，format 函数会以指定的格式**返回一个数字。**在此功能中，值将作为第一个参数传递，格式将作为第二个参数**传递。**并返回转换后的格式。

<center>

| **格式** | **描述** |
| 通用号码 | 对于没有千位分隔符的。 |
| 标准 | 对于千位分隔符+小数点右边两位数字和小数点左边至少一位数字。 |
| 百分比 | 百分比值。 |
| 科学的 | 为了科学价值。 |
| 固定的；不变的 | 小数点左边一位，小数点右边两位。 |
| 货币 | 对于货币，使用千位分隔符和两位小数。 |
| 是/否 | 如果值==0，则否，否则是。 |
| 真/假 | 如果值==0，则为真，否则为假。 |
| 开/关 | 如果值==0，则关闭，否则打开。 |

</center>

**语法:**

```sql
Format(value, format) 
```

**示例-1 :**

```sql
SELECT Format(0.55, "Percent") 
AS FormattedPercentage;
```

**输出–**

| **格式百分比** |
| 55.00% |

**示例-2 :**

```sql
SELECT Format(0.0000000004500121424255, "Scientific") 
AS FormattedScientific;
```

**输出–**

| **格式化科学** |
| 4.50E-10 |