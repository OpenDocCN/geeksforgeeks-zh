# 移动台接入中的变量类型功能

> 原文:[https://www . geesforgeks . org/vartype-function-in-ms-access/](https://www.geeksforgeeks.org/vartype-function-in-ms-access/)

在本文中，我们将介绍 MS Access 中的 VarType 函数，并将介绍 VarType 函数的变量类型，还将介绍每个 VarType 函数的返回类型。我们一个一个来讨论。

**VarType :**

它是微软 Access 中的函数，用于返回一个整数，表示变量的子类型。在 MS Access 中，VarType()函数返回一个整数，该整数表示变量的子类型，比如如果一个值是一个整数值，那么它将简单地返回 2 作为整数。

**语法:**

```sql
VarType ( varname )
```

*   **参数–**该方法接受一个参数，如上所述，如下所述。
*   **varname–**它是包含除用户定义类型的变量之外的任何变量的变体。

**返回:**
返回表示变量类型的整数。

**示例–**

在这个例子中，您可以看到所有的变量类型名称和每个类型的返回值。此外，为了更好地理解，请描述每个变量类型。

<center>

| **常量(变量类型名称)** | **可变类型描述** | **返回值** |
| --- | --- | --- |
| **清空** | 空(未初始化) | Zero |
| **零** | Null(无有效数据) | one |
| **整数** | 整数 | Two |
| **长** | 长整数 | three |
| **单** | 单精度浮点数 | four |
| **加倍** | 双精度浮点数 | five |
| **货币** | 币值 | six |
| **日期** | 日期值 | seven |
| **弦** | 线 | eight |
| **物体** | 目标 | nine |
| **错误** | 误差值 | Ten |
| **布尔** | 布尔值 | Eleven |
| **变体** | **变体**(仅用于变体阵列) | Twelve |
| 数据对象 | 数据访问对象 | Thirteen |
| **十进制** | 十进制值 | Fourteen |
| **字节** | 字节值 | Seventeen |
| **user define type** | 包含用户定义类型的变体 | Thirty-six |
| **阵列** | 排列 | Eight thousand one hundred and ninety-two |

</center>

**示例–**

让我们考虑像 80000 这样的长整数值，如果您使用 VarType 函数，那么它将返回 3 作为长整数。

```sql
SELECT VarType(80000);

```

**输出–**

```sql
3  

```

**示例–**

让我们考虑像 11.1 这样的十进制值，如果您将使用 VarType 函数，那么它将为十进制返回 14。

```sql
SELECT VarType(11.1);

```

**输出:**

```sql
14

```

**示例–**

让我们考虑一个像 Geeksforgeeks 这样的字符串值，如果您将使用 VarType 函数，那么它将为字符串返回 8。

```sql
SELECT VarType( "Geeksforgeeks");

```

**输出:**

```sql
8

```

**示例–**

让我们考虑像#11/09/20#这样的日期值，如果您将使用 VarType 函数，那么它将返回 7 作为日期值。

```sql
SELECT VarType( #11/09/20# );

```

**输出–**

```sql
7
```

**在 Visual Basic 中实现 VarType 函数:**

让我们在 Visual basic 中为应用程序实现 VarType 函数。演示**变量类型**功能以确定变量子类型的程序。

**示例–**

```sql
Dim StrVar, DateVar, IntVar, MyFun

StrVar     =  "Ashish"
DateVar =  #11/09/20# 
IntVar     =  500

MyFun   =  VarType(DateVar)   ' Returns 7.
MyFun     =  VarType(StrVar)    ' Returns 8.
MyFun   =  VarType(IntVar)    ' Returns 2.
```