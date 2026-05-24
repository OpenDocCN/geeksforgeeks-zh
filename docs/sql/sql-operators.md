# SQL 运算符

> 原文:[https://www.geeksforgeeks.org/sql-operators/](https://www.geeksforgeeks.org/sql-operators/)

运算符是任何编程语言的基础。我们可以将运算符定义为符号，帮助我们对操作数执行特定的数学和逻辑计算。换句话说，我们可以说一个运算符操作操作数。SQL 运算符有三种不同的类别。

*   [算术运算符](https://www.geeksforgeeks.org/sql-arithmetic-operators/)
*   比较运算符
*   [逻辑运算符](https://www.geeksforgeeks.org/sql-and-and-or-operators/)

### **算术运算符**:

我们可以对存储在表中的数据使用各种算术运算符。算术运算符有:

<figure class="table">

| **s . no .** | **Operator** | **Description** |
| one | + | 加法用于对数据值执行加法运算。 |
| Two | – | 该运算符用于数据值的减法运算。

 |
| three | / | 这个运算符使用‘ALL’关键字，它计算除法运算。 |
| four | * | 此运算符用于相乘数据值。 |
| five | % | 模数是用来在数据被另一个除的时候得到余数。 |

</figure>

### **对比**操作员:

SQL 中另一个重要的运算符是比较运算符，它用于将一个表达式的值与其他表达式进行比较。SQL 支持不同类型的比较运算符，描述如下:

<figure class="table">

| **S 号** | **Operator** | **Description** |
| one | = | Equal to. |
| Two | > | Greater than. |
| three | < | No. |
| four | >= | Greater than or equal to. |
| five | <= | Less than or equal to. |
| six | <> | Not equal to. |

</figure>

### 逻辑运算符:

逻辑运算符是那些对或错的运算符。它们返回真值或假值来组合一个或多个真值或假值。

<figure class="table">

| **序列号** | **操作员** | **描述** |
| one | [and](https://www.geeksforgeeks.org/sql-and-and-or-operators/) | logic AND 将两个 Booleans 作为表达式进行比较，当两个表达式都为真时返回 true。 |
| Two | [或](https://www.geeksforgeeks.org/sql-and-and-or-operators/) | Logical OR 将两个布尔值作为表达式进行比较，当其中一个表达式为真时返回 true。 |
| three | [不是](https://www.geeksforgeeks.org/sql-not-operator/) | NOT 以单个布尔为自变量，将其值由假变真或由真变假。 |

</figure>

### **特殊操作员:**

<figure class="table">

| **序列号** | **操作员** | **描述** |
| one | [全部](https://www.geeksforgeeks.org/sql-all-and-any/) | ALL 用于选择 select 语句的所有记录。它将一个值与查询结果列表中的每个值进行比较。“全部”前面必须有比较运算符，如果查询没有返回任何行，则计算结果为“真”。 |
| Two | [任意](https://www.geeksforgeeks.org/sql-all-and-any/) | ANY 将一个值与查询结果列表中的每个值进行比较，如果内部查询的结果至少包含一行，则计算结果为 true。 |
| three | [在](https://www.geeksforgeeks.org/sql-between-in-operator/)之间 | “之间”运算符根据范围测试表达式。该范围由一个开头、一个 AND 关键字和一个结束表达式组成。 |
| four | [输入](https://www.geeksforgeeks.org/sql-between-in-operator/) | IN 运算符检查由逗号分隔的一组值中的一个值，并从表中检索匹配的行。 |
| five | [存在](https://www.geeksforgeeks.org/sql-exists/) | EXISTS 检查子查询结果的存在性。EXISTS 子查询测试子查询是否至少获取一行。当没有数据返回时，该运算符返回“假”。 |
| six | [部分](https://www.geeksforgeeks.org/sql-some/) | 有些运算符计算外部表和内部表之间的条件，如果最终结果返回任意一行，则计算结果为真。如果不是，那么它的计算结果为假。 |

</figure>