# MySQL 中的 FORMAT()函数

> 原文:[https://www.geeksforgeeks.org/format-function-in-mysql/](https://www.geeksforgeeks.org/format-function-in-mysql/)

**FORMAT():**
MySQL 中的这个函数有助于格式化给定的数字，如' #，##，##。## "，将它们舍入到特定的小数点，并以字符串的形式返回结果。

**语法:**

```sql
FORMAT(N, D, locale)
```

**参数:**
这个函数一般接受三个参数。

*   **N–**
    要格式化的数字。
*   **D–**
    数字四舍五入到的小数位数。
*   **locale–**
    这是一个可选参数，决定了一千个分隔符以及分隔符之间的分组。默认情况下，在 MySQL 中存在 en_US 区域设置。

**返回:**
函数将给定的数字格式化，四舍五入到某个小数位，以字符串的形式返回数字。
**示例-1 :**
FORMAT()函数将给定的数字四舍五入到小数点后 2 位。

```sql
SELECT FORMAT(555454.12365, 2) AS form;
```

**输出:**

| 形式 |
| 555, 454.12 |

**示例-2 :**
FORMAT()函数将给定的数字四舍五入到小数点后 0 位。

```sql
SELECT FORMAT(130919999.456, 0) 
AS form;
```

**输出:**

| 形式 |
| 130, 919, 999 |

**示例-3 :**
用 de_D 区域设置替换 en_US 区域设置。

```sql
SELECT FORMAT(27112020.1052, 3, 'de_DE') As form;
```

**输出:**

| 形式 |
| 27.112.020, 105 |

**示例-4 :**
FORMAT()函数舍入表格中的列。
**创建产品表–**

```sql
CREATE TABLE Products(
Product_Id INT AUTO_INCREMENT,  
Product_Name VARCHAR(100) NOT NULL,
Price INT  NOT NULL,
PRIMARY KEY(Product_Id )
);
```

**在表格中插入数值:**

```sql
INSERT INTO Products(Product_Name, Price)
VALUES
('MotorolaMobile', 75000.999 ),
('SmartWatch', 73000.455 ),
('Camera', 170000.545 ) ;
```

该表将如下所示。

```sql
SELECT * FROM Products;
```

| 产品标识 | 产品名称 | 价格 |
| one | MotorolaMobile | Seventy-five thousand point nine nine nine |
| Two | 智能手表 | Seventy-three thousand point four five five |
| three | 照相机 | One hundred and seventy thousand point five four five |

现在，通过四舍五入到小数点后 1 位来格式化价格列。

```sql
SELECT  
   Product_Name, FORMAT(Price, 1) As New_price
FROM
   Products;
```

**输出:**

| 产品名称 | 新价格 |
| MotorolaMobile | 75, 001.0 |
| 智能手表 | 73, 000.5 |
| 照相机 | 170, 000.5 |

**注意–**
函数 FIND_IN_SET()在 MySQL 版及以上版本中工作。