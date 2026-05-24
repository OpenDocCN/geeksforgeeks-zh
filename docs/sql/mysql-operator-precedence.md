# MySQL |操作员优先

> 原文:[https://www.geeksforgeeks.org/mysql-operator-precedence/](https://www.geeksforgeeks.org/mysql-operator-precedence/)

运算符优先级指定当表达式中两个或多个具有不同优先级的运算符相邻时，运算符的求值顺序。

对于**示例**，与(1+2)/3 相比，1+2/3 给出了不同的结果。就像所有其他编程语言 C，C++，Java 等一样。MySQL 也有一个优先规则。

下表描述了 MySQL 中从最高到最低的运算符优先级。同一组中的运算符具有相同的优先级。

<center>

| **操作员** | **描述** |
| --- | --- |
| 间隔 | 返回小于第一个参数的参数索引 |
| 二进制
整理 | 这是一种存储二进制字节字符串的类型
无论默认的比较排序规则是什么，该子句都会覆盖 |
| ！ | 负值 |
| –
~ | 它改变操作数的符号
它反转操作数的位 |
| ^ | 按位异或 |
| *
/
div
%，MOD | 乘法运算符
除法运算符
整数除法(丢弃除法的小数部分)
模运算符 |
| –
+ | 减运算符
加法运算符 |
| <<
> > | 向左移动(BIGINT)数字或二进制字符串
向右移动(BIGINT)数字或二进制字符串 |
| & | 按位“与” |
| &#124; | 按位“或” |
| =
< = >
> =，>
< =，<
< >，！=
是
喜欢
REGEXP
IN | 比较运算符
空-安全等于运算符
大于/大于或等于
小于/小于或等于
不等于运算符
根据布尔值
测试值模式匹配运算符
将字符串表达式与正则表达式
进行匹配检查列表中是否存在值 |
| 在
情况下，然后是其他情况 | 检查数值是否在数值范围内
Case 运算符 |
| 不 | 否定价值 |
| AND，&& | 逻辑“与” |
| 异或 | 逻辑异或 |
| 或，&#124;&#124; | 逻辑或 |
| =
:= | 赋值(作为更新语句中 SET 语句/SET 子句的一部分)
赋值 |

这些运算符优先规则极大地影响了我们的 MySQL 查询。如果不知道运算符优先级，我们可能会得到意想不到的结果。要理解这一点，请考虑下表**学生**。

<center>

| **id** | **名称** | **标记** |
| --- | --- | --- |
| one | 帕帕尔 | Twelve |
| Two | 卡什 | nine |
| three | Reeta | Nineteen |
| four | 快活的 | Fifteen |
| five | Shanu | five |
| six | Punit | seven |

</center>

从上表中，我们需要那些分数大于 10 分，名字以“p”或“s”开头的学生的成绩。所以，它的查询可以写成-

```sql
mysql>select * 
from student 
where marks>10 and name like 'p%' 
                   or name like 's%'; 
```

**结果:**
会产生想要的结果:

<center>

| **id** | **名称** | **标记** |
| --- | --- | --- |
| one | 帕帕尔 | Twelve |
| four | 快活的 | Fifteen |
| six | Punit | seven |

</center>

该结果集与查询中预期的不同。因为它给出了学生分数低于 10 分的“惩罚”结果，这是不必要的。由于运算符“与”的优先级高于“或”，上述查询给出了所有分数大于 10 且姓名以“s”开头的学生的结果，此外，输出中还给出了姓名以“p”开头的学生的结果。所以，圆括号的作用来了。上述查询可以写成，

```sql
mysql>select * 
from student 
where marks>10 and (name like 'p%' 
                       or name like 's%');
```

**结果:**
会产生想要的结果:

<center>

| **id** | **名称** | **标记** |
| --- | --- | --- |
| one | 帕帕尔 | Twelve |
| four | 快活的 | Fifteen |

</center>

Hence, this precedence of the operator can be overridden by making use of parenthesis.</center>